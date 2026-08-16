# MFML Learning Notes

# Topic 1 — Vector Spaces & Linear Independence

> **Learning goal:** Concept → intuition → simple example → actual exam question → step-by-step solution → exam pattern.

## Topic Map

**Vector Space → Subspace → Span → Linear Independence → Basis → Dimension**

We begin with the easiest chain:

**Linear Combination → Span → Linear Independence**

---

## 1. What is a Linear Combination?

Suppose we have two vectors:

- **v₁ = (1, 0)**
- **v₂ = (0, 1)**

Take any two numbers **a** and **b**.

Then:

**a v₁ + b v₂ = a(1,0) + b(0,1) = (a,b)**

This is called a **linear combination** of v₁ and v₂.

For example:

**3v₁ + 2v₂ = (3,2)**

### Intuition

Almost everything in this part of linear algebra asks some version of:

> **Can I create this vector using those vectors?**

That question leads directly to **span**.

---

## 2. What is Span?

The **span of {v₁, v₂}** means the collection of **all possible linear combinations** of v₁ and v₂.

In words:

**span{v₁,v₂} = all vectors of the form a v₁ + b v₂**

where a and b can be any real numbers.

For:

- v₁ = (1,0)
- v₂ = (0,1)

we can create:

- (1,2)
- (-3,7)
- (0,5)
- and in fact any point (x,y)

Therefore:

> **span{v₁,v₂} = R²**

### Geometric intuition

- One nonzero vector in R² usually spans a **line**.
- Two non-parallel vectors in R² span the **whole plane**.

So span tells us:

> **How much of the space can these vectors generate?**

---

## 3. Linear Dependence — Intuitive Meaning

Consider:

- **v₁ = (1,2)**
- **v₂ = (2,4)**

Clearly:

**v₂ = 2v₁**

So v₂ gives us **no new direction**.

If we already have v₁, adding v₂ does not increase the span:

**span{v₁} = span{v₁,v₂}**

Therefore v₁ and v₂ are **linearly dependent**.

> **Memory idea: Dependent = at least one vector is redundant.**

---

## 4. Mathematical Definition of Linear Independence

Vectors v₁, v₂, ..., vₙ are **linearly independent** if:

**a₁v₁ + a₂v₂ + ... + aₙvₙ = 0**

has only one possible solution:

> **a₁ = a₂ = ... = aₙ = 0**

This is called the **trivial solution**.

### Why do we compare the combination with zero?

If a **non-zero** set of coefficients can produce the zero vector, then at least one vector can be constructed from the others.

For example:

- v₁ = (1,2)
- v₂ = (2,4)

Since:

**2v₁ - v₂ = 0**

we found coefficients 2 and -1 that are not both zero.

Therefore:

> **v₁ and v₂ are linearly dependent.**

---

# Exam Question 1 — Proving Linear Independence

### 2023–24 EC3 Regular — Q1C — 3 Marks

Suppose **a, b, c are linearly independent**. Prove that:

**{b-c, a+c, a-b}**

is linearly independent.

### What is the examiner testing?

Exactly the definition of linear independence.

Define:

- v₁ = b - c
- v₂ = a + c
- v₃ = a - b

To prove these are independent, begin with:

**α₁v₁ + α₂v₂ + α₃v₃ = 0**

Substitute:

**α₁(b-c) + α₂(a+c) + α₃(a-b) = 0**

Expand and group the coefficients of a, b and c:

**(α₂+α₃)a + (α₁-α₃)b + (α₂-α₁)c = 0**

We are given that a, b and c are linearly independent.

Therefore each coefficient must be zero:

1. α₂ + α₃ = 0
2. α₁ - α₃ = 0
3. α₂ - α₁ = 0

From equations 2 and 3:

**α₁ = α₂ = α₃**

Using equation 1:

**2α₁ = 0**

Therefore:

**α₁ = α₂ = α₃ = 0**

Hence:

> **{b-c, a+c, a-b} is linearly independent.**

### Exam Pattern to Remember

Whenever the question says:

> **Prove these vectors are linearly independent**

start with:

**α₁v₁ + α₂v₂ + ... + αₙvₙ = 0**

