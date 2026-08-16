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

So the same set C has different dimensions depending on the field.

### Final Exam Answer

> **No. Dimension can depend on the underlying field. For example, C considered as a vector space over C has basis {1}, so its dimension is 1. However, C considered as a vector space over R has basis {1,i}, so its dimension is 2. Hence dimension is not independent of the field.**

---

# 10. What is Null Space?

For a matrix A, the null space is the set of all vectors x satisfying:

**Ax = 0**

So:

> **Null Space = all input vectors that the matrix sends to the zero vector.**

We write it conceptually as:

**N(A) = {x : Ax = 0}**

If A has columns C₁, C₂, ..., Cₙ and

**x = (x₁,x₂,...,xₙ)ᵀ**

then:

**Ax = x₁C₁ + x₂C₂ + ... + xₙCₙ**

Therefore:

**Ax = 0**

means:

**x₁C₁ + x₂C₂ + ... + xₙCₙ = 0**

So a null-space vector is literally a set of coefficients showing a **linear dependence among the columns**.

### Tiny Example

Suppose:

- C₁ = (1,2)
- C₂ = (2,4)

Since:

**C₂ = 2C₁**

we can write:

**2C₁ - C₂ = 0**

So the coefficient vector:

**x = (2,-1)ᵀ**

satisfies Ax = 0.

Therefore:

> **(2,-1)ᵀ belongs to the null space of A.**

---

# Actual MFML Null-Space Question

The categorized bank contains a 6×6 matrix whose columns satisfy:

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

Given C₁ = 2C₂:

**Ax = 0**

Therefore:

> **[1,-2,0,0,0,0]ᵀ is in N(A).**

### Candidate 2

Take:

**x = [-1,0,2,2,2,2]ᵀ**

Then:

**Ax = -C₁ + 2C₃ + 2C₄ + 2C₅ + 2C₆**

From:

**C₁ = C₂ + C₃ + C₄ + C₅ + C₆**

and:

**C₁ = 2C₂**

we have:

**C₂ = C₁/2**

so:

**C₃ + C₄ + C₅ + C₆ = C₁/2**

Multiplying by 2:

**2C₃ + 2C₄ + 2C₅ + 2C₆ = C₁**

Hence:

**-C₁ + 2C₃ + 2C₄ + 2C₅ + 2C₆ = 0**

Therefore:

> **[-1,0,2,2,2,2]ᵀ is also in N(A).**

### Exam Pattern to Remember

Whenever you are given relationships among columns, convert them into a null-space vector.

Example:

**C₁ = 3C₂**

means:

**C₁ - 3C₂ = 0**

so:

**[1,-3,0,...,0]ᵀ belongs to N(A).**

Likewise:

**C₁ = C₂ + C₃**

means:

**C₁ - C₂ - C₃ = 0**

so:

**[1,-1,-1,0,...,0]ᵀ belongs to N(A).**

---

# 11. Rank and Nullity

## What is Rank?

For a matrix A, rank tells us:

> **How many linearly independent columns or rows the matrix has.**

Equivalent interpretations:

- number of independent columns
- number of independent rows
- number of pivots in RREF
- dimension of the column space

### Tiny Example

```text
A = | 1  2 |
    | 2  4 |
```

Column 2 satisfies:

**C₂ = 2C₁**

so there is only one independent column.

Therefore:

> **rank(A) = 1**

## What is Nullity?

Nullity means:

> **Dimension of the null space.**

If the null space has two independent basis vectors, then:

> **nullity(A) = 2**

## Rank–Nullity Theorem

For an m×n matrix:

> **rank(A) + nullity(A) = n**

where n is the number of columns.

Example: if a matrix has 5 columns and rank 3, then:

**nullity = 5 - 3 = 2**

---

# Actual MFML Rank Question — a_jk = j + k - 1

The Comprehensive Makeup paper asks for the rank of a matrix with entries:

**a_jk = j + k - 1**

and also asks about the modified form:

**a_jk = j + k - α**

Consider a 4×4 example for the first case.

The columns are:

- C₁ = [1,2,3,4]ᵀ
- C₂ = [2,3,4,5]ᵀ
- C₃ = [3,4,5,6]ᵀ
- C₄ = [4,5,6,7]ᵀ

Let **1** denote the all-ones vector:

**1 = [1,1,1,1]ᵀ**

Then:

- C₂ = C₁ + 1
- C₃ = C₁ + 2·1
- C₄ = C₁ + 3·1

In general:

> **C_k = C₁ + (k-1)·1**

So every column can be generated using only two vectors:

- C₁
- 1

Therefore:

**rank(A) ≤ 2**

Since C₁ is not a scalar multiple of the all-ones vector, these two vectors are linearly independent.

Hence:

> **rank(A) = 2**

## Modified Form — a_jk = j + k - α

