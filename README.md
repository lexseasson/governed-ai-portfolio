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
- A fast path to evaluate real-world governance thinking.

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

The three anchor repositories:
1) **Crypto Signals Ensemble** — signal extraction and risk under uncertainty  
2) **DevTracker Governance** — governance as admission control for change; evidence boundary  
3) **Agentic Decision Ledger (ADL)** — decision contracts and commit-time admissibility (**Decision ≠ Log**)

Repositories:
- Crypto Signals Ensemble  
  https://github.com/lexseasson/crypto_signals_ensemble
- DevTracker Governance  
  https://github.com/lexseasson/devtracker-governance
- Agentic Decision Ledger (ADL)  
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

The hook (what breaks in real orgs)

Agentic systems fail when:

change ships without admissibility,

automation overwrites meaning (semantics),

evidence is missing when incidents happen,

responsibility is ambiguous (“who approved this?”).

Thesis: Governance is not bureaucracy — it is admission control for change.

What is actually “senior” here (signals that matter)

This portfolio is optimized for concerns that appear in Staff / Principal / Architect loops:

Boundaries: who owns semantics vs who writes evidence.

Failure modes: post-incident defensibility, drift, turnover survivability.

Trade-offs: commit-time friction to reduce forensic cost later.

Non-goals: refusal to ship “magic autonomy” without controls.

Integration realism: CI gates and artifact retention as part of delivery.

See:

docs/04_ARCHITECTURE_AND_INNOVATION.md

docs/05_THREAT_MODEL.md

docs/07_INTEGRATION_PATTERNS.md

How to evaluate (fast)

Start here:

docs/01_HIRING_MANAGER_TLDR.md (≈ 90 seconds)

docs/02_15MIN_EVAL_PLAYBOOK.md (exact route)

docs/08_EVIDENCE_PACK.md (clickable proof)

If you only click one thing:

Open docs/08_EVIDENCE_PACK.md and follow the pointers to real artifacts.

Role fit (explicit)

AI Governance Architect

Responsible AI Architect

AI Risk Management / Model Risk AI

LLM / Agentic Systems Architect

Staff / Principal Platform Engineer (AI control-plane)

See:

docs/03_SYSTEMS_MAP.md

docs/04_ARCHITECTURE_AND_INNOVATION.md

Non-goals (to prevent tool-sprawl)

This portfolio is not a full MLOps suite.

DevTracker is not a project management replacement.

ADL is not a workflow engine; it is an admissibility layer.

Observability alone is not governance.