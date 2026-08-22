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

This is one of the most important formulas to remember for this exam pattern.

---

# Master Formula — Dual-Space PCA

If:

> **XᵀXvᵢ = λᵢvᵢ**

with λᵢ > 0 and ||vᵢ|| = 1, then the corresponding feature-space principal direction is:

> **uᵢ = Xvᵢ / √λᵢ**

and:

> **XXᵀuᵢ = λᵢuᵢ**

So we obtain the same nonzero eigenvalue λᵢ without directly diagonalizing the huge D×D matrix.

---

## 19. Dimension Tracking — Very Important for the Exam

For:

> **X : 1024 × 20**

we have:

> **Xᵀ : 20 × 1024**

Therefore:

> **XᵀX : 20 × 20**

Its eigenvector v has dimension:

> **v : 20 × 1**

Now:

> **Xv : (1024×20)(20×1) = 1024×1**

Therefore u has dimension:

> **u : 1024 × 1**

which is exactly what we need for a principal direction in the original 1024-dimensional feature space.

### Dimension Chain

> **v (20×1) → multiply by X (1024×20) → u (1024×1)**

This is a very useful sanity check.

---

## 20. Why XᵀX and XXᵀ Share the Same Nonzero Eigenvalues

We already proved one direction.

Suppose:

> **XᵀXv = λv**, λ ≠ 0

Then:

> **XXᵀ(Xv) = λ(Xv)**

So λ is also an eigenvalue of XXᵀ.

The reverse direction works similarly.

Suppose:

> **XXᵀu = λu**, λ ≠ 0

Multiply by Xᵀ:

> **XᵀXXᵀu = λXᵀu**

Therefore:

> **XᵀX(Xᵀu) = λ(Xᵀu)**

Thus λ is also an eigenvalue of XᵀX.

Hence:

> **XXᵀ and XᵀX have the same nonzero eigenvalues.**

They may have different numbers of zero eigenvalues because their matrix sizes can be different.

---

## 21. Connection to SVD

Recall the singular value decomposition:

> **X = UΣVᵀ**

Then:

> **XXᵀ = UΣ²Uᵀ**

and:

> **XᵀX = VΣ²Vᵀ**

Therefore:

- columns of **U** are eigenvectors of XXᵀ,
- columns of **V** are eigenvectors of XᵀX,
- eigenvalues are **σᵢ²**.

Thus:

> **λᵢ = σᵢ²**

and:

> **σᵢ = √λᵢ**

From:

> **Xvᵢ = σᵢuᵢ**

we get:

> **uᵢ = Xvᵢ / σᵢ = Xvᵢ / √λᵢ**

So the dual-space PCA formula is exactly the same relationship that appears in SVD.

---

## 22. Why This is Computationally Better

Compare the two eigenvalue problems.

### Direct Method

Solve eigenvectors of:

> **XXᵀ : 1024 × 1024**

### Dual-Space Method

Solve eigenvectors of:

> **XᵀX : 20 × 20**

Then map each useful eigenvector back using:

> **uᵢ = Xvᵢ / √λᵢ**

A 20×20 eigendecomposition is dramatically smaller than a 1024×1024 eigendecomposition.

Therefore:

> **When D >> N, use XᵀX instead of XXᵀ.**

---

## 23. Rank Insight

For:

> **X ∈ R^(D×N)**

we always have:

> **rank(X) ≤ min(D,N)**

For D = 1024 and N = 20:

> **rank(X) ≤ 20**

Therefore XXᵀ, although it is a 1024×1024 matrix, can have at most 20 nonzero eigenvalues.

If the data has been mean-centered, the centered columns satisfy a linear dependence because their sum is zero. Therefore commonly:

> **rank(X) ≤ N-1 = 19**

and hence there can be at most 19 nonzero principal directions.

This explains intuitively why solving a 1024-dimensional eigenproblem is wasteful: almost all directions must correspond to zero variance.

---

## 24. Exam Procedure

If the question gives a high-dimensional PCA problem with:

> **D >> N**

follow these steps.

### Step 1 — Center the data

Construct the centered matrix X.

### Step 2 — Check dimensions

If:

> **X ∈ R^(D×N)**

then:

- XXᵀ is D×D
- XᵀX is N×N

### Step 3 — Solve the smaller eigenproblem

> **XᵀXvᵢ = λᵢvᵢ**

### Step 4 — Keep nonzero eigenvalues

Sort:

> **λ₁ ≥ λ₂ ≥ ... > 0**

### Step 5 — Recover the original-space PCs

> **uᵢ = Xvᵢ / √λᵢ**

