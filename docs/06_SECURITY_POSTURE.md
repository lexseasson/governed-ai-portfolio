
# Security posture (baseline, explicit)

> [!NOTE]
> Goal: explicit boundaries and hardening path — not “complete security” claims.

## Baseline posture
- No secrets committed to repo.
- Deterministic checks in CI wherever possible.
- Evidence artifacts are reviewable and retained.

## Hardening path (if deployed)
- Artifact signing / attestations (provenance)
- OIDC-based CI identity
- Least-privileged workflow permissions
- Immutable artifact storage (retention + integrity)
