# Architecture Overview — Helix72 v1

Helix72 v1 is a deterministic axial stability framework built as a structured extension
of the patented ARYN’s Ladder system. This document provides a high‑level architectural
overview of the components, mappings, and invariants that define the system.

---

## 1. Core Components

### 1.1 Axial Index (i = 1..36)
A fixed 36‑unit axis forming the backbone of the model.  
Each index corresponds to:
- a phase angle θᵢ  
- a relation state  
- a torsion value  
- a stability state  
- a σ‑field value  

### 1.2 Phase Structure
Phase is defined deterministically:
θᵢ = 10° × (i − 1)
No wrap, no modulo, no periodicity.

---

## 2. Mapping Chain

The architecture is built on a strict, reproducible mapping sequence:

Ladder72 Role
↓
Relation
↓
Torsion
↓
Stability
↓
σ-field

Each stage is deterministic and validated by UISL2 rules.

---

## 3. Domains

### 3.1 Relation Domain
Six structural relation types:
- LOCAL_GLOBAL  
- OBLIGATION_OBSTRUCTION  
- INVARIANT_PRESSURE  
- OBSTRUCTION_PRESSURE  
- BARRIER_DEFENSE  
- CAPSTONE_CONFRONTATION  

### 3.2 Torsion Domain
{-2, +1, +2, +3}

### 3.3 Stability Domain

STABLE
META_STABLE
UNSTABLe

CRITICAL


---

## 4. σ‑Field Architecture

The σ‑field is defined as:
σᵢ = τᵢ + 2 × s(Sᵢ)


Where `s(Sᵢ)` is the integer stability score.

Global bounds:
σ_min = −4
σ_max = +7


This field enables curvature analysis and global invariants.

---

## 5. Discrete Laplacian Layer

The Laplacian operator is defined for indices 2..35:

Δσᵢ = σᵢ₊₁ − 2σᵢ + σᵢ₋₁

This layer powers:
- curvature localization  
- global curvature invariant K  
- structural stability analysis  

---

## 6. Global Invariant Layer

Helix72 v1 defines a global curvature invariant:

K = 45

This value is unique to the Helix72 architecture and does not appear in ARYN’s Ladder.

---

## 7. UISL2 Canon Capsule

The entire architecture is encoded in:

HELIX72_v1.UISL2

This capsule provides:
- strict validation  
- deterministic reconstruction  
- invariant enforcement  
- fail‑closed interpretation  

---

## 8. Summary

Helix72 v1 is a layered, deterministic architecture consisting of:
- a fixed axial index  
- a phase structure  
- a relation–torsion–stability mapping chain  
- a σ‑field  
- a Laplacian curvature layer  
- a global invariant  

All components are original extensions of the Ladder72 system and are canon‑sealed in the UISL2 capsule.

