# Integration patterns (CI gates)

## Pattern A — Admission control in PR (recommended)
- PR triggers admissibility checks
- Contract present? constraints satisfied?
- Evidence artifacts uploaded
- Merge allowed only if admissible

## Pattern B — Scheduled governance audits
- Nightly/weekly run
- Generates drift + missing evidence report
- Alerts on policy violations

## GitHub Actions / GitLab CI / Azure DevOps
- Same concept: stages + gates + artifacts retention
- Strong default: fail-closed on missing decision evidence