and prove:

**α₁ = α₂ = ... = αₙ = 0**

---

# Exam Question 2 — Equality of Two Spans

A previous MFML comprehensive question gives:

**v₁ + v₂ + v₃ = 0**

and asks you to show:

> **span{v₁,v₂} = span{v₂,v₃}**

From the given relation:

**v₁ = -v₂ - v₃**

Therefore v₁ can be generated using v₂ and v₃.

So:

**span{v₁,v₂} ⊆ span{v₂,v₃}**

Similarly:

**v₃ = -v₁ - v₂**

Therefore v₃ can be generated using v₁ and v₂.

So:

**span{v₂,v₃} ⊆ span{v₁,v₂}**

Since both inclusions are true:

> **span{v₁,v₂} = span{v₂,v₃}**

### Exam Pattern to Remember

To prove:

**span(A) = span(B)**

show both directions:

1. **span(A) ⊆ span(B)**
2. **span(B) ⊆ span(A)**

---

## 5. What is a Vector Space?

A vector space is a collection of objects where vector addition and scalar multiplication behave properly and linear combinations remain inside the collection.

For intuition, R² contains vectors such as:

- (1,2)
- (-5,7)
- (0,0)

If u and v belong to R² and α and β are real numbers, then:

**αu + βv also belongs to R².**

The important point is that **vectors do not have to be ordinary columns of numbers**.

Matrices, functions and polynomials can themselves form vector spaces.

---

## 6. What is a Subspace?

A **subspace** is a smaller vector space living inside a larger vector space.

To prove M is a subspace of V, a convenient test is:

1. The zero vector/object belongs to M.
2. M is closed under addition.
3. M is closed under scalar multiplication.

Equivalently, for arbitrary A and B in M and scalars α and β, prove:

> **αA + βB also belongs to M.**

---

# Exam Question 3 — Matrices as Vectors and the Subspace Test

### MFML/MFDS Comprehensive Regular 2025–26 — Q1(B) — 6 Marks total

Consider the set:

**M = {A in R^(2×2) such that A = -Aᵀ}**

The first part asks you to prove that M is a subspace of the vector space of all 2×2 real matrices.

### First understand A = -Aᵀ

Let:

```text
A = | a  b |
    | c  d |
```

Then:

```text
Aᵀ = | a  c |
     | b  d |
```

The condition **A = -Aᵀ** implies:

- a = -a → a = 0
- d = -d → d = 0
- c = -b

So every matrix in M has the form:

```text
A = |  0   b |
    | -b   0 |
```

or equivalently:

```text
        |  0   1 |
A = b × | -1   0 |
```

This observation will also help us find the basis and dimension.

### Prove closure

Take A and B in M.

Then:

- Aᵀ = -A
- Bᵀ = -B

Let:

**C = αA + βB**

Then:

**Cᵀ = (αA + βB)ᵀ**

**Cᵀ = αAᵀ + βBᵀ**

Using Aᵀ = -A and Bᵀ = -B:

**Cᵀ = -αA - βB = -C**

Therefore C satisfies the defining condition of M.

Hence:

> **M is a subspace.**

---

## 7. What is a Basis?

A **basis** must satisfy two conditions:

> **Basis = Linearly Independent + Spans the Entire Space**

For our skew-symmetric matrix space:

```text
        |  0   1 |
A = b × | -1   0 |
```

Therefore every element of M is generated by the single matrix:

```text
|  0   1 |
| -1   0 |
```

That matrix is nonzero and therefore a one-element set containing it is linearly independent.

So a basis for M is:

```text
{ |  0   1 | }
  | -1   0 |
```

---

## 8. What is Dimension?

The **dimension** of a vector space is the number of vectors in any basis of that space.

Examples:

- **dim(R²) = 2**
- **dim(R³) = 3**

Our skew-symmetric 2×2 matrix space has one basis matrix.

Therefore:

> **dim(M) = 1**

---

# Exam Question 4 — The Basis Trap

The same 2025–26 question asks whether the following two matrices form a basis for M:

```text
A₁ = |  0   1 |       A₂ = |  0   2 |
     | -1   0 |            | -2   0 |
```

Observe:

**A₂ = 2A₁**

Therefore they are **linearly dependent**.

They span M, but they are not independent.

Since:

> **Basis = Span + Independence**

one required condition fails.

Therefore:

> **The given set is NOT a basis for M.**

### Key intuition

This is exactly the same idea as the ordinary vectors:

- (1,2)
- (2,4)

The examiner has simply replaced ordinary vectors with matrices.

---

# Exam Question 5 — Linear Independence of Matrices

The same question asks whether these matrices are linearly independent:

```text
I = | 1  0 |        S = |  0   1 |
    | 0  1 |            | -1   0 |
```

Assume:

**αI + βS = 0**

Then:

```text
|  α    β |   =   | 0  0 |
| -β    α |       | 0  0 |
```

Therefore:

**α = 0 and β = 0**

Only the trivial solution exists.

Hence:

> **The two matrices are linearly independent.**

### Important subtlety

The identity matrix I is **not** in the skew-symmetric subspace M.

That does not matter for this part because the question asks whether the two matrices are linearly independent in the larger vector space of all 2×2 real matrices.

---

# Topic 1 Mental Map So Far

### Linear Combination

**a₁v₁ + ... + aₙvₙ**

means combining vectors using scalar coefficients.

### Span

**span{v₁,...,vₙ}**

means **everything that can be generated** from those vectors.

### Linear Independence

If:

**a₁v₁ + ... + aₙvₙ = 0**

then independence requires:

**a₁ = ... = aₙ = 0**

> **No vector is redundant.**

### Basis

> **Basis = Independent + Spans the Space**

### Dimension

> **Dimension = Number of vectors in a basis**

---

# Quick Exam Recognition Table

| If the question says... | First thing to think |
|---|---|
| Prove vectors are independent | Set α₁v₁ + ... + αₙvₙ = 0 |
| Show vectors are dependent | Find a non-trivial combination equal to zero |
| Prove two spans are equal | Prove inclusion in both directions |
| Prove something is a subspace | Check closure / arbitrary linear combination |
| Is this set a basis? | Check **span AND independence** |
| Find dimension | Find a basis, then count its elements |

---

# 9. Does Dimension Depend on the Field?

### Comprehensive Makeup — Q2(ii) — 2 Marks

The question asks:

> **Is the dimension of a vector space independent of the field?**

The answer is **No**.

But the important thing is to understand *why*.

## What is a Field?

When we write a linear combination such as:

**a₁v₁ + a₂v₂**

we need to know what values a₁ and a₂ are allowed to take.

That set of allowed scalars is called the **field**.

For MFML, the two most important fields are:

- **R = real numbers**
- **C = complex numbers**

Examples of real numbers:

- 2
- -5
- 0.7
- √2
- π

Examples of complex numbers:

- 2
- -5
- 3+i
- 2-7i

Every real number is also a complex number, but complex numbers additionally allow **i**, where:

**i² = -1**

---

## Why Can the Field Change the Dimension?

Take the set of complex numbers **C**.

We will treat exactly the same set in two different ways.

### Case 1 — C as a Vector Space over C

Now the allowed scalars are complex numbers.

Can every complex number be generated from the single basis element **1**?

Yes.

For example:

**3 + 4i = (3 + 4i) × 1**

The coefficient **3+4i** is allowed because the field is C.

Therefore a basis is:

**{1}**

So:

> **dim_C(C) = 1**

Read this as:

> Dimension of C as a vector space over C is 1.

---

### Case 2 — C as a Vector Space over R

Now the allowed scalars are **real numbers only**.

Can we generate **3+4i** using only the basis element 1?

No.

A real scalar times 1 can only produce a real number.

So we need two building blocks:

**{1, i}**

because:

**3 + 4i = 3(1) + 4(i)**

and both coefficients 3 and 4 are real.

Therefore:

> **dim_R(C) = 2**

So the same underlying set C has different dimensions depending on the field.

### Final Answer for the 2-Mark Question

