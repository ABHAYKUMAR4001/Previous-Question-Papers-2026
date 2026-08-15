# MFML Learning Notes

# Topic 1 — Vector Spaces & Linear Independence

> **Learning goal:** Build the concepts in the same style in which they have appeared in MFML exams: **intuition → small example → actual exam question → solution pattern**.

## Topic Map

$$
\boxed{\text{Vector Space} \rightarrow \text{Subspace} \rightarrow \text{Span} \rightarrow \text{Linear Independence} \rightarrow \text{Basis}}
$$

We will begin with the most intuitive chain:

**Linear Combination → Span → Linear Independence**

---

## 1. What is a Linear Combination?

Suppose

$$
v_1=\begin{bmatrix}1\\0\end{bmatrix},
\qquad
v_2=\begin{bmatrix}0\\1\end{bmatrix}
$$

Take any two numbers $a$ and $b$.

Then

$$
av_1+bv_2
=
a\begin{bmatrix}1\\0\end{bmatrix}
+b\begin{bmatrix}0\\1\end{bmatrix}
=
\begin{bmatrix}a\\b\end{bmatrix}
$$

This is called a **linear combination** of $v_1$ and $v_2$.

For example,

$$
3v_1+2v_2
=
\begin{bmatrix}3\\2\end{bmatrix}
$$

### Intuition

Almost everything in this part of linear algebra asks some version of:

> **Can I create this vector using those vectors?**

That question leads directly to **span**.

---

## 2. What is Span?

The span of $v_1$ and $v_2$ is the collection of **all possible linear combinations** of those vectors:

$$
\boxed{
\operatorname{span}\{v_1,v_2\}
=
\{av_1+bv_2:a,b\in\mathbb R\}
}
$$

For

$$
v_1=(1,0),\qquad v_2=(0,1)
$$

we can create

$$
(1,2),\quad(-3,7),\quad(0,5)
$$

and in fact any point $(x,y)$.

Therefore

$$
\boxed{\operatorname{span}\{v_1,v_2\}=\mathbb R^2}
$$

### Geometric intuition

- One nonzero vector in $\mathbb R^2$ usually spans a **line**.
- Two non-parallel vectors in $\mathbb R^2$ span the **whole plane**.

So span tells us:

> **How much of the space can these vectors generate?**

---

## 3. Linear Dependence — Intuitive Meaning

Consider

$$
v_1=\begin{bmatrix}1\\2\end{bmatrix},
\qquad
v_2=\begin{bmatrix}2\\4\end{bmatrix}
$$

Clearly,

$$
v_2=2v_1
$$

So $v_2$ gives us **no new direction**.

If we already have $v_1$, adding $v_2$ does not increase the span:

$$
\operatorname{span}\{v_1\}
=
\operatorname{span}\{v_1,v_2\}
$$

Therefore $v_1$ and $v_2$ are **linearly dependent**.

> **Memory idea:** Dependent means at least one vector is redundant.

---

## 4. Mathematical Definition of Linear Independence

Vectors $v_1,v_2,\ldots,v_n$ are **linearly independent** if

$$
a_1v_1+a_2v_2+\cdots+a_nv_n=0
$$

has only the solution

$$
\boxed{a_1=a_2=\cdots=a_n=0}
$$

This is called the **trivial solution**.

### Why do we compare the combination with zero?

If a **non-zero** set of coefficients can produce the zero vector, then at least one vector can be constructed from the others.

For example,

$$
v_1=\begin{bmatrix}1\\2\end{bmatrix},
\qquad
v_2=\begin{bmatrix}2\\4\end{bmatrix}
$$

Since

$$
2v_1-v_2=0
$$

we found coefficients $2$ and $-1$ that are not both zero.

Therefore

$$
\boxed{v_1,v_2\text{ are linearly dependent}}
$$

---

# Exam Question 1 — Proving Linear Independence

### 2023–24 EC3 Regular — Q1C — 3 Marks

Suppose $a,b,c$ are linearly independent. Prove that

$$
\{b-c,\ a+c,\ a-b\}
$$

is linearly independent.

### What is the examiner testing?

Exactly the definition of linear independence.

Define

$$
v_1=b-c,\qquad v_2=a+c,\qquad v_3=a-b
$$

To prove these are independent, begin with

$$
\alpha_1v_1+\alpha_2v_2+\alpha_3v_3=0
$$

Substitute:

$$
\alpha_1(b-c)+\alpha_2(a+c)+\alpha_3(a-b)=0
$$

Expand and group the coefficients of $a,b,c$:

$$
(\alpha_2+\alpha_3)a
+(\alpha_1-\alpha_3)b
+(\alpha_2-\alpha_1)c
=0
$$

