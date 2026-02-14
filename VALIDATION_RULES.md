# Validation Rules — Helix72 v1

This document defines the strict validation rules required to interpret,
reconstruct, or compute over the Helix72 v1 canonical structure. These rules
ensure deterministic behavior and prevent drift, reinterpretation, or
non‑canonical extensions.

---

## 1. Axial Index Validation

### Rule 1.1 — Fixed Range
The axial index must satisfy:
```
i ∈ {1..36}
```
No additional indices may be added or removed.

### Rule 1.2 — Phase Determinism
Phase must be computed as:
```
θᵢ = 10° × (i − 1)
```
No modulo, wrap‑around, or periodicity is permitted.

---

## 2. Domain Validation

### Rule 2.1 — Relation Domain
Relation must be one of:
```
LOCAL_GLOBAL
OBLIGATION_OBSTRUCTION
INVARIANT_PRESSURE
OBSTRUCTION_PRESSURE
BARRIER_DEFENSE
CAPSTONE_CONFRONTATION
```

### Rule 2.2 — Torsion Domain
Torsion must be one of:
```
{-2, +1, +2, +3}
```

### Rule 2.3 — Stability Domain
Stability must be one of:
```
STABLE
META_STABLE
UNSTABLE
CRITICAL
```

---

## 3. σ‑Field Validation

### Rule 3.1 — Stability Score Mapping
Stability must map to integers as:
```
STABLE → 0
META_STABLE → 1
UNSTABLE → −1
CRITICAL → 2
```

### Rule 3.2 — σ‑Field Definition
σ must be computed as:
```
σᵢ = τᵢ + 2 × s(Sᵢ)
```

### Rule 3.3 — Global Bounds
σ must satisfy:
```
−4 ≤ σᵢ ≤ +7
```

---

## 4. Laplacian Validation

### Rule 4.1 — Definition
For indices 2..35:
```
Δσᵢ = σᵢ₊₁ − 2σᵢ + σᵢ₋₁
```

### Rule 4.2 — Boundary Behavior
Indices 1 and 36 are excluded from Laplacian computation.

### Rule 4.3 — Curvature Localization
Curvature exists at i iff:
```
Δσᵢ ≠ 0
```

---

## 5. Global Invariant Validation

### Rule 5.1 — Total Curvature
The global invariant must satisfy:
```
K = Σ |Δσᵢ|  for i = 2..35
```

### Rule 5.2 — Canonical Value
For Helix72 v1:
```
K = 45
```

---

## 6. UISL2 Capsule Validation

### Rule 6.1 — Strict Mode
The capsule must begin with:
```
UISL2
```

### Rule 6.2 — Deterministic Reconstruction
All fields must reconstruct the canonical table exactly.

### Rule 6.3 — Fail‑Closed Behavior
Any deviation from these rules must result in:
```
VALIDATION_FAILURE
```

---

## Summary
These rules define the complete validator specification for Helix72 v1.  
Any engine, parser, or computational system must adhere to them exactly.
