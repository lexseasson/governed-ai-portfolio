# Capsule 3 — Governance Evolution (meta-governance / constitutional posture)

## Context
The highest-risk class of change is when the governance layer itself changes:
- workflows,
- routing logic,
- gate engine,
- schemas,
- enforcement defaults.

If these can change without explicit constitutional governance, the control plane becomes an attack surface.

This posture treats governance evolution as “constitutional risk”.

---

## Posture statement (architecture terms)

### Governance surfaces (control plane)
- `.github/workflows/**`
- `integrations/**` (actions, routing logic, CI integration)
- governance engine code (`adl/**` in the implementation repo)
- dependency wiring (e.g., `pyproject.toml`)
- tests that define admissibility behavior

### Routing rule
If a PR touches any governance surface, it routes to the **maintenance/constitutional** contract posture.

This produces the “no special humans” property:
the team that owns enforcement is also governed.

---

## What the evaluator should inspect

### 1) Constitutional invariants are explicit
Examples of invariants:
- forbidden domains remain forbidden unless changed under constitutional posture,
- strictness cannot be toggled casually,
- routing logic changes must have recorded rationale.

### 2) Audit trail captures route + reason (not just outcome)
A serious system records:
- route chosen (why this posture),
- trigger (which changed path matched governance surface),
- diff strategy and base/head metadata,
- hashes tying inputs to outputs.

This is the difference between “logs” and “audit evidence”.

### 3) Drift classification treats governance weakening as high risk
Removing checks, widening surfaces, weakening cannot-touch rules:
these must be automatically treated as high risk by default.

---

## Real failure modes this posture mitigates
- **Meta-governance drift**: the gate weakens quietly “just this once”.
- **Non-deterministic governance**: reruns disagree because diff selection is unstable.
- **Permission laundering**: indirect changes alter enforcement without touching forbidden domains.

---

## Why this matters in real orgs
This posture makes governance survivable:
- under audit,
- under incident response,
- under personnel churn.

It upgrades governance from “process” to “control plane engineering”.
