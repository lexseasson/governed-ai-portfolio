# 15-Minute Evaluation Checklist (Hiring Loop)

Use this checklist to evaluate the work as control-plane engineering, not a demo.

## A) Admission control exists (not just logging)
- [ ] A contract defines bounded authority (can_write_paths + cannot_touch)
- [ ] CI blocks out-of-bounds changes deterministically
- [ ] Decision record is generated even on failure

## B) Audit surface is defensible
- [ ] Audit trail is append-only (ndjson)
- [ ] Run records route + diff strategy + hashes
- [ ] Artifacts are tied to inputs (inputs_hash + artifact_hash)

## C) Drift and erosion are measurable
- [ ] Contract drift classifies sensitive-field deltas (low/medium/high)
- [ ] Boundary pressure quantifies repeated boundary hits
- [ ] Decision debt estimates revalidation need

## D) Governance governs itself
- [ ] Governance surface changes route to constitutional/maintenance posture
- [ ] No implicit exemptions for workflows/engine changes
- [ ] Determinism is explicit and recorded

## E) Operational realism
- [ ] Windows runbook exists
- [ ] Demo scripts clean up safely
- [ ] Failure runs still produce artifacts (incident-response posture)