We are given that $a,b,c$ are linearly independent. Therefore each coefficient must be zero:

$$
\alpha_2+\alpha_3=0,\qquad
\alpha_1-\alpha_3=0,\qquad
\alpha_2-\alpha_1=0
$$

The last two equations give

$$
\alpha_1=\alpha_2=\alpha_3
$$

Using the first equation,

$$
2\alpha_1=0
$$

therefore

$$
\alpha_1=\alpha_2=\alpha_3=0
$$

Hence

$$
\boxed{\{b-c,a+c,a-b\}\text{ is linearly independent}}
$$

### Exam Pattern to Remember

Whenever the question says **prove these vectors are linearly independent**, start with

$$
\boxed{\alpha_1v_1+\alpha_2v_2+\cdots+\alpha_nv_n=0}
$$

and prove

$$
\boxed{\alpha_1=\alpha_2=\cdots=\alpha_n=0}
$$

---

# Exam Question 2 — Equality of Two Spans

A previous MFML comprehensive question gives

$$
v_1+v_2+v_3=0
$$

and asks you to show

$$
\boxed{\operatorname{span}\{v_1,v_2\}=\operatorname{span}\{v_2,v_3\}}
$$

From the given relation,

$$
v_1=-v_2-v_3
$$

Therefore $v_1\in\operatorname{span}\{v_2,v_3\}$, so

$$
\operatorname{span}\{v_1,v_2\}
\subseteq
\operatorname{span}\{v_2,v_3\}
$$

Similarly,

$$
v_3=-v_1-v_2
$$

so

$$
\operatorname{span}\{v_2,v_3\}
\subseteq
\operatorname{span}\{v_1,v_2\}
$$

Since both inclusions are true,

$$
\boxed{\operatorname{span}\{v_1,v_2\}=\operatorname{span}\{v_2,v_3\}}
$$

### Exam Pattern to Remember

To prove

$$
\operatorname{span}(A)=\operatorname{span}(B)
$$

show both directions:

$$
\operatorname{span}(A)\subseteq\operatorname{span}(B)
$$

and

$$
\operatorname{span}(B)\subseteq\operatorname{span}(A)
$$

---

## 5. What is a Vector Space?

A vector space is a collection of objects where vector addition and scalar multiplication behave properly and linear combinations remain inside the collection.

For intuition, $\mathbb R^2$ contains vectors such as

$$
(1,2),\qquad(-5,7),\qquad(0,0)
$$

If $u,v\in\mathbb R^2$ and $\alpha,\beta\in\mathbb R$, then

$$
\alpha u+\beta v\in\mathbb R^2
$$

The important point is that **vectors do not have to be ordinary columns of numbers**. Matrices, functions and polynomials can themselves form vector spaces.

---

## 6. What is a Subspace?

A **subspace** is a smaller vector space living inside a larger vector space.

To prove $M\subseteq V$ is a subspace, a convenient test is:

1. The zero vector/object belongs to $M$.
2. $M$ is closed under addition.
3. $M$ is closed under scalar multiplication.

Equivalently, for arbitrary $A,B\in M$ and scalars $\alpha,\beta$, prove

$$
\boxed{\alpha A+\beta B\in M}
$$

---

# Exam Question 3 — Matrices as Vectors and the Subspace Test

### MFML/MFDS Comprehensive Regular 2025–26 — Q1(B) — 6 Marks total

Consider

$$
M=\{A\in\mathbb R^{2\times2}\mid A=-A^T\}
$$

The first part asks you to prove that $M$ is a subspace of the vector space of all $2\times2$ real matrices.

Let

$$
A=\begin{bmatrix}a&b\\c&d\end{bmatrix}
$$

Then

$$
A^T=\begin{bmatrix}a&c\\b&d\end{bmatrix}
$$

The condition $A=-A^T$ implies

$$
a=0,\qquad d=0,\qquad c=-b
$$

so every matrix in $M$ has the form

$$
\boxed{A=\begin{bmatrix}0&b\\-b&0\end{bmatrix}}
$$

or equivalently

$$
A=b\begin{bmatrix}0&1\\-1&0\end{bmatrix}
$$

### Prove closure

Take $A,B\in M$. Then

$$
A^T=-A,\qquad B^T=-B
$$

Let

$$
C=\alpha A+\beta B
$$

Then

$$
C^T=(\alpha A+\beta B)^T
=\alpha A^T+\beta B^T
=-\alpha A-\beta B
=-C
$$

Therefore $C=-C^T$, so $C\in M$.

Hence

$$
\boxed{M\text{ is a subspace}}
$$

