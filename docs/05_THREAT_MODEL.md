# Threat model (STRIDE-light + operational)

## Assets
- Decision intent (owner, approver, constraints)
- Evidence integrity (artifacts, reports)
- Admissibility checks (CI gates)
- Secrets (tokens, keys)

## Threats
- Spoofing: fake approver identity
- Tampering: editing evidence after the fact
- Repudiation: “nobody approved this”
- Disclosure: secrets leaking in logs/artifacts
- DoS: gates too noisy to use
- Elevation: bypassing checks

## Diagram — admissibility in CI
```mermaid
sequenceDiagram
  participant Dev as Developer/Agent
  participant PR as Pull Request
  participant CI as CI Admissibility Gates
  participant Art as Artifacts (Evidence)
  participant Main as main

  Dev->>PR: change + decision contract
  PR->>CI: run checks
  CI->>Art: write snapshots + audit report
  CI-->>PR: pass/fail + reason
  CI->>Main: merge only if admissible
