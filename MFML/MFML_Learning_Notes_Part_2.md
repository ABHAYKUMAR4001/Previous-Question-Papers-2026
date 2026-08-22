# MFML Learning Notes — Part 2

> **Continuation of `MFML_Learning_Notes.md`**
>
> **Learning goal:** Concept → intuition → dimensions → derivation → exam method → memory shortcut.

---

# Topic 3 — PCA & Dimensionality Reduction (Continued)

## 12. PCA When the Feature Dimension is Very Large

A common PCA situation is:

- **D = number of features = 1024**
- **N = number of samples = 20**

So we have **very high-dimensional data but only a small number of samples**.

The important exam question is:

> **Do we really need to solve an eigenvalue problem involving a 1024 × 1024 matrix?**

The answer is **No**.

We can solve a much smaller **20 × 20** eigenvalue problem and then recover the required principal directions in the original 1024-dimensional feature space.

This is often called the **dual-space PCA method** or the **PCA kernel-trick idea**.

---

## 13. First Fix the Data-Matrix Convention

Let the centered data matrix be:

> **X ∈ R^(D×N)**

where:

- each **column** is one centered sample,
- D = number of features,
- N = number of samples.

For the exam-style case:

> **X ∈ R^(1024×20)**

Therefore:

> **XXᵀ ∈ R^(1024×1024)**

while:

> **XᵀX ∈ R^(20×20)**

This dimension check is the entire reason the shortcut is useful.

### Memory Rule

> **D huge, N small → avoid the D×D matrix; solve the N×N problem.**

---

## 14. The Large PCA Eigenvalue Problem

Ignoring an overall normalization factor such as 1/N or 1/(N-1), the feature-space covariance-like matrix is:

> **C = XXᵀ**

PCA would normally solve:

> **XXᵀu = λu**

where u is a principal-component direction in the original D-dimensional feature space.

For D = 1024, this means eigendecomposition of a:

> **1024 × 1024 matrix**

which is unnecessarily large when only N = 20 samples are available.

---

## 15. The Smaller Matrix

Instead define:

> **G = XᵀX**

Then:

> **G ∈ R^(N×N)**

For N = 20:

> **G is only 20 × 20.**

Now solve:

> **XᵀXv = λv**

This is the small eigenvalue problem.

The key question becomes:

> **How does an eigenvector v of XᵀX give us a principal direction u of XXᵀ?**

---

## 16. Core Derivation — Why the Trick Works

Suppose:

> **XᵀXv = λv**

Multiply both sides on the left by X:

**X(XᵀXv) = X(λv)**

Rearrange:

> **XXᵀ(Xv) = λ(Xv)**

Compare this with the eigenvalue equation:

> **XXᵀu = λu**

Therefore:

> **u is proportional to Xv.**

So an eigenvector of the small matrix XᵀX can be mapped into the original feature space by multiplying it by X.

This proves the central result:

> **If v is an eigenvector of XᵀX with nonzero eigenvalue λ, then Xv is an eigenvector of XXᵀ with the same eigenvalue λ.**

---

## 17. Why the Eigenvalue Must Be Nonzero

Suppose:

> **λ = 0**

Then:

**XᵀXv = 0**

and it is possible that:

> **Xv = 0**

But the zero vector cannot be an eigenvector.

Therefore the useful correspondence is for:

> **nonzero eigenvalues λ > 0.**

Since XᵀX and XXᵀ are positive semidefinite, their eigenvalues are non-negative.

---

## 18. Normalizing the Recovered Principal Direction

We know:

> **u ∝ Xv**

If v is a unit eigenvector of XᵀX:

> **vᵀv = 1**

and:

> **XᵀXv = λv**

then:

**||Xv||² = (Xv)ᵀ(Xv)**

**= vᵀXᵀXv**

**= vᵀ(λv)**

**= λvᵀv**

**= λ**

Therefore:

> **||Xv|| = √λ**

Hence the normalized principal direction is:

> **u = Xv / √λ**

---

# Master Formula — Dual-Space PCA

If:

> **XᵀXvᵢ = λᵢvᵢ**

with λᵢ > 0 and ||vᵢ|| = 1, then:

> **uᵢ = Xvᵢ / √λᵢ**

and:

> **XXᵀuᵢ = λᵢuᵢ**

---

## 19. Dimension Tracking

