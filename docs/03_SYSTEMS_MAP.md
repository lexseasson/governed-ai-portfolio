
# Systems Map — Architecture & Responsibility

## One-line summary

This portfolio demonstrates a progression from **quantitative decision-making** to **change governance** to **decision admissibility**.

It is a map of **responsibility escalation**, not feature accumulation.

---

## Diagram 1 — Career and system trajectory

```mermaid
flowchart LR
  Econ["Economics + Risk + Econometrics"] --> ML["Applied ML"]
  ML --> CS["Crypto Signals Ensemble"]
  CS --> DT["DevTracker Governance"]
  DT --> ADL["Agentic Decision Ledger (ADL)"]

  classDef repo fill:#111,stroke:#999,color:#fff;
  class CS,DT,ADL repo;

flowchart TB
  subgraph Execution["Execution plane (can be stochastic)"]
    X1["Agents / Pipelines / Models"]
  end

  subgraph Control["Control plane (must be deterministic)"]
    C1["Admissibility Gates (CI)"]
    C2["Decision Contracts"]
    C3["Evidence Artifacts"]
  end

  X1 --> C3
  C2 --> C1
  C1 --> X1

flowchart LR
  subgraph Repo1["Crypto Signals Ensemble"]
    R1a["Signal extraction"]
    R1b["Risk metrics"]
    R1c["Reproducibility"]
  end

  subgraph Repo2["DevTracker Governance"]
    R2a["Evidence boundary"]
    R2b["Audit reports"]
    R2c["Machine snapshots"]
  end

  subgraph Repo3["ADL"]
    R3a["Decision contracts"]
    R3b["Admissibility checks"]
    R3c["CI gates"]
  end

  Repo1 --> Repo2 --> Repo3