### Step 6 — Choose the top k PCs

Use the largest eigenvalues according to the requested number of components or explained-variance threshold.

---

# Compact Exam Answer

> Let the centered data matrix be X ∈ R^(D×N), where D=1024 and N=20. Direct PCA using XXᵀ would require eigendecomposition of a 1024×1024 matrix. Instead, compute the much smaller 20×20 matrix XᵀX and solve XᵀXvᵢ=λᵢvᵢ. Multiplying by X gives XXᵀ(Xvᵢ)=λᵢ(Xvᵢ), so Xvᵢ is an eigenvector of XXᵀ with the same nonzero eigenvalue. If vᵢ is normalized, ||Xvᵢ||=√λᵢ, hence the normalized principal direction is **uᵢ=Xvᵢ/√λᵢ**. Thus the PCA directions can be obtained from the much smaller N×N eigenproblem.

---

# Quick Exam Recognition Table — High-Dimensional PCA

| If you see... | Think immediately |
|---|---|
| D >> N | Solve the N×N problem |
| X is D×N | XXᵀ is D×D; XᵀX is N×N |
| XᵀXv = λv | Multiply by X |
| Need eigenvector of XXᵀ | u = Xv / √λ |
| Eigenvalues of XᵀX | Same nonzero eigenvalues as XXᵀ |
| λ from XᵀX | Singular value σ = √λ |
| X = UΣVᵀ | uᵢ = Xvᵢ/σᵢ |
| D=1024, N=20 | Prefer 20×20 over 1024×1024 |
| Centered N samples | Rank is at most N-1 |

---

# Final Memory Chain

> **Huge feature space + few samples**
>
> **D >> N**
>
> ↓
>
> **Do NOT diagonalize XXᵀ (D×D)**
>
> ↓
>
> **Diagonalize XᵀX (N×N)**
>
> ↓
>
> **XᵀXvᵢ = λᵢvᵢ**
>
> ↓ multiply by X
>
> **XXᵀ(Xvᵢ) = λᵢ(Xvᵢ)**
>
> ↓ normalize
>
> **uᵢ = Xvᵢ / √λᵢ**
>
> ↓
>
> **These uᵢ are the PCA directions in the original feature space.**

---

## One-Line Memory Rule

> **When features are huge but samples are few, solve PCA in sample space and map the eigenvectors back to feature space.**

---

# 25. PCA Feature Scaling — Does the Principal Direction Simply Scale?

Suppose the original data vector is:

> **x = (x₁, x₂, ..., x_D)ᵀ**

and PCA gives a principal eigenvector:

> **v = (v₁, v₂, ..., v_D)ᵀ**

Now suppose every feature is scaled separately:

> **xᵢ' = αᵢxᵢ**

A tempting guess is:

> **new PCA eigenvector = (α₁v₁, α₂v₂, ..., α_Dv_D)ᵀ**

In general, this is:

> **Incorrect.**

The reason is that coordinate-wise scaling changes the covariance matrix in a way that can rotate the principal directions.

---

## 26. Uniform Scaling — The Easy Case

Suppose every feature is multiplied by the same scalar α:

> **x' = αx**

If the original covariance matrix is C, then the transformed covariance matrix is:

> **C' = α²C**

Suppose:

> **Cv = λv**

Then:

**C'v = α²Cv**

**= α²λv**

Therefore:

- the eigenvectors stay the same,
- the eigenvalues are multiplied by α².

So:

> **Uniform scaling changes variance magnitude but not PCA directions.**

### Example

If all measurements are doubled:

> **x' = 2x**

then:

> **C' = 4C**

The principal directions remain unchanged, but their associated variances become four times larger.

---

## 27. Different Scaling for Different Features

Now suppose each coordinate has its own scale factor.

Define:

```text
D = diag(α₁, α₂, ..., α_D)
```

Then:

> **x' = Dx**

For centered data, the transformed covariance matrix is:

> **C' = DCD**

because D is diagonal and therefore Dᵀ = D.

This is fundamentally different from the uniform-scaling case.

Unless D = αI, the new covariance matrix is not merely a scalar multiple of C.

Therefore:

> **The PCA eigenvectors generally change.**

Geometrically, different scaling stretches different coordinate directions by different amounts and changes the shape of the data cloud.

That can rotate the maximum-variance direction.

---

## 28. Why We Cannot Simply Scale the Old Eigenvector

Suppose the original eigenvector satisfies:

> **Cv = λv**

Someone proposes:

> **v' = Dv**

as an eigenvector of the new covariance matrix C' = DCD.

For this to work, we would need:

> **C'v' = λ'v'**

