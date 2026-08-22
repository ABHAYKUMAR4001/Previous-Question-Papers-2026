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

# 14. Finding b from a Known Solution and Understanding RREF

### MFML/MFDS Comprehensive Regular 2025–26 — Q1(A)(ii) — 2 Marks

The categorized question says to find **b** when **RREF(A)=Â**, but the exact displayed matrix Â is not present in the categorized Markdown text. Therefore this section focuses on the exact concept and method rather than inventing the missing matrix entries.

We already know that:

**xₚ = (1,0,1,0)ᵀ**

is a particular solution of:

**Ax = b**

Therefore, by definition:

> **b = Axₚ**

Since:

**A = [C₁ C₂ C₃ C₄]**

and:

```text
xₚ = | 1 |
     | 0 |
     | 1 |
     | 0 |
```

matrix multiplication gives:

**Axₚ = 1C₁ + 0C₂ + 1C₃ + 0C₄**

Hence:

> **b = C₁ + C₃**

This result is for the **original matrix A**.

---

## Why Matrix Multiplication Works This Way

If:

**A = [C₁ C₂ ... Cₙ]**

and:

**x = (x₁,x₂,...,xₙ)ᵀ**

then:

> **Ax = x₁C₁ + x₂C₂ + ... + xₙCₙ**

So the components of x are simply the coefficients used to combine the columns of A.

For:

**xₚ = (1,0,1,0)ᵀ**

we take:

- 1 × C₁
- 0 × C₂
- 1 × C₃
- 0 × C₄

therefore:

> **b = C₁ + C₃**

This also gives a very important span interpretation:

> **If Ax=b has a solution, then b must lie in the span of the columns of A.**

---

## The Important RREF Subtlety

Suppose:

**RREF(A) = Â**

Can we simply write:

**b = Âxₚ**?

> **No — not for the original b.**

When row operations transform A into Â, the same row operations must also be applied to b.

So the original system:

**Ax = b**

becomes a row-equivalent system:

**Âx = b̂**

where b̂ is the transformed right-hand side.

Therefore:

> **Âxₚ = b̂**

not necessarily the original b.

---

## Simple Example

Suppose:

```text
A = | 1  1 |
    | 2  2 |
```

and:

```text
b = | 3 |
    | 6 |
```

Apply the row operation:

**R₂ → R₂ - 2R₁**

Then:

```text
Â = | 1  1 |
    | 0  0 |
```

but the right-hand side becomes:

```text
b̂ = | 3 |
     | 0 |
```

So:

> **b ≠ b̂**

although the original and row-reduced systems have exactly the same solution set.

This is why we must distinguish between the original RHS vector and the transformed RHS vector.

---

## What Can We Calculate Using Â?

If the exam gives the actual matrix:

**Â = RREF(A)**

and asks for the RHS of the row-reduced system, then:

> **b̂ = Âxₚ**

Since:

**xₚ = (1,0,1,0)ᵀ**

this becomes:

> **b̂ = Ĉ₁ + Ĉ₃**

where Ĉ₁ and Ĉ₃ are columns 1 and 3 of Â.

So once Â is visible, the numerical calculation is immediate: simply add columns 1 and 3 of Â.

---

## Illustrative Example Only

Suppose, only as an example:

```text
Â = | 1  3  0   2 |
    | 0  0  1  -1 |
    | 0  0  0   0 |
    | 0  0  0   0 |
```

Then:

```text
Ĉ₁ = | 1 |       Ĉ₃ = | 0 |
     | 0 |            | 1 |
     | 0 |            | 0 |
     | 0 |            | 0 |
```

Therefore:

```text
b̂ = Ĉ₁ + Ĉ₃
   = | 1 |
     | 1 |
     | 0 |
     | 0 |
```

This example is only to demonstrate the method; it is not the missing exam matrix.

---

## One Very Useful Rule

Whenever you see:

**A = [C₁ C₂ ... Cₙ]**

and:

**x = (x₁,x₂,...,xₙ)ᵀ**

immediately think:

> **Ax = x₁C₁ + x₂C₂ + ... + xₙCₙ**

This single idea helps with:

- finding b,
- null-space questions,
- column dependence,
- span,
- and general solutions.

---

## Complete Connection

### Ax = b

means:

**x₁C₁ + x₂C₂ + ... + xₙCₙ = b**

### Ax = 0

means:

**x₁C₁ + x₂C₂ + ... + xₙCₙ = 0**

which describes column dependence and the null space.

### Ax = b has a solution

means:

> **b lies in the span of the columns of A.**

### Number of independent columns

means:

> **rank**

### Number of independent zero-effect directions

means:

> **nullity**

So span, dependence, null space, rank, RREF and solving Ax=b are all different views of the same matrix structure.

---

## Exam Shortcut

Given:

**xₚ = (1,0,1,0)ᵀ**

immediately write:

> **b = Axₚ = C₁ + C₃**

If the question instead asks for the RHS associated with the row-reduced system:

> **b̂ = Âxₚ = Ĉ₁ + Ĉ₃**

Once the actual Â from the exam paper is available, this becomes a direct column-addition calculation.

---

# Topic 2 — Eigenvalues & Eigenvectors

## 1. What is an Eigenvector?

A nonzero vector v is an eigenvector of A if:

> **Av = λv**

for some scalar λ, called the eigenvalue.

The matrix changes the magnitude of v, but not its direction line.

## 2. Geometric Intuition

If:

- λ > 1, the eigenvector is stretched.
- 0 < λ < 1, it is shrunk.
- λ < 0, it reverses direction and scales.
- λ = 0, it collapses to the zero vector.

## 3. Why det(A-λI)=0?

From:

**Av = λv**

we get:

**(A-λI)v = 0**

For a nonzero v to exist, A-λI must have a nontrivial null space, hence it must be singular.

Therefore:

> **det(A-λI)=0**

This is the characteristic equation.

## 4. Basic 2×2 Example

```text
A = | 4  1 |
    | 2  3 |
```

Then:

**det(A-λI) = (4-λ)(3-λ)-2 = λ²-7λ+10**

So:

**(λ-5)(λ-2)=0**

Hence the eigenvalues are:

> **λ=5 and λ=2**

For λ=5:

**(A-5I)v=0** gives y=x, so one eigenvector is:

> **(1,1)ᵀ**

For λ=2:

**(A-2I)v=0** gives y=-2x, so one eigenvector is:

> **(1,-2)ᵀ**

## 5. Eigenspace

The eigenspace for λ is:

> **E_λ = N(A-λI)**

So eigenspace questions are null-space questions in disguise.

## 6. Basis and Dimension of an Eigenspace

If:

**E₅ = span{(1,1)ᵀ}**

then a basis is:

**{(1,1)ᵀ}**

and:

> **dim(E₅)=1**

## 7. Triangular Matrix Shortcut

For any upper- or lower-triangular matrix:

> **The eigenvalues are the diagonal entries.**

This is an important exam shortcut.

### Why does it work?

For a triangular matrix, **A-λI** is still triangular.

Its determinant is the product of its diagonal terms:

**det(A-λI) = (a₁₁-λ)(a₂₂-λ)...(aₙₙ-λ)**

So the roots are exactly the diagonal entries.

---

## 8. MFML Pattern — Trace and Determinant

A previous MFML question has eigenvalues:

**3, -3, 14**

and asks for quantities involving **C⁶** and **C⁷**.

Two critical rules are:

> **Trace = sum of eigenvalues**

and:

> **Determinant = product of eigenvalues**

So:

**trace(C) = 3 + (-3) + 14 = 14**

## 9. Eigenvalues of a Matrix Power

If λ is an eigenvalue of C, then:

> **λᵏ is an eigenvalue of Cᵏ**

Therefore the eigenvalues of C⁶ are:

- 3⁶
- (-3)⁶
- 14⁶

Hence:

> **Trace(C⁶) = 3⁶ + (-3)⁶ + 14⁶**

Since the exponent is even:

**(-3)⁶ = 3⁶**

so equivalently:

> **Trace(C⁶) = 2·3⁶ + 14⁶**

## 10. Determinant of a Matrix Power

The determinant of C is:

**det(C) = 3 × (-3) × 14 = -126**