For this matrix, the same column relationship survives:

> **C_k = C₁ + (k-1)·1**

Therefore the rank is again:

> **rank(A) = 2**

for the ordinary nontrivial matrix sizes considered in the question.

### Connection to Nullity

If the matrix has n columns and rank 2, then:

> **nullity(A) = n - 2**

For a 6×6 matrix:

**nullity = 6 - 2 = 4**

### Exam Pattern to Remember

If matrix entries are given by a formula such as:

**a_jk = f(j) + g(k)**

look for a way to express every column using only a few fixed vectors.

That often reveals the rank immediately without determinant expansion.

---

# 12. RREF, Pivots and Why RREF is Unique

## What is RREF?

RREF means:

> **Reduced Row Echelon Form**

It is the most simplified row-equivalent form of a matrix.

For example:

```text
A = | 1  2 |
    | 2  4 |
```

Perform:

**R₂ → R₂ - 2R₁**

We obtain:

```text
| 1  2 |
| 0  0 |
```

This matrix is already in RREF.

## What Makes a Matrix RREF?

A matrix is in RREF if:

1. Every nonzero row has a leading **1**.
2. Each leading 1 is the **only nonzero entry in its column**.
3. Leading 1s move to the right as we go down the rows.
4. Any all-zero rows are at the bottom.

Example:

```text
| 1  0   3 |
| 0  1  -2 |
| 0  0   0 |
```

The leading 1s are called **pivots**.

There are 2 pivots, therefore:

> **rank = 2**

## Why Do Pivots Matter?

Suppose:

```text
RREF(A) =
| 1  0   2  0 |
| 0  1  -1  0 |
| 0  0   0  1 |
```

There are pivots in columns:

- 1
- 2
- 4

Therefore:

> **rank(A) = 3**

Column 3 has no pivot, so the corresponding variable is **free**.

A has 4 columns, therefore by Rank–Nullity:

**nullity = 4 - 3 = 1**

So:

> **Number of free variables = nullity**

---

# Actual MFML Conceptual Question — Is RREF Unique?

The Comprehensive Makeup question includes a 2-mark conceptual part involving two students obtaining RREFs of the same matrix.

The key theorem is:

> **Every matrix has one unique RREF.**

Different sequences of row operations are allowed.

For example, Student A may:

- swap rows first,
- then eliminate,
- then scale.

Student B may:

- scale first,
- then eliminate,
- then swap.

Their intermediate matrices may look different.

But if both continue correctly all the way to RREF, they must end at exactly the same matrix.

> **Different row-operation paths are possible, but the final RREF is unique.**

## REF is Not Unique — RREF is Unique

This distinction is an exam trap.

A matrix such as:

```text
| 1  2 |
| 0  3 |
```

can be in row echelon form (REF).

A scaled version such as:

```text
| 2  4 |
| 0  6 |
```

can also be a valid REF form.

So REF is not necessarily unique.

However, once fully reduced, the RREF is unique.

Remember:

> **REF → not unique**
>
> **RREF → unique**

---

## Simple Example — Two Different Routes, Same RREF

Take:

```text
A = | 1  2 |
    | 2  4 |
```

### Student A

Do:

**R₂ → R₂ - 2R₁**

Result:

```text
| 1  2 |
| 0  0 |
```

### Student B

First do:

**R₁ → 2R₁**

giving:

```text
| 2  4 |
| 2  4 |
```

Then:

**R₂ → R₂ - R₁**

```text
| 2  4 |
| 0  0 |
```

Then scale:

**R₁ → (1/2)R₁**

giving:

```text
| 1  2 |
| 0  0 |
```

Both students took different routes but obtained the same RREF.

## What If Two Students Claim Different RREFs?

Suppose Student A says:

```text
| 1  0   2 |
| 0  1  -1 |
```

while Student B says:

```text
| 1  0   3 |
| 0  1  -1 |
```

for the same original matrix.

Both cannot be correct.

Why?

> **Because RREF is unique.**

At least one student made an error.

---

## Relationship Between RREF and Solving Ax = b

Consider:

```text
A = | 1  2  3 |
    | 2  4  6 |
```

Its RREF is:

```text
| 1  2  3 |
| 0  0  0 |
```

There is only one pivot.

Therefore:

> **rank = 1**

Number of columns = 3.

Therefore:

> **nullity = 3 - 1 = 2**

Hence solving:

**Ax = 0**

will involve **2 free variables**.

---

## Pivot Columns vs Original Columns

Suppose RREF(A) has pivots in columns 1 and 3.

Then columns 1 and 3 of the **original matrix A** form a basis for the column space.

Do not use the columns of RREF(A) as the basis for the original column space.

Row operations preserve row-equivalence and reveal pivot locations, but they change the actual column vectors.

So the exam procedure is:

1. Compute or inspect RREF.
2. Identify pivot column numbers.
3. Go back to the original matrix.
4. Take those original columns as the column-space basis.

---

# Quick Exam Memory Map — RREF

| If you see... | Think... |
|---|---|
| Find rank | Count pivots in RREF |
| Find nullity | Number of columns - rank |
| How many free variables? | Nullity |
| Two different RREFs for same matrix? | Impossible; RREF is unique |
| Two different REFs? | Possible; REF is not unique |
| Basis of column space | Find pivot positions in RREF, take those columns from original A |

## Key Theorem to Memorize

> **Every matrix is row-equivalent to one and only one reduced row echelon form.**

---

# 13. General Solution of Ax = b

This section combines **particular solution + null space + rank + free variables**.

### MFML/MFDS Comprehensive Regular 2025–26 — Q1(A)(i) — 2 Marks

The question gives:

- **A = [C₁, C₂, C₃, C₄]**
- **rank(A) = 2**
- **C₂ = 3C₁**
- **C₄ = 2C₁ + 3C₃**
- a particular solution of **Ax = b** is **xₚ = (1,0,1,0)ᵀ**

and asks for the **general solution** of Ax = b.

## Master Formula

If xₚ is one particular solution of:

**Ax = b**

and xₙ is any solution of:

**Ax = 0**

then:

> **General solution = Particular solution + Null-space solution**

or:

**x = xₚ + xₙ**

Why?

Because:

**A(xₚ + xₙ) = Axₚ + Axₙ = b + 0 = b**

So every null-space vector can be added to a particular solution without changing the output b.

---

## Step 1 — Use C₂ = 3C₁

Rearrange:

**C₂ - 3C₁ = 0**

or:

**-3C₁ + C₂ = 0**

Therefore one null-space vector is:

**n₁ = (-3,1,0,0)ᵀ**

because:

**A n₁ = -3C₁ + C₂ = 0**

---

## Step 2 — Use C₄ = 2C₁ + 3C₃

Move everything to one side:

**-2C₁ - 3C₃ + C₄ = 0**

Therefore another null-space vector is:

**n₂ = (-2,0,-3,1)ᵀ**

because:

**A n₂ = -2C₁ - 3C₃ + C₄ = 0**

---

## Step 3 — Check How Many Null-Space Basis Vectors Are Needed

A has 4 columns and:

**rank(A) = 2**

Using Rank–Nullity:

**rank + nullity = number of columns**

So:

**2 + nullity = 4**

Therefore:

> **nullity(A) = 2**

We already found two independent null-space vectors n₁ and n₂, so they form a basis for N(A).

---

## Step 4 — Write the Complete Null-Space Solution

Any vector in N(A) can be written as:

**xₙ = s n₁ + t n₂**

where s,t ∈ R.

Therefore:

**xₙ = s(-3,1,0,0)ᵀ + t(-2,0,-3,1)ᵀ**

---

## Step 5 — Add the Particular Solution

The particular solution is:

**xₚ = (1,0,1,0)ᵀ**

Therefore:

> **x = (1,0,1,0)ᵀ + s(-3,1,0,0)ᵀ + t(-2,0,-3,1)ᵀ**

where s,t ∈ R.

Component-wise:

- **x₁ = 1 - 3s - 2t**
- **x₂ = s**
- **x₃ = 1 - 3t**
- **x₄ = t**

So equivalently:

> **x = (1 - 3s - 2t, s, 1 - 3t, t)ᵀ**, where s,t ∈ R.

---

## Compact 2-Mark Exam Answer

> Since C₂ = 3C₁, we have -3C₁ + C₂ = 0, giving null-space vector (-3,1,0,0)ᵀ. Since C₄ = 2C₁ + 3C₃, we have -2C₁ - 3C₃ + C₄ = 0, giving (-2,0,-3,1)ᵀ. Since rank(A)=2 and A has 4 columns, nullity(A)=2, so these form a null-space basis. Hence:
>
> **x = (1,0,1,0)ᵀ + s(-3,1,0,0)ᵀ + t(-2,0,-3,1)ᵀ**, s,t ∈ R.

---

## Why This Question Matters

This single problem connects several ideas:

**column dependence**

→ gives null-space vectors

→ rank tells how many independent null-space directions are needed

→ a particular solution gives one valid point

→ the null space gives all directions that can be added without changing b

So geometrically:

> **The solution set of Ax=b is one particular solution shifted by the null space.**

A useful memory rule is:

> **General solution = one solution + all zero-effect directions.**

or simply:

> **x = xₚ + N(A)**

---

# Next Step

The second part of the same 2025–26 MFML question asks you to **find b if RREF(A)=Â**.

That is the natural next step because it introduces a subtle but important distinction between:

- the **original matrix A**,
- its **RREF**, and
- how a known particular solution is used to determine b.
