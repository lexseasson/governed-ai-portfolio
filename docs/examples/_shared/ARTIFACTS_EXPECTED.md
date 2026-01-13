# Expected Artifacts (Audit + Steward)

These artifacts are the evidence surface.  
They exist to make governance **inspectable after the fact** (incident response, audit, turnover).

## Always-on artifacts (baseline)

### Decision Record
- Location: `agentic-decision-ledger/artifacts/decision_records/`
- Content: admitted/blocked, checks, failures, changed_paths, contract id

### Snapshot
- Location: `agentic-decision-ledger/artifacts/snapshots/`
- Content: commit/run state captured for reproducibility

## v0.2 Steward + Audit artifacts (muscle)

### Audit Trail (append-only)
- `agentic-decision-ledger/artifacts/audit/audit_trail.ndjson`
- Purpose:
  - route chosen + why
  - diff strategy (base/head)
  - inputs_hash + artifact hashes
  - admitted/blocked + primary failures

### Boundary Pressure Report
- `agentic-decision-ledger/artifacts/steward/boundary_pressure_report.json`
- Purpose:
  - measure pressure on governance boundaries
  - quantify forbidden touches, out-of-bounds attempts, surface expansion
  - support “erosion before drift becomes policy”

### Contract Drift Report
- `agentic-decision-ledger/artifacts/steward/contract_drift_report.json`
- Purpose:
  - semantic deltas across sensitive fields (owner, scope, bounded authority, safety)
  - classifies drift as low/medium/high

### Decision Debt Report
- `agentic-decision-ledger/artifacts/steward/decision_debt_report.json`
- Purpose:
  - portfolio-level debt scoring (age, volatility, evidence gap, owner ambiguity, recurrence)
  - produces revalidation recommendations

### Evidence References
- `agentic-decision-ledger/artifacts/steward/evidence_refs.json`
- Purpose:
  - explicit missing evidence refs for assumptions/KPIs/policies
  - prevents post-hoc rationalization

### Stewardship Summary (executive)
- `agentic-decision-ledger/artifacts/steward/stewardship_summary.md`
- Purpose:
  - 1 page: what changed, what risk increased, what to do next
  - architecture language, not ML language

## Why hiring managers care

- These artifacts turn “we have policy” into “we can prove policy enforcement”.
- They reduce forensic cost and ambiguity under incidents.
- They make governance survivable under turnover and change velocity.