For:

> **X : 1024 × 20**

we get:

> **XᵀX : 20 × 20**

so v is 20×1, while:

> **Xv : (1024×20)(20×1) = 1024×1**

which is exactly a principal direction in the original feature space.

---

## 20. Why XᵀX and XXᵀ Share the Same Nonzero Eigenvalues

If:

> **XᵀXv = λv**, λ ≠ 0

then:

> **XXᵀ(Xv) = λ(Xv)**

Conversely, if:

> **XXᵀu = λu**, λ ≠ 0

then multiplying by Xᵀ gives:

> **XᵀX(Xᵀu) = λ(Xᵀu)**

Hence:

> **XXᵀ and XᵀX have the same nonzero eigenvalues.**

---

## 21. Connection to SVD

If:

> **X = UΣVᵀ**

then:

> **XXᵀ = UΣ²Uᵀ**

and:

> **XᵀX = VΣ²Vᵀ**

Therefore:

> **λᵢ = σᵢ²**

and:

> **uᵢ = Xvᵢ / σᵢ = Xvᵢ / √λᵢ**

---

## 22. Rank Insight

For X ∈ R^(D×N):

> **rank(X) ≤ min(D,N)**

For D=1024, N=20:

> **rank(X) ≤ 20**

If centered, commonly:

> **rank(X) ≤ N-1 = 19**

So the 1024×1024 covariance-like matrix can have only a small number of nonzero eigenvalues.

---

## 23. Exam Procedure — High-Dimensional PCA

1. Center the data.
2. Form XᵀX instead of XXᵀ when D >> N.
3. Solve **XᵀXvᵢ = λᵢvᵢ**.
4. Keep nonzero λᵢ.
5. Recover **uᵢ = Xvᵢ/√λᵢ**.
6. Select top components.

### Compact Exam Answer

> Let X ∈ R^(D×N), with D=1024 and N=20. Instead of diagonalizing XXᵀ, solve the 20×20 problem XᵀXvᵢ=λᵢvᵢ. Then XXᵀ(Xvᵢ)=λᵢ(Xvᵢ), so the normalized feature-space PC is **uᵢ=Xvᵢ/√λᵢ**.

---

# 24. PCA Feature Scaling — Does the Principal Direction Simply Scale?

Suppose:

> **x' = Dx**, with **D = diag(α₁,...,α_D)**

Then for centered data:

> **C' = DCD**

If all scales are the same, D=αI and:

> **C' = α²C**

so eigenvectors do not change.

But with unequal scaling, eigenvectors generally change.

### Why Dv is Not Generally the New Eigenvector

If Cv=λv and we guess v'=Dv, then:

> **C'v' = DCD(Dv) = DCD²v**

The original equation Cv=λv gives no reason for CD²v to be proportional to v.

Therefore:

> **Dv is generally not an eigenvector of DCD.**

### Counterexample

```text
C = |2 1|
    |1 2|
```

Dominant eigenvector is proportional to (1,1)ᵀ.

Scale first feature by 2:

```text
D = |2 0|
    |0 1|
```

Then:

```text
C' = DCD = |8 2|
           |2 2|
```

Naively scaled vector is (2,1)ᵀ.

But:

> **C'(2,1)ᵀ = (18,6)ᵀ**

which is not proportional to (2,1)ᵀ.

So the principal direction changes.

### Standardization

For features with very different numerical scales, standardization is often useful:

> **zᵢ = (xᵢ-μᵢ)/σᵢ**

PCA on standardized data is closely related to PCA on the correlation matrix.

### Exam Rule

| Transformation | PCA effect |
|---|---|
| x' = αx | Same eigenvectors, eigenvalues × α² |
| x' = Dx with unequal scales | Eigenvectors generally change |
| x' = Qx, Q orthogonal | Eigenvectors rotate as Qv |

---

# 25. Modified Covariance Matrix After Feature Scaling

This directly addresses the paired MFML question asking whether the transformed covariance can be computed in O(D²) from the old covariance matrix.

If:

> **x' = Dx**

and old covariance is C, then:

> **C' = DCD**

Because D is diagonal, every entry transforms as:

> **C'ᵢⱼ = αᵢ αⱼ Cᵢⱼ**

So given C and the D scaling factors, we can compute all D² entries in O(D²).

### Compact Exam Answer

