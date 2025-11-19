# Lexicographic Constraint Optimization (LCO)
### A Unified Framework for Hierarchical Problem Solving  
**Author:** Antonios Valamontes  
**Institution:** Kapodistrian Academy of Science  
**License:** CC BY-NC 4.0

---

## What This Repository Is About

This repository contains the full source code, reference implementation, and LaTeX manuscript for the research framework **Lexicographic Constraint Optimization (LCO)**.

LCO is a general-purpose mathematical and computational method for solving problems where **objectives must be satisfied in strict priority order**, not blended into a single scalar.  
Where classical optimization asks *"minimize everything at once"*, LCO asks:

> **"What must be satisfied first?"**

This hierarchical perspective makes certain problems solvable that fail under traditional scalar optimization.

The repository includes **working Python code**, **LaTeX source**, and **algorithmic templates** for applying LCO to mathematics, physics, biology, cognitive modeling, and computational systems.

---

## Contents of This Repository

This repository is structured into three real components:

### 1. `src/` — **Actual Python Code**

Contains reference implementations:

- `lco.py` — The universal LCO solver  
  - Takes a list of objective functions `[L1, L2, ...]`
  - Solves them in strict lexicographic order  
  - Returns the highest-tier feasible solution

- `algorithms/` — Algorithmic templates  
  - Lexicographic descent  
  - Tier-by-tier constraint filtering  
  - LCO-style search procedures

- `examples/` — Example problems  
  - Simple mathematical demonstrations  
  - Multi-tier constraint systems  
  - Educational/clinical tier structures  

This is **real working code**, not pseudocode.

---

### 2. `tex/` — **The Full LaTeX Book**

This folder contains the full manuscript of the book:

**_“Lexicographic Constraint Optimization: The Hidden Order of Everything”_**

Included:

- `main.tex` — Entire book  
- `chapters/` — Each chapter split into structured TeX files  
- `images/` — Figures referenced in the manuscript  
- All mathematics, proofs, algorithms, and cross-domain applications

The LaTeX builds into a full academic monograph.

---

### 3. `releases/` — **Compiled PDF**

Contains:

- `LCO_Codex_v1.pdf` — Final compiled book version  
- Future versions will be added with semantic versioning

---

## How to Use the Python Code

Example:

```python
from lco import LCO

def L1(x): return abs(x - 5)     # Tier 1
def L2(x): return x % 2          # Tier 2
def L3(x): return (x - int(x))**2  # Tier 3

solver = LCO([L1, L2, L3])
solution = solver.solve(0)

print("Solution:", solution)