Also:

> **det(Cᵏ) = [det(C)]ᵏ**

Therefore:

> **det(C⁷) = (-126)⁷**

This is exactly the kind of shortcut expected in the exam.

---

# Quick Exam Recognition Table — Eigenvalues

| If you see... | Think immediately |
|---|---|
| Av = λv | Eigenvector/eigenvalue definition |
| Find eigenvalues | det(A-λI)=0 |
| Find eigenvectors | Solve (A-λI)v=0 |
| Find eigenspace | N(A-λI) |
| Triangular matrix | Diagonal entries are eigenvalues |
| Trace | Sum of eigenvalues |
| Determinant | Product of eigenvalues |
| Aᵏ | Eigenvalues become λᵏ |
| Basis of eigenspace | Basis of N(A-λI) |
| Dimension of eigenspace | Number of independent basis vectors |

---

# Actual MFML Eigenspace Question — 2025–26

Consider the lower-triangular matrix:

```text
A =
| -2   0   0   0 |
| -1   3   0   0 |
|  0  -1  -1   0 |
|  1   1   0   5 |
```

Because A is lower triangular, its eigenvalues are simply the diagonal entries:

> **λ = -2, 3, -1, 5**

The largest eigenvalue is:

> **λ = 5**

## Find the Eigenspace for λ = 5

Solve:

**(A-5I)v=0**

with:

```text
v = |x₁|
    |x₂|
    |x₃|
    |x₄|
```

Then:

```text
A-5I =
| -7   0   0   0 |
| -1  -2   0   0 |
|  0  -1  -6   0 |
|  1   1   0   0 |
```

This gives:

- -7x₁ = 0 → x₁ = 0
- -x₁ - 2x₂ = 0 → x₂ = 0
- -x₂ - 6x₃ = 0 → x₃ = 0
- x₁ + x₂ = 0, already satisfied

There is no equation involving x₄, so x₄ is free.

Let:

**x₄ = t**

Then:

```text
v = |0|
    |0|
    |0|
    |t|
```

or:

> **v = t(0,0,0,1)ᵀ**

Therefore:

> **E₅ = span{(0,0,0,1)ᵀ}**

A basis is:

> **{(0,0,0,1)ᵀ}**

and:

> **dim(E₅)=1**

### Compact Exam Answer

> Since A is lower triangular, its eigenvalues are -2, 3, -1 and 5. The largest eigenvalue is 5. Solving (A-5I)v=0 gives x₁=x₂=x₃=0 and x₄ free. Hence E₅=span{(0,0,0,1)ᵀ}. A basis is {(0,0,0,1)ᵀ}, so dim(E₅)=1.

---

# Distinct Eigenvalues vs Orthogonal Eigenvectors

## Key Distinction

Eigenvectors corresponding to distinct eigenvalues are always:

> **Linearly independent**

but they are not necessarily:

> **Orthogonal**

## Counterexample

Take:

```text
A = | 1  1 |
    | 0  2 |
```

Since A is triangular, its eigenvalues are 1 and 2.

For λ=1, one eigenvector is:

> **v₁=(1,0)ᵀ**

For λ=2, one eigenvector is:

> **v₂=(1,1)ᵀ**

Their dot product is:

**v₁ᵀv₂ = 1**

which is not zero.

Therefore:

> **Distinct eigenvalues do not by themselves guarantee orthogonal eigenvectors.**

## Symmetric Matrix Theorem

If A is a real symmetric matrix and λ₁≠λ₂, then eigenvectors corresponding to λ₁ and λ₂ are orthogonal.

Suppose:

**Av₁=λ₁v₁**

and:

**Av₂=λ₂v₂**

Since A is symmetric:

**Aᵀ=A**

Then:

**v₁ᵀAv₂ = λ₂v₁ᵀv₂**

but also:

**v₁ᵀAv₂ = (Av₁)ᵀv₂ = λ₁v₁ᵀv₂**

Therefore:

**(λ₁-λ₂)v₁ᵀv₂=0**

Since λ₁≠λ₂:

> **v₁ᵀv₂=0**

Hence the eigenvectors are orthogonal.