> Yes. If D=diag(α₁,...,α_D), the transformed covariance is **C'=DCD**, or entrywise **C'ᵢⱼ=αᵢαⱼCᵢⱼ**. Computing all entries needs O(D²) work.

---

# 26. Full Numerical PCA Workflow

The 2025–26 papers include full PCA calculations: covariance, unit eigenvectors/eigenvalues, choosing PC1, projection, and rank-1 reconstruction.

For any centered sample matrix with samples as rows:

1. Compute mean μ and center each sample: x̃ᵢ=xᵢ-μ.
2. Form covariance **C=(1/N)X̃ᵀX̃** or **1/(N-1)** depending on convention.
3. Solve **Cv=λv**.
4. Normalize eigenvectors.
5. Sort λ from largest to smallest.
6. Choose PC1 = eigenvector of largest λ.
7. Project a centered point using **z=v₁ᵀx̃**.
8. Reconstruct rank-1 point using **x̂=μ+v₁z**.

### Rank-1 Approximation

For all centered data:

> **X̂ = z v₁ᵀ**

if samples are rows and z=X̃v₁.

Equivalent pointwise form:

> **x̂ᵢ = μ + v₁v₁ᵀ(xᵢ-μ)**

### Exam Recognition

- “one-dimensional subspace” = span{v₁}
- “principal coordinate” = scalar zᵢ=v₁ᵀx̃ᵢ
- “rank-1 reconstruction” = project and map back
- “draw projected points” = points lie along PC1 line

---

# Topic 4 — Gradients, Jacobians and Chain Rule

## 27. Gradient of ||Ax-b||² + cᵀx + d

Let:

> **f(x)=||Ax-b||₂²+cᵀx+d**

Expand the squared term:

**||Ax-b||²=(Ax-b)ᵀ(Ax-b)**

The result is:

> **∇f = 2Aᵀ(Ax-b)+c**

Memory rule:

> **∇||Mx-r||² = 2Mᵀ(Mx-r)**

---

## 28. Jacobian of a Vector-Valued Function

Suppose:

> **f(x) = [xᵀQx, bᵀx]ᵀ**

For symmetric Q:

> **∇(xᵀQx)=2Qx**

Hence a row-wise Jacobian can be written as:

```text
J = | (2Qx)ᵀ |
    |   bᵀ    |
```

At x=0, the first-order approximation is:

> **f(x) ≈ [0, bᵀx]ᵀ**

---

## 29. Sigmoid and Tanh Derivatives

Sigmoid:

> **σ(z)=1/(1+e^(-z))**

Derivative:

> **σ'(z)=σ(z)(1-σ(z))**

Tanh:

> **tanh'(z)=1-tanh²(z)**

These are central to computation-graph questions.

---

## 30. Computation Graph Chain Rule

For the 2025–26 system:

- p=w₁ᵀx+b₁
- q=σ(p)
- r=w₂ᵀx+b₂
- s=tanh(r)
- m=q+s
- L=1/2(m-m*)²

The local derivatives are:

> **∂L/∂m = m-m***

> **∂L/∂q = m-m***

> **∂L/∂s = m-m***

> **∂q/∂p = q(1-q)**

> **∂s/∂r = 1-s²**

> **∂p/∂w₁ = x**

Thus:

> **∂L/∂p = (m-m*)q(1-q)**

and similarly:

> **∂L/∂r = (m-m*)(1-s²)**

For x:

> **∇ₓL = (m-m*)[q(1-q)w₁ + (1-s²)w₂]**

### Computation-Graph Exam Pattern

Always work backward:

> **loss → merge node → activation → affine node → parameter/input**

---

## 31. Regularized Quadratic Loss Gradient

For:

> **L(β)=1/(2p)||y-β||² + λ||Wβ||²**

we get:

> **∇L = -(1/p)(y-β) + 2λWᵀWβ**

The transpose orientation may vary depending on row/column gradient convention; the conceptual vector gradient above is the safest form.

---

# Topic 5 — Inner Products, Norms and Distances

## 32. Matrix-Weighted Inner Product

Define:

> **⟨x,y⟩_A = xᵀAy**

For this to be an inner product over Rⁿ, A must be:

1. symmetric: **A=Aᵀ**
2. positive definite: **xᵀAx>0 for all x≠0**

