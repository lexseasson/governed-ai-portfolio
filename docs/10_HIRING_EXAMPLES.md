# Hiring Examples — Governed Change Capsules (v0.1)

These capsules are designed for Staff/Principal/Architect evaluation loops.
They show governance as a **control plane**: admission control, audit-grade artifacts, and deterministic reasoning about change.

Each capsule is intentionally:
- **Deterministic**: evaluated from diff + route + contract posture.
- **Auditable**: produces inspectable outputs (records, trail, stewardship summaries).
- **Transferable**: patterns apply across orgs, stacks, and CI systems.

---

## Capsule 1 — Docs-only Install Posture (ultra minimal adoption)

**What it proves**
A team can adopt governance with near-zero friction while still emitting audit-quality evidence.

**Primary design claim**
“Adoption posture” must be separable from “governance evolution”.  
Docs-only is an on-ramp, not an end-state.

**Read**
- `docs/examples/01_INSTALL_POSTURE.md`

---

## Capsule 2 — Product Posture (bounded authority across docs/examples/scripts)

**What it proves**
Bounded authority is only meaningful when it constrains real product surfaces (scripts/examples/docs), and drift is measured rather than argued.

**Primary design claim**
A governed repo should allow iteration on product narratives and demos while preventing silent expansion into enforcement surfaces.

**Read**
- `docs/examples/02_PRODUCT_POSTURE.md`

---

## Capsule 3 — Governance Evolution (meta-governance / constitutional posture)

**What it proves**
The governance layer governs itself: changes to enforcement are treated as constitutional risk, routed to stricter contracts, and recorded with audit-grade determinism.

**Primary design claim**
Control planes fail when they can be changed quietly by the same team that “owns” enforcement.

**Read**
- `docs/examples/03_GOVERNANCE_EVOLUTION.md`

---

## 7-minute evaluation route (recommended)

1) Capsule 1 (2 min): adoption posture and minimal friction.
2) Capsule 2 (3 min): bounded authority + drift + pressure telemetry.
3) Capsule 3 (2 min): constitutional self-governance and audit trail thinking.

If this feels “obvious”, that is the point: governance should be boring, deterministic, and auditable.
