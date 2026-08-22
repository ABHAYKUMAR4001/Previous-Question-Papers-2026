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