For a symmetric matrix, positive definiteness can be checked by positive eigenvalues or positive leading principal minors.

---

## 33. Orthogonality Under a Weighted Inner Product

Vectors x,y are A-orthogonal if:

> **xᵀAy=0**

This is not necessarily the same as ordinary Euclidean orthogonality xᵀy=0.

For the MFML 3×3 matrix:

```text
A = |1  0  ρ|
    |0  1  ρ|
    |ρ  ρ  1|
```

the inner product is valid when A is positive definite.

Leading principal minors give:

- 1 > 0
- 1 > 0
- det(A)=1-2ρ² > 0

Therefore:

> **|ρ| < 1/√2**

For e₁=(1,0,0) and e₂=(0,1,0):

> **e₁ᵀAe₂=0**

so they are A-orthogonal.

If z=(z₁,z₂,z₃) must be orthogonal to both:

> **e₁ᵀAz = z₁+ρz₃=0**

> **e₂ᵀAz = z₂+ρz₃=0**

Thus:

> **z = t(-ρ,-ρ,1)**

---

## 34. L1 Distance is a Valid Metric

For:

> **d(x,y)=Σ|xᵢ-yᵢ|**

check four properties:

1. non-negativity
2. identity: d(x,y)=0 iff x=y
3. symmetry
4. triangle inequality

The triangle inequality follows from:

> **|xᵢ-zᵢ| ≤ |xᵢ-yᵢ|+|yᵢ-zᵢ|**

and summing over i.

---

## 35. Projection with a Trace Constraint

If the problem asks for a matrix M minimizing distance to A subject to:

> **trace(M)=0**

this is projection onto the linear subspace of trace-zero matrices.

For A=diag(1,2), under Frobenius norm, the closest trace-zero matrix subtracts the same scalar from each diagonal entry:

Mean trace per dimension = 3/2.

Therefore:

```text
M = | -1/2   0 |
    |   0   1/2|
```

since trace(M)=0.

---

# Topic 6 — Critical Points and Hessian

## 36. Critical Points

For f(x,y), solve:

> **∂f/∂x=0 and ∂f/∂y=0**

Then classify using Hessian:

```text
H = |f_xx  f_xy|
    |f_yx  f_yy|
```

For two variables:

> **D = f_xx f_yy - f_xy²**

- D>0 and f_xx>0 → local minimum
- D>0 and f_xx<0 → local maximum
- D<0 → saddle
- D=0 → inconclusive

---

## 37. Actual Radial MFML Pattern

For:

> **f(x,y)=(x²+y²)e^(-(x²+y²))**

let r²=x²+y².

Critical points occur at:

> **(0,0)**

and on:

> **x²+y²=1**

At origin, Hessian is positive definite, so origin is a local minimum.

The circle r=1 is a set of maxima for the radial function r²e^(-r²).

---

## 38. One-Dimensional Critical Points and Zones of Attraction

For cubic:

> **f(x)=ax³+bx²+cx+d**, a>0

critical points satisfy:

> **f'(x)=3ax²+2bx+c=0**

Two distinct critical points exist when discriminant is positive:

> **(2b)²-4(3a)c > 0**

or:

> **b²-3ac > 0**

Critical points:

> **x = [-b ± √(b²-3ac)]/(3a)**

Since a>0, the smaller critical point is a local maximum and the larger is a local minimum.

For sufficiently small-step gradient descent, the local maximum acts as a basin boundary; points on the side flowing toward the local minimum belong to its zone of attraction.

---

# Topic 7 — Gradient Descent and Optimization

## 39. Basic Gradient Descent

Update:

> **x_{k+1}=x_k-α∇f(x_k)**

Interpretation:

- ∇f points uphill
- -∇f points downhill
- α controls step size

Too large α may overshoot/diverge; very small α is slow.

---

## 40. Optimal Step Size for a Quadratic

For quadratic f and descent direction d=-∇f, exact line search solves:

> minimize f(x+αd)

For Hessian H:

> **α* = (gᵀg)/(gᵀHg)**

where g=∇f and d=-g.

This formula produces the MFML variants involving:

- f=x²+βy²
- f=2x²+βy²

The exam pattern is:

1. compute g
2. compute H
3. substitute into α*=(gᵀg)/(gᵀHg)
4. equate to the given α
5. solve for β

---

