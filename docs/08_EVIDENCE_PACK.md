# Evidence pack (click this, it proves that)

> Rule: no claims without pointers to inspectable artifacts.

## 1) Crypto Signals Ensemble
Repo: https://github.com/lexseasson/crypto_signals_ensemble

What it proves:
- quantitative decision baseline
- modularity (data/logic/dashboard)
- risk framing (Sharpe/Sortino/drawdown etc.)

Where to click (examples):
- `logic_layer/risk_metrics.py`
- `logic_layer/offline_training.py`
- `dashboard/`

---

## 2) DevTracker Governance
Repo: https://github.com/lexseasson/devtracker-governance

What it proves:
- governance artifacts exist (not just “documentation”)
- evidence boundary: automation proposes; humans approve semantics

Where to click (expected folders):
- `reports/` (audit markdown)
- `artifacts/` (json snapshots / proposals)
- any demo folder under `examples/` if present

What to look for:
- explicit “proposed updates” as reviewable deltas (not silent overwrites)
- audit report readability

---

## 3) Agentic Decision Ledger (ADL)
Repo: https://github.com/lexseasson/agentic-decision-ledger

What it proves:
- Decision ≠ Log
- decision contracts
- admissibility layer mindset (commit-time)

Where to click (target structure):
- `decisions/contracts/`
- `integrations/` (CI)
- `examples/` (demo)

If something is missing today:
- see `09_ADL_BOOM_CHECKLIST.md` — this is the exact closure plan.