## Orthogonal Matrix

A square matrix Q is orthogonal if:

> **QᵀQ=I**

Equivalently:

> **Q⁻¹=Qᵀ**

Its columns form an orthonormal set.

For a real symmetric matrix, eigenvectors can be chosen orthonormal and arranged as the columns of Q.

Then:

> **A = QDQᵀ**

This is orthogonal diagonalization.

## Exam Trap Summary

| Condition | Conclusion |
|---|---|
| Same eigenvalue | Eigenvectors may or may not be independent |
| Distinct eigenvalues | Eigenvectors are linearly independent |
| Symmetric matrix + distinct eigenvalues | Eigenvectors are orthogonal |

### Compact 2-Mark Answer

> Distinct eigenvalues guarantee linearly independent eigenvectors, but not necessarily orthogonal ones. Orthogonality is guaranteed for eigenvectors corresponding to distinct eigenvalues when the matrix is real symmetric.

---

# Algebraic Multiplicity, Geometric Multiplicity and Diagonalizability

## Algebraic Multiplicity

The algebraic multiplicity of an eigenvalue is the number of times it appears as a root of the characteristic polynomial.

Example:

**(λ-2)²(λ-5)=0**

Then:

- λ=2 has algebraic multiplicity 2
- λ=5 has algebraic multiplicity 1

## Geometric Multiplicity

The geometric multiplicity of λ is:

> **dim N(A-λI)**

So it is the dimension of the eigenspace corresponding to λ.

For every eigenvalue:

> **1 ≤ geometric multiplicity ≤ algebraic multiplicity**

## Why Multiplicity Matters

An n×n matrix is diagonalizable if it has n linearly independent eigenvectors.

Then:

> **A = PDP⁻¹**

where the columns of P are independent eigenvectors and D contains the corresponding eigenvalues.

## Distinct Eigenvalues Shortcut

If an n×n matrix has n distinct eigenvalues, then the corresponding eigenvectors are automatically linearly independent.

Therefore:

> **n distinct eigenvalues ⇒ diagonalizable**

## Repeated Eigenvalue but Still Diagonalizable

Consider:

```text
A = | 2  0 |
    | 0  2 |
```

The only eigenvalue is 2 with algebraic multiplicity 2.

Since A-2I=0, every vector in R² is an eigenvector for λ=2.

Thus:

> **geometric multiplicity = 2**

Therefore A is diagonalizable.

## Repeated Eigenvalue and Not Diagonalizable

Consider:

```text
A = | 2  1 |
    | 0  2 |
```

The eigenvalue is λ=2 with algebraic multiplicity 2.

Solve:

```text
A-2I = | 0  1 |
       | 0  0 |
```

This gives y=0 and x free.

Hence the eigenspace is:

> **span{(1,0)ᵀ}**

So:

> **geometric multiplicity = 1**

Since the 2×2 matrix has only one independent eigenvector:

> **A is not diagonalizable.**

## Diagonalizability Test

A matrix is diagonalizable if and only if the total number of independent eigenvectors is n.

Equivalently:

> **For every eigenvalue, geometric multiplicity = algebraic multiplicity.**

## Symmetric Matrix Shortcut

Every real symmetric matrix is:

> **Orthogonally diagonalizable**

so:

> **A = QDQᵀ**

Even repeated eigenvalues do not prevent diagonalization for a symmetric matrix.

## Exam Recognition Rules

### All eigenvalues distinct

Think:

> **Automatically diagonalizable.**

### Algebraic multiplicity = 3

Think:

> **Geometric multiplicity can be 1, 2 or 3.**

### Geometric multiplicity < algebraic multiplicity

Think:

> **Not diagonalizable.**

### Real symmetric matrix

Think:

> **Always orthogonally diagonalizable.**

## Compact Definitions for the Exam

> **Algebraic multiplicity** is the multiplicity of an eigenvalue as a root of the characteristic polynomial.

> **Geometric multiplicity** is the dimension of the corresponding eigenspace, i.e. dim N(A-λI).

> **A matrix is diagonalizable if it has n linearly independent eigenvectors. Equivalently, geometric multiplicity equals algebraic multiplicity for every eigenvalue.**