But:

**C'v' = DCD(Dv)**

**= DCD²v**

The original equation Cv = λv gives no general relationship for CD²v.

Therefore we cannot conclude that Dv is an eigenvector of DCD.

Hence:

> **Scaling the entries of the old PCA eigenvector does not generally produce the new PCA eigenvector.**

---

## 29. Concrete Counterexample

Consider the covariance matrix:

```text
C = | 2  1 |
    | 1  2 |
```

Its largest eigenvalue is:

> **λ₁ = 3**

with eigenvector proportional to:

> **v₁ = (1,1)ᵀ**

Now scale the first feature by 2 and leave the second unchanged:

```text
D = | 2  0 |
    | 0  1 |
```

The new covariance matrix is:

> **C' = DCD**

which gives:

```text
C' = | 8  2 |
     | 2  2 |
```

If the naive scaling rule were correct, the new eigenvector would be:

> **Dv₁ = (2,1)ᵀ**

Test it:

```text
C'(2,1)ᵀ = (18,6)ᵀ
```

For (2,1)ᵀ to be an eigenvector, (18,6)ᵀ would have to be a scalar multiple of (2,1)ᵀ.

But:

- 18/2 = 9
- 6/1 = 6

The ratios are different.

Therefore:

> **(2,1)ᵀ is not an eigenvector of C'.**

So the old eigenvector cannot generally be updated by simply scaling its coordinates.

---

## 30. Why Standardization Matters in PCA

Suppose the features are measured on very different scales, for example:

- annual salary in rupees,
- age in years,
- number of children.

PCA is based on variance.

A feature with much larger numerical variance can dominate the covariance matrix simply because of its units or scale.

This is why PCA is often performed after standardization:

> **zᵢ = (xᵢ - μᵢ) / σᵢ**

After standardization, each feature has approximately:

- mean 0,
- variance 1.

This puts features on comparable scales before PCA.

---

## 31. Covariance PCA vs Correlation PCA

### PCA on the Covariance Matrix

Uses the original feature scales.

Therefore:

> **Features with larger variance may dominate.**

### PCA on Standardized Data

Equivalent to performing PCA using the correlation matrix.

Therefore:

> **Each feature is considered on a comparable variance scale.**

Neither approach is always universally better.

The correct choice depends on whether the original feature scales themselves are meaningful.

---

## 32. Important Transformation Comparison

### Case 1 — Uniform Scaling

> **x' = αx**

Then:

> **C' = α²C**

Therefore:

> **Eigenvectors remain unchanged.**

### Case 2 — Coordinate-Wise Scaling

> **x' = Dx**

Then:

> **C' = DCD**

Therefore:

> **Eigenvectors generally change.**

### Case 3 — Orthogonal Rotation

Suppose:

> **x' = Qx**

where Q is orthogonal:

> **QᵀQ = I**

Then:

> **C' = QCQᵀ**

If:

> **Cv = λv**

then:

**C'(Qv) = QCQᵀQv**

**= QCv**

**= λQv**

Therefore:

> **Under an orthogonal rotation, the eigenvectors simply rotate as Qv and the eigenvalues stay the same.**

This transformation behaves very differently from arbitrary coordinate-wise scaling.

---

## 33. Exam-Ready Answer

If the question asks:

> **If each coordinate is transformed as xᵢ' = αᵢxᵢ, can the new PCA eigenvector be obtained by simply scaling the entries of the old eigenvector?**

A compact answer is:

> **No, not in general. Let D=diag(α₁,...,α_D). The transformed covariance matrix is C'=DCD. If Cv=λv, it does not generally follow that Dv is an eigenvector of DCD. Coordinate-wise scaling changes the relative variances and covariances and can rotate the principal directions. Only uniform scaling D=αI leaves the PCA eigenvectors unchanged.**

---

# Quick Exam Recognition Table — PCA Scaling

| Transformation | New covariance | PCA effect |
|---|---|---|
| x' = αx | α²C | Same eigenvectors |
| x' = Dx | DCD | Eigenvectors generally change |
| x' = Qx, Q orthogonal | QCQᵀ | Eigenvectors rotate as Qv |
| Standardization | Scale each feature by 1/σᵢ | PCA can change significantly |

---

## Intuition to Remember

PCA asks:

> **Along which direction does the data vary the most?**

Different coordinate scaling changes the shape of the data cloud.

Changing the shape can change the maximum-variance direction.

Therefore:

> **Different feature scaling can change PCA itself.**

---

## One-Line Memory Rule

> **Uniform scaling preserves PCA directions; unequal feature scaling generally does not.**