## 41. Momentum

A common update is:

> **z_{k+1}=z_k-α∇f(z_k)+β(z_k-z_{k-1})**

β carries a fraction of the previous movement into the new step.

The 2023–24 MFML problem reduces the x-coordinate recurrence and solves β from the supplied x₃ value, giving:

> **β=0.4**

### Exponential-Moving-Average Interpretation

For updates of the form:

> **a_t = γa_{t-1} + (1-γ)g_t**

older gradients receive geometrically decaying weights.

Contribution of an old gradient g_j to a_t is proportional to:

> **(1-γ)γ^(t-j)**

So γ controls memory length:

- γ near 1 → long memory/smoother updates
- small γ → recent gradients dominate

---

## 42. Initialization and Global Minima

For nonconvex functions, initialization matters because gradient descent follows local slope.

Exam approach:

1. solve f'(x)=0
2. classify stationary points
3. sketch sign of f'(x)
4. identify which starting point flows to which minimum

For the polynomial with stationary points 0,2,3, the initial value should be chosen from the basin that leads to the global minimum rather than the wrong local basin.

---

# Topic 8 — Convexity

## 43. Convex Set

A set C is convex if for any x,y∈C and θ∈[0,1]:

> **θx+(1-θ)y ∈ C**

For:

> **C={x:Ax=b}**

if Ax=b and Ay=b, then:

> **A[θx+(1-θ)y]=θb+(1-θ)b=b**

so C is convex.

---

## 44. Convex Function

f is convex if:

> **f(θx+(1-θ)y) ≤ θf(x)+(1-θ)f(y)**

### L1 Norm

> **f(x)=||x||₁**

is convex because norms satisfy triangle inequality and absolute homogeneity:

> **||θx+(1-θ)y||₁ ≤ θ||x||₁+(1-θ)||y||₁**

### Affine Composition

If g is convex and:

> **h(x)=g(Ax+b)**

then h is convex because affine maps preserve convex combinations.

---

# Topic 9 — Lagrange Multipliers

## 45. Equality-Constrained Optimization

For:

> minimize f(x) subject to h(x)=0

form:

> **L(x,λ)=f(x)+λh(x)**

Stationarity requires:

> **∇f + λ∇h = 0**

plus the constraint h=0.

---

## 46. Closest Point to a Line

To find the closest point to p on line h(x,y)=0, minimize squared distance:

> **(x-p₁)²+(y-p₂)²**

subject to h=0.

This avoids unnecessary square roots.

The 2023–24 question evaluates two candidate constraint lines separately, then compares the resulting squared distances.

---

## 47. Equality Constraint Example

For:

> **minimize f=x²+y**

subject to:

> **x²-y²=1**

Lagrange equations lead to:

> **λ=1, y=-1/2, x=±√(5/4)**

and:

> **f=3/4**

for the minima.

---

## 48. Linear Objective with Linear Equality Constraint

Consider:

> **min ax+by+cz**

subject to:

> **px+qy+rz=0**

Let objective vector c=(a,b,c) and constraint normal n=(p,q,r).

If objective vector is not parallel to the constraint normal, there exists a feasible direction within the plane along which the objective decreases without bound. Therefore no finite minimizer exists.

A finite minimum exists only when:

> **(a,b,c)=λ(p,q,r)**

Then every feasible point satisfies objective:

> **λ(px+qy+rz)=0**

so every feasible point is optimal and minimum value is 0.

---

# Topic 10 — KKT and Duality

## 49. KKT Conditions

For:

> minimize f(x)

subject to:

> **gᵢ(x) ≤ 0**

Lagrangian:

> **L=f+Σλᵢgᵢ**

KKT conditions:

1. primal feasibility: gᵢ(x*)≤0
2. dual feasibility: λᵢ≥0
3. stationarity: ∇f+Σλᵢ∇gᵢ=0
4. complementary slackness: λᵢgᵢ(x*)=0

For convex problems satisfying a constraint qualification such as Slater's condition, KKT conditions are sufficient and strong duality holds.

---

## 50. Nearest-Point KKT Pattern

For a point constrained by inequalities:

> minimize distance² to origin

subject to region constraints.

Exam procedure:

1. write all inequalities as gᵢ≤0
2. form Lagrangian
3. write stationarity
4. list feasibility
5. list λᵢ≥0
6. apply λᵢgᵢ=0
7. test active-set cases

