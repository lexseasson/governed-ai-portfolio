
# Architecture & innovation (seniority signals)

## The primitives (what’s actually non-trivial)
### 1) Evidence boundary
- Humans own **semantics**: intent, priority, ownership, acceptance criteria.
- Automation owns **evidence**: timestamps, diffs, metrics, run IDs, provenance.
- Outcome: automation helps without overwriting meaning.

### 2) Decision admissibility (commit-time)
- A change is a state transition.
- It is admissible only if explicit constraints are satisfied.
- Outcome: governance becomes part of delivery, not meetings.

### 3) Control plane vs execution plane
- Execution can be agentic/stochastic.
- Admission control must be deterministic, legible, and auditable.

---

## Trade-offs (explicit)
- You add commit-time friction to reduce forensic cost after incidents.
- Deterministic gates may block “useful” change when intent/constraints are missing.
- Evidence-first designs privilege legibility over raw speed.

---

## Failure modes we design against
- Silent regressions shipped as “minor refactors”
- Post-hoc rationalization (“the model decided that…”)
- Organizational amnesia across quarters
- Ownership ambiguity under pressure (“who approved this?”)

---

## Non-goals (to avoid tool-sprawl)
- This portfolio is not a full MLOps suite.
- DevTracker is not a project manager replacement.
- ADL is not a workflow engine; it’s an admissibility layer.