---

# Trace, Determinant, Singular Values and SVD Connection

## 1. Singular Value Decomposition

For a matrix A:

> **A = UΣVᵀ**

where:

- U contains the left singular vectors,
- V contains the right singular vectors,
- Σ contains the singular values σ₁, σ₂, ...

The singular values are always non-negative.

## 2. Key Eigenvalue Connection

The important identities are:

> **AᵀA = VΣ²Vᵀ**

and:

> **AAᵀ = UΣ²Uᵀ**

Therefore:

> **The eigenvalues of AᵀA are σ₁², σ₂², ...**

and the nonzero eigenvalues of AAᵀ are the same σᵢ² values.

## 3. Why Does AᵀA Give σ²?

Start from:

**A = UΣVᵀ**

Then:

**Aᵀ = VΣᵀUᵀ**

Therefore:

**AᵀA = VΣᵀUᵀUΣVᵀ**

Since U is orthogonal:

**UᵀU = I**

we get:

**AᵀA = VΣᵀΣVᵀ**

For the usual singular-value structure:

**ΣᵀΣ = Σ²**

so:

> **AᵀA = VΣ²Vᵀ**

Thus the columns of V are eigenvectors of AᵀA, and its eigenvalues are σᵢ².

## 4. Frobenius Norm

The Frobenius norm satisfies:

> **||A||_F² = sum of squares of all entries of A**

For SVD:

> **||A||_F² = σ₁² + σ₂² + ...**

Since Σ contains the singular values on its diagonal:

> **||Σ||_F² = σ₁² + σ₂² + ...**

Therefore:

> **||A||_F² = ||Σ||_F²**

## 5. Actual MFML Question Pattern

Suppose:

**A = UΣVᵀ**

and:

> **||Σ||_F² = γ**

Let:

**B = AᵀA**

Since the eigenvalues of B are σ₁², σ₂², ...:

**trace(B) = σ₁² + σ₂² + ...**

But:

**σ₁² + σ₂² + ... = ||Σ||_F² = γ**

Therefore:

> **trace(AᵀA) = γ**

So a statement claiming trace(AᵀA)=γ is correct.

A statement claiming trace(AᵀA)=√γ is incorrect.

## 6. Why Trace Appears

Remember:

> **Trace = sum of eigenvalues**

For AᵀA, the eigenvalues are σᵢ².

Hence:

> **trace(AᵀA) = Σσᵢ²**

So the following three quantities are the same:

> **trace(AᵀA) = ||A||_F² = Σσᵢ²**

## 7. What About AAᵀ?

Let:

**C = AAᵀ**

Its nonzero eigenvalues are also σ₁², σ₂², ...

Therefore:

> **trace(AAᵀ) = Σσᵢ² = γ**

So:

> **trace(AᵀA) = trace(AAᵀ) = γ**

not γ².

## 8. Why AᵀA and AAᵀ Share Nonzero Eigenvalues

Suppose:

**AᵀA v = λv**

with λ ≠ 0.

Multiply by A:

**AAᵀ(Av) = λ(Av)**

Therefore Av is an eigenvector of AAᵀ with the same eigenvalue λ.

Hence AᵀA and AAᵀ share the same nonzero eigenvalues.

## 9. Singular Values vs Eigenvalues

Eigenvalues of a general matrix may be:

- positive,
- negative,
- zero,
- or complex.

Singular values are always:

> **non-negative real numbers**

because:

> **σᵢ = √λᵢ(AᵀA)**

## 10. Simple Numerical Example

Take:

```text
A = | 3  0 |
    | 0  4 |
```

Then:

```text
AᵀA = | 9   0 |
      | 0  16 |
```

The eigenvalues of AᵀA are 9 and 16.

Therefore the singular values are:

> **σ₁=3, σ₂=4**

Now:

**||A||_F² = 3² + 4² = 25**

and:

**trace(AᵀA) = 9 + 16 = 25**

Therefore:

> **||A||_F² = trace(AᵀA) = σ₁² + σ₂²**

## 11. Rank Connection

The rank of A equals:

> **Number of nonzero singular values**

For example, if:

