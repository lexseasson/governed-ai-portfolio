# Capsule 2 — Product Posture (bounded authority across docs/examples/scripts)

## Context
In real repos, the risky surface area is not only “code”.
It is the operational perimeter:
- scripts,
- demos,
- examples,
- runbooks,
- config-like docs that influence execution.

This posture governs those surfaces with bounded authority and drift telemetry.

---

## Posture statement (architecture terms)

### Allowed change surfaces (bounded authority)
- `docs/**`
- `examples/**`
- `scripts/**`
- `decisions/contracts/**`
- `artifacts/**` (outputs)

### Forbidden surfaces (constitutional red lines)
- `.github/workflows/**` (enforcement plane)
- secrets material / credentials / token stores
- execution-plane directories (org-specific; treat as cannot-touch)

### Principle
Bounded authority is not “trust”; it is a *typed interface*:
- `can_write_paths` expresses allowed effects,
- `cannot_touch` expresses explicit invariants.

---

## What the evaluator should inspect

### 1) Bounded authority is actually useful
The allowed surface should be non-trivial (you can do meaningful work)
but not dangerous (you cannot alter enforcement).

### 2) Drift is semantic, not cosmetic
Contract drift should be classifiable deterministically:
- **Low drift**: formatting, reordering, titles.
- **Medium drift**: expanding `can_write_paths`, broadening includes materially.
- **High drift**: weakening/removing `cannot_touch`, changing owner/approver, removing excludes, relaxing safety constraints.

A senior control plane does not “debate drift”; it measures it.

### 3) Pressure telemetry exists (boundary pressure)
Repeated out-of-bounds attempts are governance health signals:
- misaligned incentives,
- unclear boundaries,
- insufficient posture separation.

Pressure is not just “failure”: it is operational telemetry for stewards.

---

## Real failure modes this posture mitigates
- **Scope/authority creep**: slow expansion until the agent can modify enforcement.
- **Policy bypass by indirection**: change a generator/script instead of the forbidden target.
- **Artifact spoofing**: outputs exist but are not cryptographically bound to inputs.

---

## Why this matters in real orgs
This posture supports delivery velocity without letting “product convenience”
gradually erode governance invariants.
It is the difference between:
- “We have policy,” and
- “We can prove policy under incident review.”
