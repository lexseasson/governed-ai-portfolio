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