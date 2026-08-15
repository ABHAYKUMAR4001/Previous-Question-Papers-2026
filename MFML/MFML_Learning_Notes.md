# MFML Learning Notes

## Topic 1 — Vector Spaces & Linear Independence

Before touching the exam questions, there are **five ideas** to connect:

\[
\boxed{\text{Vector Space}
\rightarrow \text{Subspace}
\rightarrow \text{Span}
\rightarrow \text{Linear Independence}
\rightarrow \text{Basis}}
\]

We’ll start with the easiest exam-style idea: **linear combination → span → independence**.

---

## 1. What is a linear combination?

Suppose

\[
v_1=
\begin{bmatrix}1\\0\end{bmatrix},
\qquad
v_2=
\begin{bmatrix}0\\1\end{bmatrix}
\]

Take any numbers \(a,b\).

Then

\[
av_1+bv_2
=
a\begin{bmatrix}1\\0\end{bmatrix}
+b\begin{bmatrix}0\\1\end{bmatrix}
=
\begin{bmatrix}a\\b\end{bmatrix}.
\]

This is called a **linear combination**.

So, for example,

\[
3v_1+2v_2=
\begin{bmatrix}3\\2\end{bmatrix}.
\]

Nothing complicated yet.

### Why does MFML care?

Because almost everything in linear algebra asks some version of:

> **Can I create this vector using those vectors?**

That is the heart of **span**.

---

# 2. What is Span?

The span of \(v_1,v_2\) is the collection of **all possible linear combinations**:

\[
\boxed{
\operatorname{span}\{v_1,v_2\}
=
\{a v_1+b v_2:a,b\in\mathbb R\}
}
\]

For our vectors,

\[
v_1=(1,0),\quad v_2=(0,1),
\]

we can create

\[
(1,2),\quad (-3,7),\quad(0,5)
\]

or literally any \((x,y)\).

Therefore

\[
\boxed{\operatorname{span}\{v_1,v_2\}=\mathbb R^2}.
\]

### Geometrically

One nonzero vector in \(\mathbb R^2\):

\[
\operatorname{span}\{v_1\}
\]

usually gives a **line**.

Two non-parallel vectors:

\[
\operatorname{span}\{v_1,v_2\}
\]

give the **whole plane**.

This geometric picture will become very useful.

---

# 3. Linear dependence — the intuitive meaning

Now consider

\[
v_1=
\begin{bmatrix}1\\2\end{bmatrix},
\qquad
v_2=
\begin{bmatrix}2\\4\end{bmatrix}.
\]

Obviously,

\[
v_2=2v_1.
\]

So \(v_2\) gives us **no new direction**.

If I already have \(v_1\), adding \(v_2\) does not enlarge the span:

\[
\operatorname{span}\{v_1\}
=
\operatorname{span}\{v_1,v_2\}.
\]

Therefore they are **linearly dependent**.

Think:

> **Dependent = at least one vector is redundant.**

---

# 4. Mathematical definition of independence

Vectors

\[
v_1,v_2,\ldots,v_n
\]

are linearly independent if

\[
a_1v_1+a_2v_2+\cdots+a_nv_n=0
\]

has **only**

\[
\boxed{a_1=a_2=\cdots=a_n=0}.
\]

This equation is extremely important.

### Why zero?

Because if a nonzero combination produces zero, one vector can be expressed using the others.

For example,

\[
v_1=
\begin{bmatrix}1\\2\end{bmatrix},
\quad
v_2=
\begin{bmatrix}2\\4\end{bmatrix}.
\]

Since

\[
2v_1-v_2=0,
\]

we have coefficients

\[
2,-1
\]

that are **not both zero**.

Hence

\[
\boxed{v_1,v_2\text{ are linearly dependent}.}
\]

---

# 5. Now an actual exam-style problem

Your categorized MFML bank contains this 2023–24 question:

> If \(a,b,c\) are linearly independent, prove that
>
> \[
> \{b-c,\ a+c,\ a-b\}
> \]
>
> is linearly independent.

At first glance, this looks abstract.

But the examiner is testing **exactly the definition we just learned**.

Let

\[
v_1=b-c
\]

\[
v_2=a+c
\]

\[
v_3=a-b.
\]

To prove \(v_1,v_2,v_3\) independent, start with:

\[
\alpha_1v_1+\alpha_2v_2+\alpha_3v_3=0.
\]

Substitute:

\[
\alpha_1(b-c)
+\alpha_2(a+c)
+\alpha_3(a-b)=0.
\]

Expand:

\[
\alpha_1b-\alpha_1c
+\alpha_2a+\alpha_2c
+\alpha_3a-\alpha_3b=0.
\]

Now group \(a,b,c\):

\[
(\alpha_2+\alpha_3)a
+
(\alpha_1-\alpha_3)b
+
(\alpha_2-\alpha_1)c
=0.
\]

Now comes the key point.

We were **given** that

\[
a,b,c
\]

are linearly independent.

Therefore the only way their combination can equal zero is:

\[
\alpha_2+\alpha_3=0
\]