---

## 7. What is a Basis?

A **basis** must satisfy two conditions:

$$
\boxed{\text{Basis}=\text{Linearly Independent}+\text{Spans the Entire Space}}
$$

For our skew-symmetric matrix space,

$$
A=b\begin{bmatrix}0&1\\-1&0\end{bmatrix}
$$

Therefore

$$
M=\operatorname{span}\left\{\begin{bmatrix}0&1\\-1&0\end{bmatrix}\right\}
$$

The single nonzero matrix is linearly independent. Therefore a basis for $M$ is

$$
\boxed{\left\{\begin{bmatrix}0&1\\-1&0\end{bmatrix}\right\}}
$$

---

## 8. What is Dimension?

The **dimension** of a vector space is the number of vectors in any basis of that space.

$$
\dim(\mathbb R^2)=2,\qquad \dim(\mathbb R^3)=3
$$

Our skew-symmetric $2\times2$ matrix space has one basis matrix, so

$$
\boxed{\dim(M)=1}
$$

---

# Exam Question 4 — The Basis Trap

The same 2025–26 question asks whether

$$
\left\{
\begin{bmatrix}0&1\\-1&0\end{bmatrix},
\begin{bmatrix}0&2\\-2&0\end{bmatrix}
\right\}
$$

is a basis for $M$.

Call the matrices $A_1$ and $A_2$. Observe that

$$
A_2=2A_1
$$

Therefore they are **linearly dependent**.

They span $M$, but they are not independent. Since a basis requires both conditions,

$$
\boxed{\text{The given set is NOT a basis for }M}
$$

### Key intuition

This is exactly the same idea as the ordinary vectors

$$
(1,2),\qquad(2,4)
$$

The examiner has simply replaced ordinary vectors with matrices.

---

# Exam Question 5 — Linear Independence of Matrices

The same question asks whether

$$
\left\{
\begin{bmatrix}1&0\\0&1\end{bmatrix},
\begin{bmatrix}0&1\\-1&0\end{bmatrix}
\right\}
$$

is linearly independent.

Let

$$
\alpha\begin{bmatrix}1&0\\0&1\end{bmatrix}
+
\beta\begin{bmatrix}0&1\\-1&0\end{bmatrix}=0
$$

Then

$$
\begin{bmatrix}\alpha&\beta\\-\beta&\alpha\end{bmatrix}
=
\begin{bmatrix}0&0\\0&0\end{bmatrix}
$$

Therefore

$$
\alpha=0,\qquad\beta=0
$$

Only the trivial solution exists. Hence

$$
\boxed{\text{The two matrices are linearly independent}}
$$

### Important subtlety

The identity matrix is **not** in the skew-symmetric subspace $M$. That does not matter for this part because the question asks whether the two matrices are linearly independent in the larger vector space $\mathbb R^{2\times2}$.

---

# Topic 1 Mental Map So Far

### Linear Combination

$$
a_1v_1+\cdots+a_nv_n
$$

means combining vectors using scalar coefficients.

### Span

$$
\operatorname{span}\{v_1,\ldots,v_n\}
$$

means **everything that can be generated** from those vectors.

### Linear Independence

$$
a_1v_1+\cdots+a_nv_n=0
$$

must imply

$$
a_1=\cdots=a_n=0
$$

> **No vector is redundant.**

### Basis

$$
\boxed{\text{Basis}=\text{Independent}+\text{Spans the Space}}
$$

### Dimension

$$
\boxed{\text{Dimension}=\text{Number of vectors in a basis}}
$$

---

# Quick Exam Recognition Table

| If the question says... | First thing to think |
|---|---|
| Prove vectors are independent | Set $\alpha_1v_1+\cdots+\alpha_nv_n=0$ |
| Show vectors are dependent | Find a non-trivial combination equal to zero |
| Prove two spans are equal | Prove inclusion in both directions |
| Prove something is a subspace | Check closure / arbitrary linear combination |
| Is this set a basis? | Check **span AND independence** |
| Find dimension | Find a basis, then count its elements |

---

# Topic 1 — Remaining Material

Topic 1 is **not yet complete**.

The categorized MFML question bank also contains conceptual questions involving:

- whether dimension is independent of the underlying field,
- relationships between span and vector-space dimension,
- conceptual linear-independence statements,
- questions that begin connecting vector spaces to rank, RREF and null space.

We will cover those before declaring Topic 1 complete.

## Next Concept

> **Is the dimension of a vector space independent of the field?**

This will introduce the meaning of the underlying **field** ($\mathbb R$ versus $\mathbb C$) and show why the same collection of objects can have a different dimension depending on which scalars are allowed.
