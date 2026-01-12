# ADL boom checklist (today/tomorrow)

Goal: turn ADL from “strong concept” into “auditable control primitive”.

## Minimum deliverables (high signal)
1) A **hello decision contract**
- `decisions/contracts/hello_world.yml`
- fields: owner, scope, constraints, risk level, required approvals

2) A **demo that produces artifacts**
- `examples/happy_path/run_demo.cmd` (Windows CMD)
- outputs: `artifacts/sample_run/decision.json` + `audit.md`

3) A **CI admissibility gate**
- GitHub Action runs on PR
- fails closed if contract missing/invalid
- uploads artifacts

## What “boom” looks like
- Hiring can click: contract → CI gate → generated artifacts
- They can reproduce locally in CMD
- Claims become falsifiable in 5 minutes