The 2025–26 receiver-location question is exactly this pattern.

---

## 51. Dual Function

Given L(x,λ), the dual function is:

> **q(λ)=inf_x L(x,λ)**

Dual problem:

> maximize q(λ) subject to λ≥0

Weak duality always gives:

> **dual optimum ≤ primal optimum**

Strong duality gives equality under suitable convexity/regularity conditions.

---

# Topic 11 — Regularized Quadratic Loss and Exact Line Search

## 52. Gradient

For:

> **g(z)=1/2||Az-b||² + 1/2||z||² + ||b||²**

we get:

> **∇g=(AᵀA+I)z-Aᵀb**

The steepest-descent direction is:

> **d=Aᵀb-(AᵀA+I)z = -∇g**

---

## 53. Optimal Step Size

Let:

> **H=AᵀA+I**

Then exact line-search step along d gives:

> **α*=(dᵀd)/(dᵀHd)**

This is the same quadratic exact-line-search pattern already seen in the GD questions.

---

# Topic 12 — Null Space and Rank Completion

## 54. Orthogonality Constraints as a Null Space

If:

> **S={x:Rᵢᵀx=0 for all i}**

stack the row vectors into matrix A.

Then:

> **S=N(A)**

If A has m columns and rank(A)=m, then:

> **nullity(A)=m-rank(A)=0**

Therefore:

> **S={0}**

This covers the remaining null-space/rank question pattern.

---

# Topic 13 — SVM and Kernel Methods

## 55. Hard-Margin SVM Primal

For labeled points (xᵢ,yᵢ), yᵢ∈{−1,+1}:

> minimize **1/2||w||²**

subject to:

> **yᵢ(wᵀxᵢ+b) ≥ 1**

The decision boundary is:

> **wᵀx+b=0**

Margin width is inversely related to ||w||.

---

## 56. SVM Dual

The hard-margin dual is:

> maximize **Σαᵢ - 1/2 ΣᵢΣⱼ αᵢαⱼyᵢyⱼ xᵢᵀxⱼ**

subject to:

> **αᵢ≥0**

and:

> **Σαᵢyᵢ=0**

Recover:

> **w=Σαᵢyᵢxᵢ**

Support vectors have αᵢ>0.

---

## 57. Why Adding a Training Point Cannot Reduce the Dual Maximum

In the 2025–26 question, problem B adds one more variable αₙ₊₁≥0 to the SVM dual.

Take any feasible solution of problem A and set:

> **αₙ₊₁=0**

Then the same α₁,...,αₙ remains feasible for problem B and gives exactly the same objective value.

Therefore B's feasible set contains an embedded copy of A's feasible set.

Hence:

> **max(B) ≥ max(A)**

This is a clean feasible-set argument.

---

## 58. Kernel Trick

A kernel computes an inner product in a feature space:

> **K(x,z)=φ(x)ᵀφ(z)**

without explicitly constructing φ when unnecessary.

### Kernel Matrix

For samples x₁,...,xₙ:

> **Kᵢⱼ=K(xᵢ,xⱼ)**

A valid kernel matrix is symmetric positive semidefinite.

---

## 59. Explicit Feature Map Example

For:

> **K(x,z)=(xᵀz)² + 3(xᵀz+2)²**

expand:

**K = 4(xᵀz)² + 12xᵀz + 12**

A valid map can combine:

- quadratic monomials representing 4(xᵀz)²
- linear coordinates scaled by √12
- constant coordinate √12

One convenient conceptual map is:

> **φ(x) = [2 vec(xxᵀ), √12 x, √12]**

which has n²+n+1 entries and satisfies:

> **φ(x)ᵀφ(z)=4(xᵀz)²+12xᵀz+12**

Exactly matching K.

---

## 60. Quadratic-Kernel Feature Count

For a degree-2 polynomial-type construction with constant, linear, and ordered quadratic terms, the feature map can have:

> **1+d+d²**

components.

If symmetric monomials are compressed, the minimal count may be smaller, but the exam's stated mapping pattern uses 1+d+d².

---

## 61. Hinge Loss

Standard hinge loss:

> **max(0,1-yf(x))**

Interpretation:

- yf(x)≥1 → loss 0
- correct but inside margin → positive loss
- misclassified → larger positive loss

