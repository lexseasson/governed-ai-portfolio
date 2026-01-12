# Systems map (expanded)

## One-line summary
This portfolio demonstrates a progression from **quantitative decision-making** to **change governance** to **decision admissibility**.

---

## Diagram 1 — trajectory
```mermaid
flowchart LR
  Econ[Economics + Risk + Econometrics] --> ML[Applied ML]
  ML --> CS[Crypto Signals Ensemble]
  CS --> DT[DevTracker Governance]
  DT --> ADL[Agentic Decision Ledger]

  CS:::repo
  DT:::repo
  ADL:::repo

  classDef repo fill:#111,stroke:#999,color:#fff;

---

## Diagram 2 — Control plane vs execution plane
```mermaid 
flowchart TB
  subgraph Execution[Execution plane (can be stochastic)]
    X1[Agents / Pipelines / Models]
  end

  subgraph Control[Control plane (must be deterministic)]
    C1[Admissibility Gates (CI)]
    C2[Decision Contracts]
    C3[Evidence Artifacts]
  end

  X1 --> C3
  C1 --> X1
  C2 --> C1