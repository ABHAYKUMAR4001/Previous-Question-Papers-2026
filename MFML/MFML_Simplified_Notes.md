# MFML — Simplified Consolidated Notes

> **One-stop revision guide.** Every topic from both Learning Notes files, broken into the simplest possible language with key formulas and exam tricks.

---

## Table of Contents

1. [Vector Spaces & Linear Independence](#1-vector-spaces--linear-independence)
2. [Eigenvalues & Eigenvectors](#2-eigenvalues--eigenvectors)
3. [PCA & Dimensionality Reduction](#3-pca--dimensionality-reduction)
4. [Gradients, Jacobians & Chain Rule](#4-gradients-jacobians--chain-rule)
5. [Inner Products, Norms & Distances](#5-inner-products-norms--distances)
6. [Critical Points & Hessian](#6-critical-points--hessian)
7. [Gradient Descent & Optimization](#7-gradient-descent--optimization)
8. [Convexity](#8-convexity)
9. [Lagrange Multipliers](#9-lagrange-multipliers)
10. [KKT & Duality](#10-kkt--duality)
11. [SVD (Singular Value Decomposition)](#11-svd-singular-value-decomposition)
12. [SVM & Kernel Methods](#12-svm--kernel-methods)
13. [Power Method](#13-power-method)
14. [Complex Eigenvalues](#14-complex-eigenvalues)
15. [Null Space & Rank](#15-null-space--rank)
16. [Master Formula Sheet](#16-master-formula-sheet)

---

# 1. Vector Spaces & Linear Independence

## What You Need to Know (Plain English)

| Concept | One-Line Meaning |
|---------|-----------------|
| Linear Combination | Mixing vectors with scalar weights: `a·v₁ + b·v₂` |
| Span | All vectors you can create by combining a set of vectors |
| Linear Independence | No vector in the set is "extra" (can't be made from others) |
| Basis | Minimum set of vectors that spans the whole space |
| Dimension | How many vectors are in a basis |
| Subspace | A smaller space living inside a bigger one |
| Null Space | All vectors x where Ax = 0 |

---

## Key Ideas Simplified

### Linear Combination
You have vectors v₁ and v₂. Pick any numbers a, b. Then `a·v₁ + b·v₂` is a linear combination.

**Example:** v₁ = (1,0), v₂ = (0,1) → 3v₁ + 2v₂ = (3,2)

### Span
Span = "what can these vectors reach?"

- One vector spans a **line**
- Two non-parallel vectors in 2D span the **whole plane**

### Linear Independence — The Test

Set up: `a₁v₁ + a₂v₂ + ... + aₙvₙ = 0`

- If the ONLY solution is all a's = 0 → **Independent**
- If you can find non-zero a's → **Dependent** (some vector is redundant)

### Basis = Independent + Spans Everything

### Dimension = Number of vectors in a basis

---

## Exam Patterns

| Question Type | What To Do |
|--------------|-----------|
| "Prove vectors are independent" | Set `α₁v₁ + ... = 0`, show all α = 0 |
| "Show vectors are dependent" | Find non-zero coefficients that give zero |
| "Prove span(A) = span(B)" | Show A ⊆ B AND B ⊆ A |
| "Is this a subspace?" | Check: contains zero? closed under addition and scaling? |
| "Is this a basis?" | Check BOTH span AND independence |
| "Find dimension" | Find a basis, count it |

---

## Important Exam Example: Skew-Symmetric Matrices

M = {2×2 matrices where A = -Aᵀ}

Every such matrix looks like:
```
|  0   b |
| -b   0 |
```

- **Basis:** One matrix `[[0,1],[-1,0]]`
- **Dimension:** 1

**Trap:** Two matrices like `[[0,1],[-1,0]]` and `[[0,2],[-2,0]]` are NOT a basis because second = 2 × first (dependent!)

---

## Null Space Quick Rules

- Column relation → null space vector
- `C₂ = 3C₁` means `[1, -3, 0, ...]ᵀ` is in null space
- `C₁ = C₂ + C₃` means `[1, -1, -1, 0, ...]ᵀ` is in null space

---

## Rank-Nullity Theorem

> **rank(A) + nullity(A) = number of columns**

- Rank = number of independent columns = number of pivots in RREF
- Nullity = dimension of null space = number of free variables

---

## RREF Facts

- **RREF is unique** (different row operations, same final answer)
- **REF is NOT unique**
- Pivot columns in RREF → take those columns from the ORIGINAL matrix as column-space basis

---

## General Solution of Ax = b

> **x = xₚ + (any null space vector)**

Steps:
1. Find one particular solution xₚ
2. Find null space basis from column relations
3. General solution = xₚ + s·n₁ + t·n₂ + ...

---

## Does Dimension Depend on the Field?

**Yes!**

- C over C: basis = {1}, dim = 1
- C over R: basis = {1, i}, dim = 2

Same set, different allowed scalars → different dimension.

---

# 2. Eigenvalues & Eigenvectors

## Core Idea

> **Av = λv** → The matrix only stretches/flips v, doesn't change its direction.

- v = eigenvector (must be non-zero)
- λ = eigenvalue (can be anything, even 0 or complex)

## How to Find Eigenvalues

Solve: **det(A - λI) = 0** (characteristic equation)

## How to Find Eigenvectors

For each λ, solve: **(A - λI)v = 0**

The solution space is called the **eigenspace**: E_λ = N(A - λI)

---

## Shortcuts

| Situation | Shortcut |
|-----------|----------|
| Triangular matrix | Eigenvalues = diagonal entries |
| Any matrix | trace = sum of all eigenvalues |
| Any matrix | det = product of all eigenvalues |
| Matrix power Aᵏ | Eigenvalues become λᵏ |

---

## Multiplicities

- **Algebraic multiplicity** = how many times λ appears as a root
- **Geometric multiplicity** = dim of eigenspace = dim N(A-λI)

Rule: 1 ≤ geometric ≤ algebraic

## Diagonalizability

A matrix is diagonalizable (A = PDP⁻¹) if:
- It has n independent eigenvectors, OR equivalently
- geometric = algebraic for every eigenvalue

**Quick check:** n distinct eigenvalues → always diagonalizable

**Symmetric matrices** are ALWAYS diagonalizable (even with repeated eigenvalues)

---

## Orthogonality of Eigenvectors

- Distinct eigenvalues → eigenvectors are **independent** (always)
- Distinct eigenvalues → eigenvectors are **orthogonal** (ONLY if matrix is symmetric)

---

## Exam Example: 4×4 Lower Triangular

```
A = | -2   0   0   0 |
    | -1   3   0   0 |
    |  0  -1  -1   0 |
    |  1   1   0   5 |
```

Eigenvalues (read diagonal): -2, 3, -1, 5

For largest eigenvalue λ=5: solve (A-5I)v = 0 → v = t(0,0,0,1)ᵀ

---

# 3. PCA & Dimensionality Reduction

## What PCA Does (Plain English)

You have data with many features. PCA finds the directions where data varies the most and lets you keep only a few important directions.

> **Goal: Reduce dimensions while keeping maximum information (variance)**

---

## PCA Pipeline (Memorize This)

1. **Center** the data (subtract mean)
2. **Compute** covariance matrix C
3. **Find** eigenvalues and eigenvectors of C
4. **Sort** eigenvalues largest → smallest
5. **Pick** top k eigenvectors (these are your principal components)
6. **Project** data onto those directions
7. **Reconstruct** if needed

---

## Key Facts

| Concept | Formula/Rule |
|---------|-------------|
| PC1 (first principal component) | Eigenvector with LARGEST eigenvalue |
| Variance captured by PCk | The k-th eigenvalue |
| Explained variance ratio | (sum of top k eigenvalues) / (sum of all eigenvalues) |
| Projection of point x | z = v₁ᵀx (scalar coordinate along PC1) |
| Reconstruction | x̂ = μ + v₁·z |
| Covariance matrix is | Symmetric → eigenvectors are orthogonal |

---

## Exam Pattern: How Many PCs for 95%/99%?

Given eigenvalues: 12, 6.8, 3.5, 1, 0.02, 0.01 (total = 23.33)

- Top 1: 12/23.33 = 51.4%
- Top 2: 18.8/23.33 = 80.6%
- Top 3: 22.3/23.33 = **95.6%** ← enough for 95%
- Top 4: 23.3/23.33 = **99.9%** ← enough for 99%

---

## High-Dimensional PCA Trick (D >> N)

When features D = 1024 but samples N = 20:

- DON'T solve the 1024×1024 eigenvalue problem
- DO solve the small 20×20 problem: **XᵀX v = λv**
- RECOVER the big eigenvector: **u = Xv / √λ**

**Why it works:** If XᵀXv = λv, then multiply by X: XXᵀ(Xv) = λ(Xv)

So Xv is an eigenvector of the big matrix with the same eigenvalue!

---

## Feature Scaling Effect on PCA

- Same scale on all features (x' = αx): eigenvectors DON'T change, eigenvalues × α²
- Different scales (D = diag(α₁,...,αD)): eigenvectors CHANGE
- New covariance: C' = DCD, entry-wise: C'ᵢⱼ = αᵢ·αⱼ·Cᵢⱼ (computable in O(D²))

---

# 4. Gradients, Jacobians & Chain Rule

## Must-Know Gradient Formulas

| Function | Gradient |
|----------|----------|
| ‖Ax - b‖² | 2Aᵀ(Ax - b) |
| xᵀQx (Q symmetric) | 2Qx |
| cᵀx | c |
| σ(z) = 1/(1+e⁻ᶻ) | σ(z)(1-σ(z)) |
| tanh(z) | 1 - tanh²(z) |

---

## Computation Graph (Chain Rule)

For a neural network-style chain:
- Work **backward** from the loss
- At each node: local derivative × incoming gradient

**Example chain:**
```
p = w₁ᵀx + b₁
q = σ(p)
r = w₂ᵀx + b₂
s = tanh(r)
m = q + s
L = ½(m - m*)²
```

Backward:
- ∂L/∂m = m - m*
- ∂L/∂q = m - m* (passes through addition)
- ∂L/∂p = (m - m*) · σ'(p) = (m - m*) · q(1-q)
- ∂L/∂r = (m - m*) · (1 - s²)

---

## Regularized Loss Gradient

For `L = (1/2p)‖y - β‖² + λ‖Wβ‖²`:

> **∇L = -(1/p)(y - β) + 2λWᵀWβ**

---

# 5. Inner Products, Norms & Distances

## Matrix-Weighted Inner Product

> **⟨x, y⟩_A = xᵀAy**

This is valid when A is:
1. Symmetric (A = Aᵀ)
2. Positive definite (all eigenvalues > 0)

## A-Orthogonality

x and y are A-orthogonal when **xᵀAy = 0** (not the same as regular xᵀy = 0!)

## L1 Distance is a Valid Metric

d(x,y) = Σ|xᵢ - yᵢ| satisfies:
- Non-negative ✓
- Zero iff x = y ✓
- Symmetric ✓
- Triangle inequality ✓ (follows from |a+b| ≤ |a|+|b|)

## Projection with Trace Constraint

Closest trace-zero matrix to A = diag(a,b): subtract mean of diagonal from each diagonal entry.

Example: A = diag(1,2), mean = 1.5 → M = diag(-0.5, 0.5)

---

# 6. Critical Points & Hessian

## Finding Critical Points

Solve: **∇f = 0** (all partial derivatives = 0)

## Classifying (2D case)

Hessian matrix:
```
H = | f_xx   f_xy |
    | f_xy   f_yy |
```

Compute D = f_xx · f_yy - (f_xy)²

| D | f_xx | Result |
|---|------|--------|
| D > 0 | > 0 | Local minimum |
| D > 0 | < 0 | Local maximum |
| D < 0 | any | Saddle point |
| D = 0 | any | Inconclusive |

---

## Radial Function Pattern

For f(x,y) = (x²+y²)·e^(-(x²+y²)):
- Let r² = x² + y²
- Critical at origin (minimum) and on circle r=1 (maximum ring)

---

# 7. Gradient Descent & Optimization

## Basic Update Rule

> **x_{k+1} = x_k - α·∇f(x_k)**

- α = learning rate (step size)
- Too big → diverge
- Too small → slow

## Optimal Step Size (Quadratic Functions)

For direction d = -∇f and Hessian H:

> **α* = (gᵀg) / (gᵀHg)** where g = ∇f

## Momentum

> **z_{k+1} = z_k - α∇f(z_k) + β(z_k - z_{k-1})**

β carries previous movement forward (like a ball rolling downhill).

## Exponential Moving Average (EMA)

> **a_t = γ·a_{t-1} + (1-γ)·g_t**

- γ near 1 → smooth, long memory
- γ near 0 → reacts fast to new gradients

## Nonconvex: Initialization Matters

- Different starting points can lead to different local minima
- Local maxima act as basin boundaries
- Sketch f'(x) sign to see which way gradient pushes

---

# 8. Convexity

## Convex Set

A set C is convex if any line segment between two points in C stays inside C:

> **θx + (1-θ)y ∈ C** for all x,y ∈ C and θ ∈ [0,1]

**Example:** {x : Ax = b} is convex (solution set of linear equations)

## Convex Function

f is convex if the line segment between any two points on the graph lies above the curve:

> **f(θx + (1-θ)y) ≤ θf(x) + (1-θ)f(y)**

**Key convex functions:**
- ‖x‖₁ (L1 norm)
- ‖x‖² (squared L2 norm)
- g(Ax + b) if g is convex (affine composition preserves convexity)

---

# 9. Lagrange Multipliers

## When to Use

Optimize f(x) subject to **equality** constraint h(x) = 0

## Method

1. Form Lagrangian: **L(x, λ) = f(x) + λ·h(x)**
2. Solve: **∇f + λ∇h = 0** AND **h(x) = 0**

## Common Exam Pattern: Closest Point to a Line

Minimize distance² (not distance!) subject to the line equation.

## Linear Objective + Linear Constraint Trap

min ax+by+cz subject to px+qy+rz = 0

- If (a,b,c) is NOT parallel to (p,q,r) → no finite minimum (unbounded)
- If (a,b,c) = λ(p,q,r) → minimum = 0 at every feasible point

---

# 10. KKT & Duality

## When to Use

Optimize f(x) subject to **inequality** constraints gᵢ(x) ≤ 0

## KKT Conditions (4 things to check)

1. **Primal feasibility:** gᵢ(x*) ≤ 0
2. **Dual feasibility:** λᵢ ≥ 0
3. **Stationarity:** ∇f + Σλᵢ∇gᵢ = 0
4. **Complementary slackness:** λᵢ · gᵢ(x*) = 0

> Slackness means: either the constraint is tight (gᵢ = 0) OR λᵢ = 0 (constraint doesn't matter)

## Dual Function

q(λ) = min_x L(x, λ)

- Weak duality: dual optimum ≤ primal optimum (always)
- Strong duality: equality (holds for convex problems with Slater's condition)

---

# 11. SVD (Singular Value Decomposition)

## The Decomposition

> **A = UΣVᵀ**

- U = left singular vectors (columns are orthonormal)
- Σ = diagonal matrix of singular values σ₁ ≥ σ₂ ≥ ... ≥ 0
- V = right singular vectors (columns are orthonormal)

## Key Relationships

| Formula | Meaning |
|---------|---------|
| AᵀA = VΣ²Vᵀ | V contains eigenvectors of AᵀA |
| AAᵀ = UΣ²Uᵀ | U contains eigenvectors of AAᵀ |
| Eigenvalues of AᵀA | σᵢ² |
| rank(A) | Number of non-zero singular values |
| ‖A‖²_F | σ₁² + σ₂² + ... = trace(AᵀA) |

## Why AᵀA and AAᵀ Share Nonzero Eigenvalues

If AᵀAv = λv (λ≠0), multiply by A → AAᵀ(Av) = λ(Av)

So Av is an eigenvector of AAᵀ with the same eigenvalue.

---

# 12. SVM & Kernel Methods

## Hard-Margin SVM (Linearly Separable Data)

**Primal:**
- Minimize: ½‖w‖²
- Subject to: yᵢ(wᵀxᵢ + b) ≥ 1

Decision boundary: wᵀx + b = 0

**Dual:**
- Maximize: Σαᵢ - ½ΣᵢΣⱼ αᵢαⱼyᵢyⱼ(xᵢᵀxⱼ)
- Subject to: αᵢ ≥ 0, Σαᵢyᵢ = 0
- Recover: w = Σαᵢyᵢxᵢ

Support vectors = points where αᵢ > 0 (they sit on the margin)

## Soft Margin (Noisy Data)

Minimize: ½‖w‖² + C·Σξᵢ

- **Large C** → strict fitting, can overfit noise
- **Small C** → tolerates errors, smoother margin, better for noisy data

## Kernel Trick

> **K(x, z) = φ(x)ᵀφ(z)**

Computes inner product in high-dimensional space WITHOUT actually computing φ.

**Kernel matrix:** Kᵢⱼ = K(xᵢ, xⱼ) — must be symmetric positive semidefinite.

## Hinge Loss

> **loss = max(0, 1 - y·f(x))**

- Correctly classified and far from boundary → 0 loss
- Near boundary or wrong → positive loss

## Adding a Training Point Can't Reduce Dual Max

New problem has one extra variable αₙ₊₁ ≥ 0. Setting it to 0 recovers the old problem. So the new feasible set contains the old one → max can only stay same or increase.

---

# 13. Power Method

## What It Does

Finds the **dominant eigenvalue** (largest |λ|) and its eigenvector.

## Algorithm

1. Start with random x₀
2. Compute x_{k+1} = Ax_k
3. Normalize x_{k+1}
4. Repeat until convergence

## When It Works

- A must have a **unique** dominant eigenvalue
- x₀ must have a **non-zero component** along the dominant eigenvector

## Exam Example

```
A = |1 2|
    |1 2|
```
Eigenvalues: 3 and 0. Dominant eigenvector: (1,1)ᵀ

**Trap:** If starting vector has zero component along (1,1), method can fail.

---

# 14. Complex Eigenvalues

## When They Appear

Real matrices can have complex eigenvalue **pairs** (always conjugate: a±bi)

## Exam Example

```
A = |3 -1  0|
    |1  3  0|
    |0  0  4|
```

Top-left 2×2 block: (3-λ)² + 1 = 0 → **λ = 3 ± i**

Third eigenvalue: **λ = 4** (from the diagonal)

Eigenvectors for complex eigenvalues are also complex:
- λ = 3+i → v = (1, -i, 0)ᵀ
- λ = 3-i → v = (1, i, 0)ᵀ
- λ = 4 → v = (0, 0, 1)ᵀ

---

# 15. Null Space & Rank

## Rank from a Formula

If matrix entries are `a_jk = j + k - 1`:

Columns: C_k = C₁ + (k-1)·**1** (where **1** = all-ones vector)

Every column is a combination of just C₁ and **1** → **rank = 2**

## Orthogonality Constraints = Null Space

If S = {x : Rᵢᵀx = 0 for all i}, stack rows into matrix A.

Then S = N(A). If A has full column rank → S = {0}.

## Rank of Matrices with Patterns

> If `a_jk = f(j) + g(k)`, look for ways to express all columns using few fixed vectors.

---

# 16. Master Formula Sheet

## Linear Algebra Core

```
rank + nullity = number of columns
Av = λv  →  det(A - λI) = 0
trace(A) = Σλᵢ
det(A) = Πλᵢ
Symmetric → orthogonally diagonalizable
RREF is unique; REF is not
```

## SVD / PCA

```
A = UΣVᵀ
AᵀA = VΣ²Vᵀ
AAᵀ = UΣ²Uᵀ
PC1 = eigenvector of covariance with largest eigenvalue
Explained variance = cumulative eigenvalues / total
Projection: z = Vᵀx
Reconstruction: x̂ = VVᵀx
High-dim trick: u = Xv/√λ
```

## Gradients

```
∇‖Ax-b‖² = 2Aᵀ(Ax-b)
∇(xᵀQx) = 2Qx  (Q symmetric)
σ'(z) = σ(z)(1-σ(z))
tanh'(z) = 1 - tanh²(z)
```

## Optimization

```
GD: x_{k+1} = x_k - α∇f
Exact line search: α* = (gᵀg)/(gᵀHg)
Lagrange: ∇f + λ∇h = 0
KKT: feasibility + dual feasibility + stationarity + complementary slackness
```

## SVM

```
Constraint: yᵢ(wᵀxᵢ + b) ≥ 1
Recovery: w = Σαᵢyᵢxᵢ
Kernel: K(x,z) = φ(x)ᵀφ(z)
Hinge loss: max(0, 1 - y·f(x))
```

---

## Quick Decision Guide for Exams

| You See... | Immediately Think... |
|-----------|---------------------|
| "Prove independent" | Set combination = 0, show trivial solution |
| "Find eigenvalues" | det(A-λI) = 0 |
| Triangular matrix | Eigenvalues = diagonal |
| "How many PCs for 95%?" | Cumulative eigenvalue sum |
| "Gradient of ‖Ax-b‖²" | 2Aᵀ(Ax-b) |
| "Minimize subject to h=0" | Lagrange multipliers |
| "Minimize subject to g≤0" | KKT conditions |
| "Is this convex?" | Check f(θx+(1-θ)y) ≤ θf(x)+(1-θ)f(y) |
| "Saddle/min/max?" | Hessian determinant test |
| "SVD connection" | AᵀA eigenvalues = σᵢ² |
| "Column dependence" | Null space vector |
| D >> N in PCA | Use XᵀX (small matrix) |
| Complex eigenvalues | Come in conjugate pairs for real matrices |

---

> **Recommended Use:** Read through once for understanding, then use the formula sheet and decision guide for quick exam revision. Practice with past papers under timed conditions.
