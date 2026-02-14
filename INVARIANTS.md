# Canonical Invariants — Helix72 v1

This document lists all invariants that must hold true for any valid Helix72 v1
structure. These invariants define the mathematical backbone of the system and
must never be altered.

---

## 1. Axial Invariants

### Invariant 1.1 — Fixed Length
The axial index must contain exactly 36 units.

### Invariant 1.2 — Phase Spacing
Phase spacing must be:
```
Δθ = 10°
```
for all adjacent indices.

---

## 2. Domain Invariants

### Invariant 2.1 — Relation Domain Closure
All relation values must belong to the 6‑element relation domain.

### Invariant 2.2 — Torsion Domain Closure
All torsion values must belong to:
```
{-2, +1, +2, +3}
```

### Invariant 2.3 — Stability Domain Closure
All stability values must belong to:
```
STABLE, META_STABLE, UNSTABLE, CRITICAL
```

---

## 3. σ‑Field Invariants

### Invariant 3.1 — Stability Score Mapping
The stability score mapping is fixed and immutable.

### Invariant 3.2 — σ‑Field Formula
σ must always satisfy:
```
σᵢ = τᵢ + 2 × s(Sᵢ)
```

### Invariant 3.3 — Global σ Bounds
σ must always remain within:
```
−4 ≤ σᵢ ≤ +7
```

---

## 4. Curvature Invariants

### Invariant 4.1 — Laplacian Definition
The discrete Laplacian must always be:
```
Δσᵢ = σᵢ₊₁ − 2σᵢ + σᵢ₋₁
```

### Invariant 4.2 — Curvature Localization
Curvature exists iff:
```
Δσᵢ ≠ 0
```

### Invariant 4.3 — Boundary Exclusion
Indices 1 and 36 are excluded from curvature computation.

---

## 5. Global Invariant

### Invariant 5.1 — Total Curvature
The global curvature invariant must satisfy:
```
K = Σ |Δσᵢ|
```

### Invariant 5.2 — Canonical Value
For Helix72 v1:
```
K = 45
```

This value is unique and must never change.

---

## 6. UISL2 Invariants

### Invariant 6.1 — Strict Header
The capsule must begin with:
```
UISL2
```

### Invariant 6.2 — Deterministic Reconstruction
All canonical values must reconstruct exactly from the UISL2 capsule.

### Invariant 6.3 — No Drift
Any deviation from canonical values invalidates the structure.

---

## Summary
These invariants define the unbreakable mathematical and structural truths of
Helix72 v1. They form the foundation for all future versions and computational
implementations.