---

## 62. Soft Margin and C

Soft-margin primal:

> minimize **1/2||w||² + CΣξᵢ**

subject to:

> **yᵢ(wᵀxᵢ+b) ≥ 1-ξᵢ**, ξᵢ≥0

Interpretation:

- **large C** strongly penalizes violations → tries harder to fit training points, can overfit noise
- **small C** tolerates violations → wider/smoother margin, more robust to noisy labels/outliers

For noisy sensor data, a smaller/moderate C is usually preferable to avoid chasing noise.

Points far from the margin with α=0 are typically non-support vectors; changing such a point slightly may not affect the boundary. Support vectors are boundary-sensitive.

---

## 63. Nonlinear Separability and Feature Transformations

Some datasets become linearly separable after mapping φ(x).

Exam examples include:

- parity/mod-2 transformation
- XOR solved with quadratic features

The pattern is:

> **nonlinear in input space → linear in feature space**

---

# Topic 14 — Power Method

## 64. Power Method Idea

Starting from x₀, repeatedly compute:

> **x_{k+1}=Ax_k**

and normalize.

If A has a unique dominant eigenvalue in magnitude and the starting vector has nonzero component in its eigenvector direction, the normalized iterates converge to the dominant eigenvector direction.

---

## 65. Actual 2025–26 Pattern

For:

```text
A = |1 2|
    |1 2|
```

characteristic polynomial gives eigenvalues:

> **λ=3 and λ=0**

For λ=3, eigenvector satisfies y=x, so dominant eigenvector is proportional to:

> **(1,1)ᵀ**

For λ=0, eigenvector is proportional to:

> **(-2,1)ᵀ**

If the chosen starting vector has a nonzero component along (1,1), the power method converges to λ=3 and eigenvector direction (1,1).

### Important Trap

If the initial vector is exactly orthogonal/invariant in a way that has zero component along the dominant eigenvector, convergence to the dominant mode can fail.

---

# Topic 15 — Eigenvalues Completion: Complex Eigenvalues

## 66. Actual 2025–26 EC-3 Matrix

```text
A = |3 -1  0|
    |1  3  0|
    |0  0  4|
```

The top-left 2×2 block has characteristic equation:

> **(3-λ)²+1=0**

Therefore:

> **λ=3±i**

The third eigenvalue is:

> **λ=4**

So over the real field, the 2×2 block has no real eigenvectors for 3±i. Over C, corresponding eigenvectors exist.

For λ=3+i, one eigenvector is proportional to:

> **(1,-i,0)ᵀ**

For λ=3-i:

> **(1,i,0)ᵀ**

For λ=4:

> **(0,0,1)ᵀ**

### Exam Rule

Real matrices can have complex conjugate eigenvalue pairs.

---

# Topic 16 — Final Consolidated Exam Patterns

## 67. High-Frequency Formula Sheet

### Linear Algebra

> **rank + nullity = number of columns**

> **Av=λv ⇒ det(A-λI)=0**

> **trace(A)=Σλᵢ**

> **det(A)=Πλᵢ**

> **A symmetric ⇒ orthogonally diagonalizable**

### SVD / PCA

> **A=UΣVᵀ**

> **AᵀA=VΣ²Vᵀ**

> **AAᵀ=UΣ²Uᵀ**

> **PCA PC1 = eigenvector of covariance with largest eigenvalue**

> **explained variance ratio = cumulative eigenvalues / total eigenvalues**

> **projection z=Vᵀx**

> **reconstruction x̂=VVᵀx**

### Gradients

> **∇||Ax-b||² = 2Aᵀ(Ax-b)**

> **∇(xᵀQx)=(Q+Qᵀ)x**

> symmetric Q ⇒ **2Qx**

> **σ'(z)=σ(1-σ)**

> **tanh'(z)=1-tanh²(z)**

### Optimization

> **GD: x_{k+1}=x_k-α∇f**

> **quadratic exact line search: α*=(gᵀg)/(gᵀHg)**

> **Lagrange: ∇f+λ∇h=0**

> **KKT: feasibility + dual feasibility + stationarity + complementary slackness**

### SVM

> **yᵢ(wᵀxᵢ+b)≥1**

> **w=Σαᵢyᵢxᵢ**

> **K(x,z)=φ(x)ᵀφ(z)**