**Σ = diag(5,2,0,0)**

then:

> **rank(A)=2**

## 12. Exam Recognition Table

| If you see... | Think immediately |
|---|---|
| A = UΣVᵀ | SVD |
| Eigenvalues of AᵀA | σᵢ² |
| Eigenvalues of AAᵀ | Same nonzero σᵢ² |
| Singular values | √eigenvalues(AᵀA) |
| trace(AᵀA) | Sum of σᵢ² |
| ||A||_F² | Sum of σᵢ² |
| ||Σ||_F² | Sum of σᵢ² |
| rank(A) | Number of nonzero singular values |

## Compact MFML Answer

If:

**A = UΣVᵀ**, **||Σ||_F² = γ**, and **B=AᵀA**,

then:

> Since AᵀA = VΣ²Vᵀ, the eigenvalues of AᵀA are σᵢ². Hence **trace(AᵀA)=Σσᵢ²=||Σ||_F²=γ**. Similarly, **trace(AAᵀ)=γ**.

---

# Topic 3 — PCA & Dimensionality Reduction

## 1. Why PCA Exists

Suppose each data point has many features:

**x = (x₁, x₂, ..., x_D)**

Often, many features are correlated and the data effectively lies in a lower-dimensional subspace.

PCA asks:

> **Can we represent the data using fewer directions while preserving as much variance as possible?**

So the core goal is:

> **Dimensionality reduction while preserving variance.**

---

## 2. Variance Intuition

If a cloud of 2D data lies approximately along a diagonal line, then the spread along that diagonal is large while the spread perpendicular to it is small.

The first principal component chooses:

> **The direction along which the projected data has maximum variance.**

The second principal component is orthogonal to the first and captures the next-largest remaining variance.

---

## 3. Why Mean-Center the Data?

PCA studies variation around the mean rather than absolute location.

Example:

```text
(10,10)
(11,11)
(12,12)
```

Mean:

**μ = (11,11)**

Centered data:

```text
(-1,-1)
( 0, 0)
( 1, 1)
```

Therefore PCA normally starts by subtracting the mean.

---

## 4. Covariance Matrix

For mean-centered data matrix X, the covariance matrix is proportional to:

> **C = XᵀX**

Depending on convention, a factor such as 1/N or 1/(N-1) may be included.

That scalar factor changes eigenvalues but not eigenvector directions.

The covariance matrix describes how the features vary together.

---

## 5. PCA is an Eigenvalue Problem

The key PCA theorem is:

> **Principal components are eigenvectors of the covariance matrix.**

and:

> **The corresponding eigenvalues tell us how much variance each principal component captures.**

If:

**λ₁ ≥ λ₂ ≥ λ₃ ≥ ...**

then:

- PC1 is the eigenvector for λ₁
- PC2 is the eigenvector for λ₂
- and so on

Since the covariance matrix is symmetric, these eigenvectors can be chosen orthonormal.

---

# Actual MFML PCA Question — Maximum Variance Direction

### 2022–23 Makeup — Q1b — 2 Marks

The data is:

```text
X =
|  2  -1 |
| -2   1 |
| -4   2 |
|  4  -2 |
```

The question asks whether the maximum-variance direction is:

- [1,0]ᵀ
- [0,1]ᵀ
- or neither

Observe that every point satisfies:

> **y = -x/2**

So all points lie exactly on one line.

A direction vector for that line is:

> **(2,-1)ᵀ**

The normalized direction is:

> **(2/√5, -1/√5)ᵀ**

Therefore the maximum-variance direction is neither coordinate axis.

> **Correct answer: neither [1,0]ᵀ nor [0,1]ᵀ.**

The dominant principal direction is proportional to **(2,-1)ᵀ**.

### Exam Insight

If the data visibly lies on a line, you can often identify PC1 geometrically without calculating the covariance matrix.

---

## Formal Interpretation

For the same data, the covariance structure is proportional to:

```text
|  1    -1/2 |
| -1/2   1/4 |
```

Its dominant eigenvector points along:

> **(2,-1)ᵀ**

which matches the geometric answer.

---

# Actual MFML PCA Question — Explained Variance

