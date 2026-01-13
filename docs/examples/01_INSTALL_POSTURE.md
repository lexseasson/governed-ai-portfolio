# Capsule 1 — Docs-only Install Posture (ultra minimal adoption)

## Context
Most governance initiatives fail at the adoption edge:
the first step is too costly (process burden), so teams route around it.

This posture makes adoption cheap while keeping the core invariant:
**every change has deterministic, reviewable evidence**.

---

## Posture statement (architecture terms)

### Allowed change surfaces
- `docs/**`
- (optionally) `artifacts/**` as emitted outputs

### Disallowed / out-of-scope surfaces
- `.github/**` (CI enforcement plane)
- `integrations/**` (routing and gate integration)
- `adl/**` or any governance engine code (control-plane logic)
- `scripts/**`, `examples/**` (product/demo execution surfaces)
- dependency wiring (`pyproject.toml`, tests)

### Routing rule
If a PR touches anything outside the allowed surfaces, it must not “pretend install”:
it routes to a stricter posture (product or maintenance).

This is the core safety property:
**adoption cannot be used as a loophole**.

---

## What the evaluator should inspect

### 1) Adoption friction (organizational ergonomics)
- Docs-only PRs should admit without negotiation.
- The “first PR” should not require governance expertise.

### 2) Evidence quality (audit posture)
Even a docs-only change must create artifacts that answer:
- what posture was applied (route),
- what contract governed it,
- what changed paths were evaluated,
- whether the change was admitted or blocked.

A governance system without evidence is not governance; it is policy theater.

### 3) Determinism (repeatability)
A rerun of the same PR should produce the same route and the same changed-path set,
or explain deviations explicitly in the audit trail (base/head selection, event type).

---

## Real failure modes this posture mitigates
- **Non-deterministic diff selection**: governance becomes non-repeatable.
- **Permission laundering**: “it was docs” while affecting execution via indirection.
- **Governance theater**: compliance claims without enforceable evidence.

---

## Why this matters in real orgs
This posture is the “land-and-expand” pattern for governance:
you can get adoption first, then progressively tighten posture where real risk exists,
without rebuilding the system or rewriting history.