> **hinge=max(0,1-yf(x))**

---

# 68. Coverage Verification Against MFML_Questions_Categorized.md

The categorized bank was rechecked category-by-category after completing Part 2.

## Category 1 — PCA & Dimensionality Reduction

Covered:

- feature scaling and why PCs do not simply scale
- transformed covariance in O(D²)
- maximum-variance direction
- 95% / 99% explained variance
- PCA projection
- D=1024, N=20 dual-space/kernel trick
- full covariance/eigenvector/projection workflow
- rank-1 reconstruction

> **Status: Covered**

## Category 2 — Gradient Descent & Optimization

Covered:

- basic GD
- momentum
- EMA interpretation of γ
- optimal step-size quadratic pattern
- nonconvex initialization
- critical points and attraction zones

> **Status: Covered**

## Category 3 — SVM & Kernel Methods

Covered:

- primal and dual
- support-vector interpretation
- adding a data point cannot reduce dual maximum
- explicit kernel matrix idea
- nonlinear feature mappings
- quadratic/XOR-style kernel intuition
- hinge loss
- soft-margin C
- degree-2 feature-map count
- explicit 2025–26 kernel map pattern

> **Status: Covered conceptually and by exam pattern**

## Category 4 — Convex Functions & Optimization

Covered:

- convex sets
- L1 norm convexity
- affine composition
- Lagrange multiplier method
- linear objective with linear equality constraint
- nearest-point patterns

> **Status: Covered**

## Category 5 — Eigenvalues & Matrix Properties

Covered across Part 1 and Part 2:

- characteristic equation
- eigenspaces
- trace/determinant
- triangular matrices
- multiplicity and diagonalizability
- symmetric-matrix orthogonality
- complex-eigenvalue 2025–26 matrix

> **Status: Covered**

## Category 6 — Vector Spaces & Linear Independence

Covered in Part 1:

- span
- independence
- basis
- dimension
- field dependence
- RREF uniqueness
- general Ax=b solution
- skew-symmetric matrix subspace

> **Status: Covered**

## Category 7 — Gradients & Jacobians

Covered:

- norm-squared gradient
- quadratic form Jacobian
- sigmoid derivative
- tanh derivative
- computation graph and chain rule
- regularized quadratic gradient

> **Status: Covered**

## Category 8 — Inner Products & Norms

Covered:

- weighted inner product requirements
- positive definite matrix condition
- weighted orthogonality
- L1 metric proof
- trace-zero projection pattern

> **Status: Covered**

## Category 9 — Critical Points

Covered:

- gradient-zero condition
- Hessian classification
- radial MFML example
- one-dimensional stationary-point classification

> **Status: Covered**

## Category 10 — Constrained Optimization & KKT

Covered:

- Lagrangian
- KKT four conditions
- active constraints
- nearest-point inequality problems
- dual function
- weak/strong duality

> **Status: Covered**

## Category 11 — SVD

Covered in Part 1 and reinforced in Part 2:

- SVD decomposition
- AᵀA and AAᵀ
- singular values
- Frobenius norm
- rank
- PCA connection

> **Status: Covered**

## Category 12 — Regularized Loss & Stochastic Gradients

Covered:

- regularized quadratic gradient
- descent direction
- exact line-search step size

> **Status: Covered**

## Category 13 — Null Space & Rank

Covered in Part 1 and completed here:

- rank formula pattern a_jk=j+k-1
- column dependencies as null-space vectors
- orthogonality constraints as null space
- full-column-rank ⇒ nullity zero

> **Status: Covered**

## Category 14 — Power Method & Iterative Techniques

Covered:

- convergence principle
- dominant eigenvalue requirement
- initialization condition
- 2025–26 2×2 example

> **Status: Covered**

---

# 69. Final Coverage Conclusion

After comparing the notes against the categorized MFML question bank, every named category and every listed exam-question pattern is represented in either:

- **MFML_Learning_Notes.md**, or
- **MFML_Learning_Notes_Part_2.md**.

The remaining risk is only source-format detail for questions whose original paper contains a diagram or formatting that is not fully reproduced in the categorized Markdown. The underlying mathematical concepts and solution patterns for those questions are covered.

> **Coverage status: No major MFML topic category remains uncovered.**

> **Recommended next use of these notes: revision + solving full past-paper questions under exam timing.**