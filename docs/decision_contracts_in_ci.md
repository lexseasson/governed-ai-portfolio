# Decision Contracts in CI  
## Enforcing Admissibility Before Change Ships

This document is a **technical demo and design note**.

It shows how to enforce decisions as **admission-controlled contracts** at commit-time, using CI as the control plane.

No runtime magic.  
No post-hoc reconstruction.  
No governance theater.

---

## The problem this solves

In many production systems:

- Changes ship because tests pass.
- Logs exist after deployment.
- Metrics drift slowly.
- Incidents happen weeks later.
- Nobody can answer: 

**who approved this change and under what constraints?**

At that point, teams try to reconstruct intent from logs.

That is already a failure.

---

## Core principle

**Logs are forensic artifacts.  
Decisions are contracts.**

A decision must exist **before** a change is allowed to merge.

If no explicit decision exists, the change is **not admissible**.

---

## What is a Decision Contract?

A decision contract is a **minimal, explicit declaration** that answers:

- Who owns the decision?
- What scope does it affect?
- What risk level does it carry?
- Under which constraints is it admissible?
- Who must approve it?
- For how long is it valid?

It is not documentation.  
It is an **admission requirement**.

---

## Minimal Decision Contract (schema)

Below is a **minimal but sufficient** schema.
Anything smaller loses accountability.

```yaml
# decisions/contracts/example_decision.yml

decision_id: DEC-2024-001
title: "Enable autonomous model retraining"
owner: "data-platform-steward"
scope:
  - "model-training"
  - "feature-generation"
risk_level: HIGH   # LOW | MEDIUM | HIGH
constraints:
  - "training_data_source == approved"
  - "human_review == true"
approvals_required:
  - role: "steward"
  - role: "security"
expires_at: "2024-12-31"
```

Design notes:
Owner is a human role, not a system.
Risk level drives enforcement strictness.
Constraints are declarative, not procedural.
Expiration prevents decisions from living forever.

CI as admission control:
CI evaluates admissibility, not behavior.

The rule is simple:

If a change requires a decision and no valid contract exists, the merge is blocked.

This gate runs at commit/PR time.
Runtime can remain stochastic; governance cannot.

Fail-closed vs fail-open (explicit trade-off):

| Context            | Strategy         | Rationale                                         |
| ------------------ | ---------------- | ------------------------------------------------- |
| Production         | Fail-closed      | Missing intent is higher risk than delayed change |
| Regulated systems  | Fail-closed      | Auditability > velocity                           |
| Research / sandbox | Fail-open (warn) | Exploration allowed, but evidence still generated |
| Prototyping        | Fail-open (warn) | Learning phase, not decision phase                |


Rule of thumb:
Fail-open still produces artifacts and warnings.
Fail-closed blocks state change.

Minimal demo (Windows CMD, reproducible):
This is a local simulation of the CI gate.

1) Create folders (CMD):

From your repo root (for example, governed-ai-portfolio)

mkdir decisions
mkdir decisions\contracts
mkdir ci

2) Create the contract file (CMD):

Open Notepad

notepad decisions\contracts\example_decision.yml


Paste the YAML from the “Minimal Decision Contract” section and save.

3) Create the CI gate script (CMD):

Open Notepad

notepad ci\check_admissibility.py


Paste the script below and save.

ci/check_admissibility.py (minimal gate):

import sys
from datetime import datetime, timezone

try:
    import yaml
except ImportError:
    print("❌ Missing dependency: pyyaml")
    print("Install with: python -m pip install pyyaml")
    sys.exit(2)


REQUIRED_KEYS = [
    "decision_id",
    "title",
    "owner",
    "scope",
    "risk_level",
    "constraints",
    "expires_at",
]


def fail(msg: str, code: int = 1) -> None:
    print(f"❌ {msg}")
    sys.exit(code)

def parse_date(date_str: str) -> datetime:
    # Expect YYYY-MM-DD
    try:
        dt = datetime.fromisoformat(date_str)
    except ValueError:
        fail(f"expires_at must be ISO format YYYY-MM-DD, got: {date_str}")
    # Make timezone-aware (UTC) for safe comparison
    return dt.replace(tzinfo=timezone.utc)


def main() -> None:
    if len(sys.argv) != 2:
        fail("Usage: python ci\\check_admissibility.py decisions\\contracts\\example_decision.yml", code=2)

    path = sys.argv[1]

    try:
        with open(path, "r", encoding="utf-8") as f:
            decision = yaml.safe_load(f) or {}
    except FileNotFoundError:
        fail(f"Decision contract not found: {path}")
    except Exception as e:
        fail(f"Could not read decision contract: {e}")

    for k in REQUIRED_KEYS:
        if k not in decision:
            fail(f"Missing required key '{k}' in contract")

    risk = str(decision["risk_level"]).upper().strip()
    if risk not in {"LOW", "MEDIUM", "HIGH"}:
        fail(f"risk_level must be LOW|MEDIUM|HIGH, got: {decision['risk_level']}")

    owner = str(decision["owner"]).strip()
    if not owner:
        fail("owner must be a non-empty string (human role)")

    expires_at = parse_date(str(decision["expires_at"]).strip())
    now = datetime.now(timezone.utc)
    if expires_at < now:
        fail(f"Decision contract expired at {decision['expires_at']} (UTC)")

    # Approval policy: HIGH risk requires approvals_required entries
    if risk == "HIGH":
        approvals = decision.get("approvals_required")
        if not approvals or not isinstance(approvals, list) or len(approvals) == 0:
            fail("HIGH risk decision requires approvals_required (non-empty list)")

    print("✅ Decision admissible (contract valid)")
    print(f"   decision_id: {decision['decision_id']}")
    print(f"   owner: {decision['owner']}")
    print(f"   risk_level: {risk}")
    print(f"   expires_at: {decision['expires_at']}")


if __name__ == "__main__":
    main()

Run the demo (CMD):
1) Install the only dependency:
python -m pip install pyyaml

2) Run the gate:
python ci\check_admissibility.py decisions\contracts\example_decision.yml


Expected output:

✅ Decision admissible (contract valid)

3) Test failure quickly:

Edit the contract and set

expires_at: "2000-01-01"


Re-run the gate. It should fail with

❌ Decision contract expired…

This is what “fail-closed” looks like.

How this becomes real CI (GitHub Actions in one paragraph):

In a GitHub Actions workflow, you run the same command on pull requests

python -m pip install pyyaml
python ci\check_admissibility.py decisions\contracts\example_decision.yml


If the script exits non-zero, the PR is blocked.

This is governance as admission control are deterministic, reviewable, auditable.:

What this blocks in practice:

Silent behavior changes without ownership
“The model decided” post-hoc explanations
Drift without explicit responsibility
Retroactive approval theater
Accountability loss during team turnover
