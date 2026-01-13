# Hiring Examples — 3 Governed Change Capsules

These three capsules are intentionally small and inspectable.  
They demonstrate **admission control for agentic change** under three realistic postures:

1) **Install posture** — docs-only, ultra-minimal adoption  
2) **Product posture** — bounded authority for day-to-day change  
3) **Governance evolution** — self-governing control plane, no implicit exemptions

> Design principle: **Governance must be cheaper than forensics.**  
> Each capsule links to deterministic artifacts and a reproducible run path.

---

## How to evaluate (fast)

1) Read each capsule README (3–5 minutes total).  
2) For proof, run the corresponding demo in **Agentic Decision Ledger (ADL)**:
   - Windows runbook: `agentic-decision-ledger/docs/runbook_windows.md`
   - Linux runbook: `agentic-decision-ledger/docs/runbook_linux.md`
   - Demo runner (Windows): `agentic-decision-ledger/scripts/demo_all.cmd`

Shared references:
- Expected outputs: `docs/examples/_shared/ARTIFACTS_EXPECTED.md`
- Evaluation checklist: `docs/examples/_shared/EVAL_CHECKLIST.md`

---

## Capsule 1 — Install posture (ultra minimal)

**Goal**: adopt governance without touching workflows or execution plane.  
**Contract**: `DC-INSTALL-DEMO-001`.

Read: `docs/examples/01_Install_Posture/README.md`

---

## Capsule 2 — Product posture (bounded authority)

**Goal**: allow real work while preventing authority creep.  
**Contract**: `DC-2026-001`.

Read: `docs/examples/02_Product_Posture/README.md`

---

## Capsule 3 — Governance evolution (self-governance)

**Goal**: when the control plane changes, require constitutional-level governance.  
**Contract**: `DC-REPO-001`.

Read: `docs/examples/03_Governance_Evolution/README.md`

---

## Why these three matter (architect-level signal)

Most orgs fail here:

- They can’t **introduce** governance without breaking dev flow. (Capsule 1)
- They can’t **scale** governance as velocity increases. (Capsule 2)
- They can’t **govern the governance** (meta-drift, silent weakening). (Capsule 3)

These capsules show the escalation path from adoption → operations → constitution.