\[
\alpha_1-\alpha_3=0
\]

\[
\alpha_2-\alpha_1=0.
\]

From the second:

\[
\alpha_1=\alpha_3.
\]

From the third:

\[
\alpha_2=\alpha_1.
\]

Therefore

\[
\alpha_1=\alpha_2=\alpha_3.
\]

Put this into the first:

\[
\alpha_1+\alpha_1=0
\]

\[
2\alpha_1=0
\]

so

\[
\alpha_1=0.
\]

Hence

\[
\alpha_1=\alpha_2=\alpha_3=0.
\]

Therefore

\[
\boxed{\{b-c,a+c,a-b\}\text{ is linearly independent}.}
\]

That is a complete exam answer.

---

# 6. The important pattern to recognize

Whenever the question says:

> **Prove these vectors are linearly independent**

your first instinct should be:

\[
\boxed{
\alpha_1v_1+\alpha_2v_2+\cdots+\alpha_nv_n=0
}
\]

Then prove

\[
\boxed{\alpha_1=\alpha_2=\cdots=\alpha_n=0}.
\]

That's your standard weapon.

---

# 7. Now let's understand Span using another actual MFML question

Your bank also contains:

\[
v_1+v_2+v_3=0
\]

and asks you to establish

\[
\boxed{
\operatorname{span}\{v_1,v_2\}
=
\operatorname{span}\{v_2,v_3\}
}.
\]

This is an excellent question because it tests whether you **actually understand span**.

We're told

\[
v_1+v_2+v_3=0.
\]

Therefore

\[
v_1=-v_2-v_3.
\]

So \(v_1\) can be constructed using \(v_2,v_3\).

Therefore

\[
v_1\in\operatorname{span}\{v_2,v_3\}.
\]

Obviously \(v_2\) is also in that span.

Consequently anything constructed from \(v_1,v_2\) can also be constructed from \(v_2,v_3\).

Thus

\[
\operatorname{span}\{v_1,v_2\}
\subseteq
\operatorname{span}\{v_2,v_3\}.
\]

But also rearrange the original equation:

\[
v_3=-v_1-v_2.
\]

So

\[
v_3\in\operatorname{span}\{v_1,v_2\}.
\]

Hence

\[
\operatorname{span}\{v_2,v_3\}
\subseteq
\operatorname{span}\{v_1,v_2\}.
\]

Since each is contained in the other:

\[
\boxed{
\operatorname{span}\{v_1,v_2\}
=
\operatorname{span}\{v_2,v_3\}
}.
\]

### This teaches a second exam pattern

To prove

\[
\operatorname{span}(A)=\operatorname{span}(B),
\]

show:

\[
\boxed{\operatorname{span}(A)\subseteq\operatorname{span}(B)}
\]

and

\[
\boxed{\operatorname{span}(B)\subseteq\operatorname{span}(A)}.
\]

---

# 8. Now: what is a Vector Space?

This sounds intimidating because textbooks usually start with a long list of axioms.

For MFML, think more simply first.

A vector space is a **collection of objects where linear combinations remain inside the collection**.

For example,

\[
\mathbb R^2
\]

contains vectors such as

\[
(1,2),(-5,7),(0,0).
\]

If

\[
u,v\in\mathbb R^2
\]

then

\[
\alpha u+\beta v
\]

is still in \(\mathbb R^2\).

Hence \(\mathbb R^2\) is a vector space.

But vectors do NOT have to look like columns of numbers.

Matrices can themselves be "vectors."

Functions can themselves be "vectors."

Polynomials can themselves be "vectors."

This is crucial for the latest MFML question.

---

# 9. Actual 2025–26 exam question: matrices as vectors

The question defines

\[
M=\{A\in\mathbb R^{2\times2}:A=-A^T\}
\]

and asks you to prove \(M\) is a subspace of the vector space of all \(2\times2\) real matrices.

First understand what

\[
A=-A^T
\]

means.

Let

\[
A=
\begin{bmatrix}
a&b\\
c&d
\end{bmatrix}.
\]

Then

\[
A^T=
\begin{bmatrix}
a&c\\
b&d
\end{bmatrix}.
\]

Condition:

\[
A=-A^T
\]

means

\[
\begin{bmatrix}
a&b\\
c&d
\end{bmatrix}
=
\begin{bmatrix}
-a&-c\\
-b&-d
\end{bmatrix}.
\]

Therefore

\[
a=-a\Rightarrow a=0
\]

\[
d=-d\Rightarrow d=0
\]

and

\[
c=-b.
\]

Thus every matrix in \(M\) looks like

\[
\boxed{
A=
\begin{bmatrix}
0&b\\
-b&0
\end{bmatrix}
}.
\]

Or

\[
A=b
\begin{bmatrix}
0&1\\
-1&0
\end{bmatrix}.
\]

Every matrix in this entire space is generated by **one matrix**.

Keep that observation—we'll use it for basis shortly.

---

# 10. How do I prove something is a subspace?

Rather than memorizing all vector-space axioms every time, use the standard subspace test.

For \(M\subseteq V\), establish:

