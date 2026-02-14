# Helix72 v1 — Structural Diagram

This diagram provides a high‑level visual overview of the Helix72 v1 architecture,
showing how each layer connects to the next in the deterministic mapping chain.

┌──────────────────────────────┐
│        AXIAL INDEX (i)       │
│          i = 1..36           │
└───────────────┬──────────────┘
│
▼
┌──────────────────────────────┐
│        PHASE LAYER           │
│     θᵢ = 10° × (i − 1)       │
└───────────────┬──────────────┘
│
▼
┌──────────────────────────────┐
│       RELATION DOMAIN        │
│  (6 canonical relation types)│
└───────────────┬──────────────┘
│
▼
┌──────────────────────────────┐
│        TORSION DOMAIN        │
│       {−2, +1, +2, +3}       │
└───────────────┬──────────────┘
│
▼
┌──────────────────────────────┐
│       STABILITY DOMAIN       │
│ STABLE / META / UNSTABLE /   │
│           CRITICAL           │
└───────────────┬──────────────┘
│
▼
┌──────────────────────────────┐
│         σ‑FIELD LAYER        │
│   σᵢ = τᵢ + 2 × s(Sᵢ)        │
│   Range: −4 ≤ σᵢ ≤ +7        │
└───────────────┬──────────────┘
│
▼
┌──────────────────────────────┐
│     LAPLACIAN OPERATOR       │
│ Δσᵢ = σᵢ₊₁ − 2σᵢ + σᵢ₋₁       │
│     (i = 2..35 only)         │
└───────────────┬──────────────┘
│
▼
┌──────────────────────────────┐
│     GLOBAL INVARIANT K       │
│     K = Σ |Δσᵢ| = 45         │
└──────────────────────────────┘


---ASCII diagram of the Helix72 v1 architecture