### 2023–24 EC3 Regular — Q4B — 4 Marks

The covariance eigenvalues are:

**12, 6.8, 3.5, 1, 0.02, 0.01**

Total variance:

> **23.33**

The cumulative explained-variance ratio using the first k PCs is:

> **(λ₁ + λ₂ + ... + λ_k) / (sum of all eigenvalues)**

## 95% Variance

Top 1:

**12 / 23.33 ≈ 51.4%**

Top 2:

**(12 + 6.8) / 23.33 ≈ 80.6%**

Top 3:

**(12 + 6.8 + 3.5) / 23.33 ≈ 95.6%**

Therefore:

> **3 principal components are enough to retain at least 95% variance.**

## 99% Variance

The first 3 PCs give only about 95.6%.

Including the fourth eigenvalue:

**12 + 6.8 + 3.5 + 1 = 23.3**

and:

**23.3 / 23.33 ≈ 99.87%**

Therefore:

> **4 principal components are enough to retain at least 99% variance.**

---

## 6. Interpretation of Eigenvalue Size

In PCA:

> **Large eigenvalue = important high-variance direction**

> **Small eigenvalue = low-information direction**

For the eigenvalues:

**12, 6.8, 3.5, 1, 0.02, 0.01**

the final two directions contribute almost no variance.

This is why dimensionality reduction can discard them with little information loss.

---

## 7. PCA Projection

Suppose v₁ is a unit principal-component direction and x is a centered data point.

The scalar PCA coordinate is:

> **z = v₁ᵀx**

This tells us how far the point lies along that principal direction.

If we keep k principal components:

**V_k = [v₁ v₂ ... v_k]**

then the low-dimensional representation is:

> **z = V_kᵀx**

---

## 8. PCA Reconstruction

From the low-dimensional coordinate z:

> **x̂ = V_k z**

Substituting z = V_kᵀx gives:

> **x̂ = V_kV_kᵀx**

If the original data was mean-centered, then for an original point x:

> **x̂ = μ + V_kV_kᵀ(x-μ)**

This gives the approximate reconstruction using only the retained principal directions.

---

## 9. Why the Largest Eigenvector is PC1

The first principal component solves:

> **Maximize the variance of projected data**

subject to:

> **||v|| = 1**

For covariance matrix C, projected variance is proportional to:

> **vᵀCv**

So PCA solves:

> maximize **vᵀCv** subject to **vᵀv = 1**

The solution is:

> **The eigenvector of C corresponding to the largest eigenvalue.**

---

## 10. PCA Pipeline to Memorize

For a standard PCA calculation:

1. **Mean-center the data**
2. **Compute covariance matrix**
3. **Find eigenvalues and eigenvectors**
4. **Sort eigenvalues from largest to smallest**
5. **Choose the top k eigenvectors**
6. **Project the data**
7. If asked, **reconstruct using those k components**

Memory chain:

> **Center → Covariance → Eigendecomposition → Sort → Choose → Project → Reconstruct**

---

## 11. Quick Exam Recognition Table — PCA

| If the question says... | Think immediately |
|---|---|
| Maximum variance direction | Eigenvector with largest eigenvalue |
| PC1 | Dominant eigenvector |
| Variance captured by a PC | Corresponding eigenvalue |
| Retain 95% / 99% variance | Cumulative eigenvalue ratio |
| PCA projection | Vᵀx |
| PCA reconstruction | VVᵀx |
| Covariance matrix | Symmetric |
| PCA eigenvectors | Orthogonal / orthonormal |
| Tiny eigenvalues | Low-information directions |

---

## Questions Covered So Far

This PCA section directly covers the main ideas required for:

- **2022–23 Makeup Q1b** — maximum-variance direction
- **2023–24 EC3 Regular Q4B** — 95% and 99% explained variance

---

# Next PCA Step

The next exam pattern to study is the high-dimensional case:

> **D = 1024, N = 20**

where direct eigendecomposition of a 1024×1024 covariance-like matrix is inconvenient.

The key idea will be:

> **Use the much smaller 20×20 matrix XᵀX, then map its eigenvectors back through X.**

This is the PCA kernel-trick / dual-space shortcut.