1. Zero is in \(M\).
2. Closed under addition.
3. Closed under scalar multiplication.

Even more compactly, show

\[
\boxed{\alpha A+\beta B\in M}
\]

for arbitrary

\[
A,B\in M,\quad\alpha,\beta\in\mathbb R.
\]

Here,

\[
A=-A^T,\qquad B=-B^T.
\]

Take

\[
C=\alpha A+\beta B.
\]

Then

\[
C^T
=
\alpha A^T+\beta B^T.
\]

Because

\[
A^T=-A,\qquad B^T=-B,
\]

we get

\[
C^T=-\alpha A-\beta B=-C.
\]

Therefore

\[
C=-C^T.
\]

Hence

\[
C\in M.
\]

So

\[
\boxed{M\text{ is a subspace}.}
\]

Notice how little memorization was required.

---

# 11. Basis — now everything connects

A **basis** is a set of vectors that satisfies TWO conditions:

\[
\boxed{\text{Basis}=
\text{Linearly Independent}
+
\text{Spans the space}}
\]

This is one of the most important statements in Topic 1.

For the skew-symmetric matrix space above, we discovered:

\[
A=b
\begin{bmatrix}
0&1\\
-1&0
\end{bmatrix}.
\]

Therefore

\[
M=
\operatorname{span}
\left\{
\begin{bmatrix}
0&1\\
-1&0
\end{bmatrix}
\right\}.
\]

And that one nonzero matrix is obviously independent.

Therefore a basis is

\[
\boxed{
\left\{
\begin{bmatrix}
0&1\\
-1&0
\end{bmatrix}
\right\}
}
\]

and consequently

\[
\boxed{\dim M=1}.
\]

---

# 12. Now the examiner's trap

The same 2025–26 question asks whether

\[
\left\{
\begin{bmatrix}
0&1\\
-1&0
\end{bmatrix},
\begin{bmatrix}
0&2\\
-2&0
\end{bmatrix}
\right\}
\]

is a basis for \(M\).

Look carefully.

Call them \(A_1,A_2\).

But

\[
A_2=2A_1.
\]

Therefore they are linearly dependent.

They certainly span \(M\), but they are **not independent**.

Remember:

\[
\text{Basis}=\text{Span}+\text{Independence}.
\]

One condition fails.

Therefore

\[
\boxed{\text{Not a basis}.}
\]

This is exactly the same concept as

\[
(1,2),\quad(2,4).
\]

The examiner simply replaced ordinary vectors with matrices.

---

# 13. One more part of that same exam question

It asks whether

\[
\left\{
\begin{bmatrix}
1&0\\
0&1
\end{bmatrix},
\begin{bmatrix}
0&1\\
-1&0
\end{bmatrix}
\right\}
\]

is linearly independent.

Let

\[
\alpha
\begin{bmatrix}
1&0\\
0&1
\end{bmatrix}
+
\beta
\begin{bmatrix}
0&1\\
-1&0
\end{bmatrix}
=0.
\]

Then

\[
\begin{bmatrix}
\alpha&\beta\\
-\beta&\alpha
\end{bmatrix}
=
\begin{bmatrix}
0&0\\
0&0
\end{bmatrix}.
\]

Therefore

\[
\alpha=0,\qquad\beta=0.
\]

Only the trivial solution exists.

Hence

\[
\boxed{\text{linearly independent}.}
\]

Notice something subtle:

The identity matrix isn't in the skew-symmetric subspace \(M\).

**That doesn't matter.**

The question only asks whether the two matrices are linearly independent in the larger vector space \(V=\mathbb R^{2\times2}\).

---

# 14. Where we are now

You should now have this mental map:

\[
\boxed{\text{Linear combination}}
\]

means

\[
a_1v_1+\cdots+a_nv_n.
\]

↓

\[
\boxed{\text{Span}}
\]

means **everything I can generate** using those linear combinations.

↓

\[
\boxed{\text{Linear Independence}}
\]

means **none of my vectors is redundant**.

↓

\[
\boxed{\text{Basis}}
\]

means

\[
\boxed{\text{independent + spans the entire space}}.
\]

↓

\[
\boxed{\text{Dimension}}
\]

means

> number of vectors in a basis.

So for

\[
\mathbb R^2:
\quad
\dim=2.
\]

For

\[
\mathbb R^3:
\quad
\dim=3.
\]

For the \(2\times2\) skew-symmetric matrix space:

\[
\dim M=1.
\]

---

## Topic 1 is not finished yet

The categorized bank has another **10-mark conceptual bundle** containing questions about dimension and field, RREF uniqueness, rank structure, spans, and eigenvalue/orthogonality claims. Some of those naturally bridge Topic 1 into Topic 2, so we'll separate them carefully rather than mixing concepts.

For the **next step of Topic 1**, we will tackle the conceptual question:

> **“Is the dimension of a vector space independent of the field?”**

That will teach what \(\mathbb R\), \(\mathbb C\), field, basis and dimension actually mean, and it is representative of the short conceptual questions appearing in the MFML question bank.