> **No. Dimension can depend on the underlying field. For example, C considered as a vector space over C has basis {1}, so its dimension is 1. However, C considered as a vector space over R has basis {1,i}, so its dimension is 2. Hence dimension is not independent of the field.**

### Intuition to Remember

> **Dimension = number of independent building blocks required.**

The field determines what scalar coefficients are allowed.

If complex coefficients are allowed, one building block is enough:

**(3+4i) × 1**

If only real coefficients are allowed, two building blocks are needed:

**3 × 1 + 4 × i**

---

# 10. Null Space

For a matrix **A**, the null space is the set of all vectors x satisfying:

**Ax = 0**

So:

> **Null Space = all input vectors that the matrix sends to the zero vector.**

We write:

**N(A) = {x : Ax = 0}**

If A has columns C₁, C₂, ..., Cₙ and:

**x = (x₁, x₂, ..., xₙ)ᵀ**

then:

**Ax = x₁C₁ + x₂C₂ + ... + xₙCₙ**

Therefore:

**Ax = 0**

means:

**x₁C₁ + x₂C₂ + ... + xₙCₙ = 0**

So a null-space vector is literally a set of coefficients showing a **linear dependence among the columns**.

---

## Tiny Example

Suppose:

- C₁ = (1,2)
- C₂ = (2,4)

Since:

**C₂ = 2C₁**

we can write:

**2C₁ - C₂ = 0**

So the coefficient vector:

**x = (2,-1)ᵀ**

satisfies:

**Ax = 0**

Therefore:

> **(2,-1)ᵀ belongs to the null space of A.**

This is the same linear-dependence idea we already know.

---

# Exam Question 6 — Null Space from Column Relations

### 2023–24 EC3 Regular — Q3A — 2 Marks

For a 6×6 matrix, the columns satisfy:

**C₁ = C₂ + C₃ + C₄ + C₅ + C₆**

and also:

**C₁ = 2C₂**

Two null-space vectors are:

- **[1,-2,0,0,0,0]ᵀ**
- **[-1,0,2,2,2,2]ᵀ**

### Candidate 1

Take:

**x = [1,-2,0,0,0,0]ᵀ**

Then:

**Ax = C₁ - 2C₂**

But C₁ = 2C₂.

Therefore:

**Ax = 0**

Hence:

> **[1,-2,0,0,0,0]ᵀ belongs to N(A).**

### Candidate 2

Take:

**x = [-1,0,2,2,2,2]ᵀ**

Then:

**Ax = -C₁ + 2C₃ + 2C₄ + 2C₅ + 2C₆**

From:

**C₁ = C₂ + C₃ + C₄ + C₅ + C₆**

and:

**C₁ = 2C₂**

we get:

**C₂ = C₁/2**

Substituting:

**C₁ = C₁/2 + C₃ + C₄ + C₅ + C₆**

Therefore:

**C₃ + C₄ + C₅ + C₆ = C₁/2**

Multiplying by 2:

**2C₃ + 2C₄ + 2C₅ + 2C₆ = C₁**

Hence:

**-C₁ + 2C₃ + 2C₄ + 2C₅ + 2C₆ = 0**

Therefore:

> **[-1,0,2,2,2,2]ᵀ also belongs to N(A).**

### Exam Pattern to Remember

Whenever a question gives **relationships among matrix columns**, convert them into:

**column relation → coefficients → null-space vector**

For example:

**C₁ = 3C₂**

means:

**C₁ - 3C₂ = 0**

so:

**[1,-3,0,...,0]ᵀ belongs to N(A)**

Similarly:

**C₁ = C₂ + C₃**

means:

**C₁ - C₂ - C₃ = 0**

so:

**[1,-1,-1,0,...,0]ᵀ belongs to N(A)**

### Connection to Rank

If there is a nonzero vector x such that:

**Ax = 0**

then the columns of A are linearly dependent.

Therefore:

> **Nontrivial null space → column dependence → rank is smaller than the number of columns.**

This leads directly to the Rank–Nullity Theorem.

---

# 11. What is Rank?

For a matrix **A**, rank tells us:

> **How many linearly independent columns (or rows) the matrix has.**

Equivalent ways to understand rank:

