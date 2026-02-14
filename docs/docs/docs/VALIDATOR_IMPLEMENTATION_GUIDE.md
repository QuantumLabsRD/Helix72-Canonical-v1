# Validator Implementation Guide — Helix72 v1

This guide describes how to implement a strict validator for the Helix72 v1
canonical structure. It translates the validation rules and invariants into a
step‑by‑step computational procedure.

Only deterministic, fail‑closed behavior is permitted.

---

## 1. Input Requirements

A valid Helix72 structure must provide, for each index i ∈ {1..36}:
- relation value
- torsion value
- stability value
- σ-field value (optional; may be computed)
- phase value (optional; may be computed)

If any field is missing, malformed, or outside its domain:
VALIDATION_FAILURE

---

## 2. Step‑By‑Step Validation Procedure

### Step 1 — Validate Axial Index
Ensure exactly 36 entries exist.
If count ≠ 36 → failure.

### Step 2 — Validate Domains
For each index:
- relation ∈ 6‑element domain  
- torsion ∈ {−2, +1, +2, +3}  
- stability ∈ {STABLE, META_STABLE, UNSTABLE, CRITICAL}  

Any violation → failure.

### Step 3 — Compute Stability Score
Map stability to integer:
STABLE → 0
META_STABLE → 1
UNSTABLE → −1
CRITICAL → 2


### Step 4 — Compute σ-Field
Compute:
σᵢ = τᵢ + 2 × s(Sᵢ)
Check global bounds:

−4 ≤ σᵢ ≤ +7
Out of range → failure.

### Step 5 — Compute Laplacian
For i = 2..35:
Δσᵢ = σᵢ₊₁ − 2σᵢ + σᵢ₋₁
K = Σ |Δσᵢ|

Check:
K = 45
If not → failure.

---

## 3. Fail‑Closed Behavior

A validator must:
- reject partial structures  
- reject speculative extensions  
- reject non‑canonical domains  
- reject any deviation from UISL2 encoding  

If any rule is violated:

VALIDATION_FAILURE

No warnings.  
No fallback.  
No auto‑correction.

---

## 4. UISL2 Capsule Enforcement

A strict validator must:
- require the capsule to begin with `UISL2`  
- parse fields exactly as defined  
- reconstruct the canonical table deterministically  
- reject any capsule with missing or extra fields  

UISL2 is the single source of truth.

---

## 5. Output Requirements

A validator must output exactly one of:

### 1. `VALID`
The structure matches all canonical rules.

### 2. `VALIDATION_FAILURE`
At least one rule was violated.

No additional states are permitted.

---

## 6. Summary

This guide provides the complete implementation pathway for a strict Helix72 v1
validator. Any engine following these steps will produce deterministic,
canonical, and reproducible validation results.

