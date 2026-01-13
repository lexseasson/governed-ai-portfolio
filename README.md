# Governed AI Portfolio — Admission Control for Agentic Change

> **Positioning:** control-plane architecture for AI / agentic systems, focused on admissibility, auditability, and governance-by-construction.

---

## What this portfolio is (and is not)

> [!IMPORTANT]
> This is **not** a projects gallery.  
> It is a **coherent professional trajectory** showing how responsibility escalates from signal → change governance → decision admissibility.

**This portfolio is:**
- A landing page for Staff / Principal / Architect hiring loops.
- A set of **falsifiable claims** backed by inspectable artifacts.
- A fast path to evaluate real-world governance and model-risk thinking.
- **Hiring capsules (3 governed change scenarios)**  
  Concrete, inspectable examples of admission control, bounded authority, and governance evolution:  
  → `docs/10_HIRING_EXAMPLES.md`



**This portfolio is not:**
- a SaaS pitch,
- a hype deck,
- a promise of safe autonomy by default,
- a replacement for organizational responsibility.

---

## The trajectory (coherent, not parachuted)

My path is deliberate and cumulative:

**Economics → Risk management → Econometrics → Applied ML → Crypto decision systems → Change governance → Decision admissibility**

Why this matters:
- Economics and risk force explicit treatment of uncertainty and incentives.
- Econometrics and ML expose drift, fragility, and overfitting.
- Crypto decision systems impose real cost of error and reproducibility discipline.
- Governance emerges naturally when scale, turnover, and time enter the system.

### Anchor repositories

1) **Crypto Signals Ensemble**  
Signal extraction, uncertainty management, and risk metrics under real cost of error.  
https://github.com/lexseasson/crypto_signals_ensemble

2) **DevTracker Governance**  
Governance as admission control for change; evidence boundary and audit artifacts.  
https://github.com/lexseasson/devtracker-governance

3) **Agentic Decision Ledger (ADL)**  
Decision contracts and commit-time admissibility (**Decision ≠ Log**).  
https://github.com/lexseasson/agentic-decision-ledger

---
## Systems map (high-level)

```mermaid
flowchart LR
  A["Crypto Signals Ensemble<br/>Signal + Risk Metrics + Reproducibility"]
  B["DevTracker Governance<br/>Evidence Boundary + Audit Artifacts"]
  C["Agentic Decision Ledger (ADL)<br/>Decision Contracts + Commit-time Admissibility"]

  A --> B
  B --> C

  subgraph Pressures["Production pressures"]
    P1["Uncertainty & cost of error"] --> A
    P2["Change velocity & organizational amnesia"] --> B
    P3["Auditability, turnover, drift"] --> C
  end
```

## The hook (what breaks in real organizations)

Agentic systems fail when:
- change ships without admissibility,
- automation overwrites meaning (semantics),
- evidence is missing when incidents happen,
- responsibility is ambiguous (“who approved this?”).

> **Thesis:** Governance is not bureaucracy — it is admission control for change.

---

## What survives incidents (and why this exists)

Most systems optimize for *shipping*.  
This portfolio optimizes for what happens **two weeks after something breaks**.

It shows:
- how decisions remain attributable after turnover,
- how evidence stays verifiable after context is lost,
- how governance scales without relying on “the person who remembers”.

This is not about preventing all failures —  
it is about making failures *defensible, reconstructible, and learnable*.

---

## What is actually senior here (signals that matter)

This portfolio is optimized for concerns that appear in Staff / Principal / Architect loops:

- **Boundaries:** who owns semantics vs who writes evidence.
- **Failure modes:** post-incident defensibility, drift, turnover survivability.
- **Trade-offs:** commit-time friction to reduce forensic cost later.
- **Non-goals:** refusal to ship “magic autonomy” without controls.
- **Integration realism:** CI gates and artifact retention as part of delivery.

See:
- `docs/04_ARCHITECTURE_AND_INNOVATION.md`
- `docs/05_THREAT_MODEL.md`
- `docs/07_INTEGRATION_PATTERNS.md`

---

## How to evaluate (fast)

Start here:
1) `docs/01_HIRING_MANAGER_TLDR.md` (≈ 90 seconds)
2) `docs/02_15MIN_EVAL_PLAYBOOK.md` (exact route)
3) `docs/08_EVIDENCE_PACK.md` (clickable proof)

If you only click one thing:  
**Open `docs/08_EVIDENCE_PACK.md` and follow the pointers to real artifacts.**

- Decision contracts enforced in CI (demo) → `docs/decision_contracts_in_ci.md`

---

## Role fit (explicit)

This portfolio is relevant if you care about:

- admission control over change, not just execution,
- AI systems that must survive audit, turnover, and time,
- governance that produces evidence, not ceremonies.

Typical titles:
- AI Governance Architect
- Responsible AI Architect
- AI / Model Risk Architect
- Agentic Systems Architect
- Staff / Principal Platform Engineer (AI control-plane)


See:
- `docs/03_SYSTEMS_MAP.md`
- `docs/04_ARCHITECTURE_AND_INNOVATION.md`

---

## Non-goals (to prevent tool sprawl)

- This portfolio is not a full MLOps suite.
- DevTracker is not a project management replacement.
- ADL is not a workflow engine; it is an admissibility layer.
- Observability alone is not governance.

---

## How to use this in an interview

Ask:
- What change would you block, and why?
- Where does the decision live, and who owns it over time?
- What evidence would you want two weeks after an incident?

This repository exists so those questions have
**inspectable, deterministic, non-hand-wavy answers**.

If those answers matter in your organization,
this work is relevant.