- number of independent columns
- number of independent rows
- number of pivots in RREF
- dimension of the column space

All of these give the same number.

### Tiny Example

Suppose:

```text
A = | 1  2 |
    | 2  4 |
```

Column 2 is:

**C₂ = 2C₁**

So only one column gives a genuinely new direction.

Therefore:

> **rank(A) = 1**

---

# 12. What is Nullity?

Nullity means:

> **Dimension of the null space.**

So if the null space has two independent basis vectors, then:

> **nullity(A) = 2**

This gives one of the most important formulas in linear algebra:

> **Rank + Nullity = Number of Columns**

For an m × n matrix:

> **rank(A) + nullity(A) = n**

This is the **Rank–Nullity Theorem**.

---

## Why Does Rank + Nullity = Number of Columns Make Sense?

Suppose A has 5 columns.

If 3 directions are independent, then:

**rank = 3**

The remaining freedom in solving:

**Ax = 0**

accounts for:

**5 - 3 = 2**

independent free directions.

So:

**nullity = 2**

Hence:

**3 + 2 = 5**

---

# Exam Question 7 — Special Matrix Rank

### Comprehensive Makeup — Q2(i) — 2 Marks

For a matrix with entries:

**a_jk = j + k - 1**

find its rank.

The same question also considers:

**a_jk = j + k - α**

### Step 1 — Understand the Column Structure

Take a 4×4 example for:

**a_jk = j + k - 1**

Then:

**C₁ = [1,2,3,4]ᵀ**

**C₂ = [2,3,4,5]ᵀ**

**C₃ = [3,4,5,6]ᵀ**

**C₄ = [4,5,6,7]ᵀ**

Let:

**1 = [1,1,1,1]ᵀ**

Then:

**C₂ = C₁ + 1**

**C₃ = C₁ + 2·1**

**C₄ = C₁ + 3·1**

In general:

> **C_k = C₁ + (k-1)·1**

So every column can be generated using only two vectors:

- C₁
- the all-ones vector 1

Therefore:

> **rank(A) ≤ 2**

Now ask whether C₁ and the all-ones vector are linearly independent.

They are, because C₁ is not a scalar multiple of the all-ones vector.

Therefore:

> **rank(A) = 2**

### Modified Matrix: a_jk = j + k - α

For this matrix, the k-th column is:

**C_k = [1+k-α, 2+k-α, 3+k-α, ...]ᵀ**

Again:

> **C_k = C₁ + (k-1)·1**

So the same structure remains.

Therefore, for the usual matrix size greater than 1:

> **rank(A) = 2**

The shift by α does not change the essential rank structure.

---

## Why This Is an Important Exam Pattern

The examiner is not expecting brute-force determinant expansion.

The intended idea is:

> **Look for a simple relationship between columns.**

Once you notice:

**C_k = C₁ + (k-1)·1**

the rank question is almost solved.

This is a classic **structure-recognition** question.

---

## Connection with Rank–Nullity

If an n-column matrix has:

**rank = 2**

then:

**nullity = n - 2**

For example, if the matrix is 6×6:

**rank = 2**

and therefore:

**nullity = 6 - 2 = 4**

So its null space has 4 independent basis vectors.

---

# Exam Pattern to Remember for Structured Matrices

If a question defines matrix entries using a formula such as:

**a_jk = f(j) + g(k)**

ask:

> **Can every column be written using only a few fixed vectors?**

If yes, the rank is bounded by the number of those fixed vectors.

Here:

**a_jk = j + k - 1**

is essentially:

**row-dependent part + column-dependent part**

which is why the rank collapses to 2.

---

# Quick Checkpoint — Rank and Nullity

At this point you should know:

- **Rank** = number of independent columns/rows
- **Nullity** = dimension of the null space
- **Rank + Nullity = number of columns**
- structured matrices often have low rank
- column formulas can be more useful than determinant calculations

## Next Concept

The next natural step is **RREF and pivots**, because one of the remaining actual MFML questions asks about **two students obtaining the same RREF and who is correct**.

That will connect:

**RREF → pivots → rank → free variables → nullity → uniqueness of RREF**
