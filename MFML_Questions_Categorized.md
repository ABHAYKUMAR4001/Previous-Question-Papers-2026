# MFML (Mathematical Foundation for Machine Learning) - Comprehensive Exam Questions (Full Verbatim)

**Papers Covered:**
- 2022-23 Comprehensive (40%)
- 2022-23 Comprehensive Makeup AIML (40%)
- 2023-24 EC3 Regular Solutions (40%)
- 2023-24 EC3 Makeup Solutions (40%)
- Comprehensive Regular AIML & AK
- Comprehensive Makeup AIML & AK
- MFML Comprehensive March 2025 Solution Key (40%)
- MFML Comprehensive Makeup April 2025 Solution Key (40%)

> **Note:** Questions involving diagrams are marked with [DIAGRAM IN ORIGINAL].

---

## 1. PCA & Dimensionality Reduction

### Q1 [2022-23 Comprehensive, Q1a - 5M]

$N>10000$ points in $D>100$ dimensions. Top 10 PCs found (mean-centred data). Each point $(x_1,\ldots,x_D)$ transformed to $(\alpha_1 x_1,\ldots,\alpha_D x_D)$. Can eigenvector $(b_1,\ldots,b_D)$ be modified to $(\alpha_1 b_1,\ldots,\alpha_D b_D)$ to get new PCs? Mathematical justification.

### Q2 [2022-23 Comprehensive, Q1b - 3M]

Same transformation. Can modified covariance matrix be computed in $O(D^2)$ given old covariance matrix? Demonstrate method.

### Q3 [2022-23 Makeup, Q1b - 2M]

Data: $X = \begin{bmatrix} 2 & -1 \\ -2 & 1 \\ -4 & 2 \\ 4 & -2 \end{bmatrix}$

Direction of max variance: $[1,0]^T$, $[0,1]^T$, or neither? Find correct $v$.

### Q4 [2023-24 EC3R, Q4B - 4M]

Eigenvalues: 12, 6.8, 3.5, 1, 0.02, 0.01. Total variance = 23.330.
- 95% variance: top 3 components $(12+6.8+3.5)/23.33 = 95.7\%$
- 99% variance: top 4 components
- Compute PCA projection for given data

### Q5 [Comprehensive Makeup, Q3(2) - 3M]

$x_i \in \mathbb{R}^{1024}$, $N=20$. $S = \sum_{i=1}^N x_i x_i^T \in \mathbb{R}^{1024\times1024}$. Function `eig(A)` works only for <32 rows.
(a) How to find eigenvalues of S? (b) How to find eigenvectors?

**Hint:** Use kernel trick. Define $K = X^T X$ (20x20 matrix). Eigenvalues of $K$ = non-zero eigenvalues of $S$. Eigenvectors of $S$ = $X \cdot$ eigenvectors of $K$ (normalized).

---

## 2. Gradient Descent & Optimization

### Q1 [2023-24 EC3M, Q1(1) - 4M]

$f(x,y) = 3x^2 + 2y^2$. GD with momentum: $z_{i+1} = z_i - \alpha\nabla f(z_i) + \beta(z_i - z_{i-1})$

$(x_0,y_0)=(2,4)$, $\alpha=1/2$. Given $x_3=-7.36$, find $\beta$.

$x_1 = -4$, $x_2 = 8-6\beta$, $x_3 = -6\beta^2+24\beta-16 = -7.36$

Solving: $\beta = 0.4$

### Q2 [2023-24 EC3M, Q1(3) - 3M]

$f(x,y) = x^2 + \beta y^2$ at $(1,1)$. Optimal step size:

$$\alpha = \frac{1+\beta^2}{2+2\beta^3}$$

If $\alpha=0.5$: $\beta^2(\beta-1)=0 \Rightarrow \beta=1$

### Q3 [March 2025, Q4(i) - 4M]

$f(x,y) = 2x^2 + \beta y^2$ at $(1,2)$. $\nabla f = [4, 4\beta]^T$.

$$\alpha = \frac{16+16\beta^2}{64+32\beta^3}$$

If $\alpha=0.25$: $\beta^2(\beta-2)=0 \Rightarrow \beta=2$

### Q4 [April 2025 Makeup, Q4(i) - 4M]

$f(x,y) = x^2 + \beta y^2$ at $(1,1)$. $\nabla f = [2, 2\beta]^T$.

$$\alpha = \frac{4+4\beta^2}{8+8\beta^3}$$

If $\alpha=1/6$: $\beta=2$

### Q5 [2022-23 Makeup, Q1a - 4M]

$f(x) = 3x^4 - 20x^3 + 36x^2 + 10$

$f'(x) = 12x(x-2)(x-3) = 0$. Stationary points: $x=0,2,3$

Better initial for GD to find global minima: $x=0.5$ or $x=3.5$?

### Q6 [March 2025, Q4(ii) - 2M]

$f(z) = 3z^4-6z^3-42z^2+2z+72$. Critical points in $[-5,5]$:

$f'(z) = 6z(2z^2-3z-14)=0$. Points: $z=0, -2, 3.5$

At $z=-2$: $f''(-2)>0$ → minimum

### Q7 [April 2025, Q4(ii) - 2M]

$f(z) = 3z^4-8z^3+6z^2$. $f'(z) = 12z(z-1)^2 = 0$. Points: $z=0, 1$

---

## 3. SVM & Kernel Methods

### Q1 [2022-23 Comprehensive, Q1c - 8M]

Points: $(-1,3,+), (1,3,-), (-1,1,-)$. Find separating hyperplane $w^Tx+b=0$.

Set up Lagrangian dual in terms of $\alpha_i$. Find optimal hyperplane using calculus.

### Q2 [2023-24 EC3M, Q2(1) - 5M]

Make linearly separable: $(7,0)\to+1$, $(9,0)\to+1$, $(8,0)\to-1$, $(10,0)\to-1$

Transformation: $\phi(x) = x \bmod 2$. Decision boundary: $x=0.5$

### Q3 [2023-24 EC3M, Q2(2) - 3M]

Kernel matrix for $\phi(x) = [x_1, x_2, ||x||]$, data $X=[(4,-3),(0,1)]$:

$\phi(4,-3)=[4,-3,5]$, $\phi(0,1)=[0,1,1]$

$$K = \begin{bmatrix} 50 & 2 \\ 2 & 2 \end{bmatrix}$$

### Q4 [2023-24 EC3M, Q2(3) - 2M]

Hinge loss: $\max(0, 1-y\cdot y')$
- $(y=0.5, y'=1)$: loss = 0.5
- $(y=1, y'=-1)$: loss = 2 (misclassified)

### Q5 [2023-24 EC3R, Q3B - 3.5M]

4 points (XOR pattern). $K(x_1,x_2) = (4+x_1^Tx_2)^2$.

$$K = \begin{bmatrix} 144&16&16&16\\16&144&16&16\\16&16&144&16\\16&16&16&144 \end{bmatrix}$$

Solve dual: $\alpha_i = 1/128$. Decision boundary: $x_1 x_2 = 0$

### Q6 [March 2025, Q5 - 8M]

$\min x+y$ s.t. $\alpha x^2+\beta y^2 \leq 1$, $\beta x^2+\alpha y^2 \leq 1$

Dual: $D(\lambda) = -\lambda_1-\lambda_2-\frac{1}{4(\alpha\lambda_1+\beta\lambda_2)}-\frac{1}{4(\alpha\lambda_2+\beta\lambda_1)}$

By complementary slackness: $x=\pm y$, $x^2=\frac{1}{\alpha+\beta}$

### Q7 [March 2025, Q6 - 6M]

Kernel $(K(x,y)+c)^2$. Mapping has $1+d+d^2$ components.

### Q8 [April 2025, Q3 - 8M]

Points $(1,1,+1),(-1,-1,+1),(1,-1,-1),(-1,1,-1)$. Write SVM dual. Solve for $\alpha$. Find $w$, $b$.

---

## 4. Convex Functions & Optimization

### Q1 [2022-23 Comprehensive, Q2a - 4M]

i) Prove/disprove $f_1(x)=||x||_1$ is convex. [2M]
ii) $g(x)$ convex → prove $h(x)=g(Ax+b)$ is convex. [2M]

### Q2 [Comprehensive Makeup, Q3(1)ii - 1M]

$C = \{x|Ax=b\}$ — prove $C$ is convex set.

### Q3 [2022-23 Makeup, Q1c - 4M]

$M = \{(x,y) | x^2+y^2 \leq 5, x+2y=4, x\geq0, y\geq0\}$

Nearest point to origin. Lagrangian. Verify $(4/5, 8/5)$ satisfies KKT.

### Q4 [2023-24 EC3R, Q1A - 4M]

Closest point to $(4,2)$ on lines $x-2y+3=0$ and $x+2y+5=0$.

Line 1: $(17/5, 16/5)$, distance $=\sqrt{9/5}$
Line 2: $(7/5, -16/5)$, distance $=\sqrt{169/5}$

### Q5 [April 2025, Q2 - 6M]

$\min f(x,y)=x^2+y$ s.t. $x^2-y^2=1$

Lagrange: $2x=\lambda(2x)$, $1=\lambda(-2y)$

$\lambda=1 \Rightarrow y=-1/2$, $x=\pm\sqrt{5/4}$, $f=3/4$ (minimum)

---

## 5. Eigenvalues & Matrix Properties

### Q1 [2022-23 Comprehensive, Q2b - 4M]

$A=U\Sigma V^T$, $||\Sigma||_F^2=\gamma$. $B=A^TA$.

$\text{trace}(B) = \text{trace}(\Sigma^2) = \gamma$ ✓ (G1 correct)

$\text{trace}(B) = \sqrt{\gamma}$? ✗ (G2 wrong)

$C=AA^T$: $\text{trace}(C)=\gamma$ (not $\gamma^2$) ✗

### Q2 [2023-24 EC3R, Q1B - 4M]

$\det(C-\lambda I) = (\lambda-3)(\lambda+3)(\lambda-14)=0$

$\text{Trace}(C^6) = 14^6+3^6+(-3)^6$

$\det(C^7) = (14\times3\times(-3))^7 = (-126)^7$

### Q3 [2023-24 EC3M, Q1(2) - 2.5M]

Cholesky: $A=LL^T$. $L=\begin{bmatrix}2&0&0\\1&4&0\\3&1&5\end{bmatrix}$

Eigenvalues of $L$: 2, 4, 5

---

## 6. Vector Spaces & Linear Independence

### Q1 [2023-24 EC3R, Q1C - 3M]

$a,b,c$ linearly independent → prove $\{b-c, a+c, a-b\}$ linearly independent.

$\alpha_1(b-c)+\alpha_2(a+c)+\alpha_3(a-b)=0$

$\Rightarrow a(\alpha_2+\alpha_3)+b(\alpha_1-\alpha_3)+c(\alpha_2-\alpha_1)=0$

Since $a,b,c$ independent: $\alpha_1=\alpha_2=\alpha_3=0$ ✓

### Q2 [Comprehensive Makeup, Q2 - 10M]

i) Rank of $A$ with $a_{jk}=j+k-1$. Rank=2. Same for $a_{jk}=j+k-\alpha$. [2M]
ii) Dimension of vector space independent of field? [2M]
iii) $v_1+v_2+v_3=0 \Rightarrow \text{span}\{v_1,v_2\}=\text{span}\{v_2,v_3\}$. [2M]
iv) Two students get same RREF — who's correct? [2M]
v) Distinct eigenvalues → orthogonal matrix possible? [2M]

### Q3 [2023-24 EC3R, Q3A - 2M]

6x6 matrix: $C_1=\sum_{i=2}^6 C_i = 2C_2$. Null space vectors:
- $[1,-2,0,0,0,0]^T$
- $[-1,0,2,2,2,2]^T$

---

## 7. Gradients & Jacobians

### Q1 [2022-23 Comprehensive, Q2c - 4M]

$f(x) = ||Ax-b||_2^2 + c^Tx + d$

$\nabla f = 2A^T(Ax-b) + c$

$g(x) = ||A_1^TA_1x||_2^2 + ||A_2^Tx||_2^2$

$\nabla g = 2(A_1^TA_1)^T(A_1^TA_1)x + 2A_2A_2^Tx$

### Q2 [2022-23 Comprehensive, Q3b - 3M]

$f(x) = [x^TQx, b^Tx]^T$. Jacobian: $\nabla_x f = \begin{bmatrix} 2x^TQ \\ b^T \end{bmatrix}$

Linear approximation at origin: $f(x) \approx \begin{bmatrix} 0 \\ b^Tx \end{bmatrix}$

### Q3 [2023-24 EC3M, Q3B - 5M]

$\sigma(z) = (1+e^{-z})^{-1}$. Prove $\sigma'(z)=\sigma(z)(1-\sigma(z))$.

$f(x,y) = (1-\alpha)(x+\beta y) - \ln(\sigma(x+\beta y))$

$\frac{\partial f}{\partial x} = -\alpha + \sigma(x+\beta y)$

$\frac{\partial f}{\partial y} = \beta(-\alpha + \sigma(x+\beta y))$

Taylor at (0,0): $T_1 = \ln(2) + (-\alpha+1/2)(x+\beta y)$

### Q4 [2023-24 EC3R, Q2A - 3.5M]

$L(\beta) = \frac{1}{2p}||y-\beta||^2 + \lambda||W\beta||^2$

$\nabla L = -\frac{1}{p}(y-\beta)^T + 2\lambda(W^TW\beta)^T$

---

## 8. Inner Products & Norms

### Q1 [2022-23 Comprehensive, Q3a - 6M]

$A = \begin{bmatrix}1&0&\rho\\0&1&\rho\\\rho&\rho&1\end{bmatrix}$

i) Conditions on $\rho$ for $\langle x,y\rangle_A = x^TAy$ to be inner product. (Require $A$ positive definite)
ii) Is $[1,0,0]^T \perp [0,1,0]^T$? Find all $z \perp$ both.

### Q2 [Comprehensive Makeup, Q3(1)i - 2M]

$d(x,y) = \sum|x_i-y_i|$. Prove valid distance (non-negativity, identity, symmetry, triangle inequality).

### Q3 [2022-23 Comprehensive, Q3c - 3M]

Find 2x2 matrix $M$ with $\text{trace}(M)=0$ minimizing $||M-A||_2^2$ where $A=\begin{bmatrix}1&0\\0&2\end{bmatrix}$.

---

## 9. Critical Points (Multivariable)

### Q1 [2023-24 EC3R, Q2C - 3M]

$f(x,y) = (x^2+y^2)e^{-(x^2+y^2)}$

Critical points: $A = \{(0,0)\} \cup \{x^2+y^2=1\}$

At $(0,0)$: $H=\begin{bmatrix}2&0\\0&2\end{bmatrix}$ → minimum

---

## 10. Constrained Optimization & KKT

### Q1 [2023-24 EC3R, Q4A - 6M]

$\min x_1^2+x_2^2-4x_1-4x_2$ s.t. $x_1^2-x_2\leq0$, $x_1+x_2-2\leq0$

$x_1 = \frac{4-\lambda_2}{2(1+\lambda_1)}$, $x_2 = \frac{\lambda_1-\lambda_2+4}{2}$

Strong duality holds (convex problem).

---

## 11. SVD

### Q1 [2022-23 Comprehensive, Q2b - 4M]

$A=U\Sigma V^T$. $B=A^TA=V\Sigma^2V^T$. $\text{trace}(B)=\sum\sigma_i^2=||\Sigma||_F^2=\gamma$

---

## 12. Regularized Loss & Stochastic Gradients

### Q1 [Comprehensive Makeup, Q3(3) - 4M]

$g(z) = \frac{1}{2}||Az-b||_2^2 + \frac{1}{2}||z||_2^2 + ||b||_2^2$

$\nabla g = (A^TA+I)z - A^Tb$

GD direction: $d_k = A^Tb - (A^TA+I)z_k$

Optimal stepsize: $\alpha^* = \frac{d_k^Td_k}{d_k^T(A^TA+I)d_k}$

---

## 13. Null Space & Rank

### Q1 [Comprehensive Makeup, Q2i - 2M]

$a_{jk} = j+k-1$. Column $C_k = C_1 + (k-1)\mathbf{1}$. Rank = 2.

### Q2 [2023-24 EC3M, Q3A - 4M]

$S = \{x | R_i^Tx=0\} = N(A)$. If $\text{rank}(A)=m$: $\dim S = 0 \Rightarrow S=\{0\}$.

---



---

**Additional Papers Covered (from MFML Final.pdf):**
- MFML/MFDS Comprehensive Regular 2025-26
- MFML/MFDS Comprehensive Makeup 2025-26
- EC-3 Regular 2025-26 (AIMLC2C416) Solution
- EC-3 Makeup 2025-26 (DSECL ZC416, Date: 08-03-2026)

---

## 1. PCA & Dimensionality Reduction

### Q6 [MFML/MFDS Comprehensive Regular 2025-26, Q3(A) - 8M]

Consider the following design matrix, representing four sample points $x_i \in \mathbb{R}^2$:

$$X = \begin{bmatrix} -4 & 5 \\ -2 & -1 \\ 2 & 0 \\ 4 & -4 \end{bmatrix}$$

(i) Compute the unit-length principal component directions of $X$, and state which principal component you would choose if you were requested to choose just one. Show computations. [4 Marks]

(ii) Draw the principal component direction (as a line) and the projections of all four sample points onto the principal direction. [3 Marks]

(iii) Reconstruct the data using rank-1 approximation. [1 Mark]

### Q7 [MFML/MFDS Comprehensive Makeup 2025-26, Q3(A) - 8M]

You are given a design matrix:

$$X = \begin{bmatrix} -8 & 4 \\ -2 & -1 \\ 6 & 5 \\ 6 & -2 \\ 2 & 3 \end{bmatrix}$$

(a) Compute the covariance matrix for the sample points. Then compute the unit eigenvectors, and the corresponding eigenvalues, of the covariance matrix. [4 Marks]

(b) Use PCA to project the sample points onto a one-dimensional space. What one-dimensional subspace are we projecting onto? For each of the four sample points in $X$, write the coordinate (in principal coordinate space, not in $\mathbb{R}^2$) that the point is projected to. [3 Marks]

(c) Draw the rough sketch of the projected points on the principal axis. [1 Mark]

---

## 2. Gradient Descent & Optimization

### Q8 [MFML/MFDS Comprehensive Regular 2025-26, Q2(C) - 2M]

Consider a gradient update rule given by:

$$\theta_{t+1} = \gamma a_t + (1-\gamma)\nabla_w(L)$$
$$w_{t+1} = w - \eta(\theta_{t+1})$$

What is the contribution of $\gamma$ while computing the value of $a_5$? [2 Marks]

### Q9 [MFML/MFDS Comprehensive Makeup 2025-26, Q2(a) - 6M]

Consider the function $f(x) = ax^3 + bx^2 + cx + d$ where $a > 0$.

(a) Find the condition on $a, b, c$ such that the function has two distinct critical points. Calculate the critical points in terms of $a, b, c$. Identify the nature of each critical point (i.e., maxima or minima). [3 Marks]

(b) Define a "zone of attraction" around each local minimum to be the region around it such that if gradient descent starts at any point in the region, it would end up at the given local minimum. Find the zone of attraction for each local minimum, if any, of the critical points. Justify your answer mathematically. [3 Marks]

---

## 3. SVM & Kernel Methods

### Q9 [MFML/MFDS Comprehensive Regular 2025-26, Q2(A) - 3M]

Consider the following optimization problem (A) on the data $(x_1, y_1), \ldots, (x_n, y_n)$ of the following form:

$$\max \sum \alpha_i - \frac{1}{2}\sum_i\sum_j \alpha_i \alpha_j y_i y_j x_i^T x_j$$

subject to $\sum \alpha_i y_i = 0$, $\alpha_i \geq 0, \forall i$

Note that here $y_i$ is $\pm 1, \forall i$ and each $x_i$ is an $n \times 1$ vector. We form a new optimization problem (B) as follows:

$$\max \sum_{i=1}^{n+1} \alpha_i - \frac{1}{2}\sum_{i=1}^{n+1}\sum_{j=1}^{n+1} \alpha_i \alpha_j y_i y_j x_i^T x_j$$

subject to $\sum_{i=1}^{n+1} \alpha_i y_i = 0$, $\alpha_i \geq 0, \forall i, 1 \leq i \leq n+1$

where $x_{n+1} = \frac{1}{2}(x_i + x_j)$ for some values of $i$ and $j$ such that $y_i = y_j$. We set $y_{n+1} = y_i$.

Show that the maximum value of the objective function for problem (B) is greater than or equal to the maximum value of the objective function for problem (A). Justify your solution mathematically. [3 Marks]

### Q10 [MFML/MFDS Comprehensive Regular 2025-26, Q2(B) - 5M]

Let $x$ and $z$ be two $n \times 1$ vectors, for which a kernel function is defined as $K(x, z) = (x^Tz)^2 + 3(x^Tz + 2)^2$. If possible, find a mapping $\phi$ from the space of $n \times 1$ vectors to the space of $(n^2 + n + 1) \times 1$ vectors for which the given kernel function represents the inner product. Otherwise explain why such a mapping is not possible for the given kernel function. [5 Marks]

### Q11 [MFML/MFDS Comprehensive Makeup 2025-26, Q3(B) - 5M]

Assume that you received the below data from a noisy sensor. The data consists of two classes (1 and 0). You train an SVM classifier with a quadratic kernel (i.e., polynomial with degree 2). Assume that $C$ is the regularisation parameter used to build a hard margin / soft margin classifier. [DIAGRAM IN ORIGINAL]

(a) Draw a possible decision boundary for a small value of $C$.

(b) Draw a possible decision boundary for a large value of $C$.

(c) Highlight one point, if it had a wrong label when given to you, would not affect the decision boundary.

(d) Highlight one point, if it had a wrong label when given to you, would affect the decision boundary.

(e) Would you prefer a high value of $C$ or a low value of $C$, given the nature of the problem?

[1 Mark × 5]

---

## 4. Convex Functions & Optimization

### Q6 [MFML/MFDS Comprehensive Makeup 2025-26, Q2(b) - 4M]

Consider solving the following constrained optimization problem:

$$\min \; ax + by + cz$$
$$\text{subject to} \; px + qy + rz = 0$$

Use the theory of Lagrange multipliers to obtain a condition on $(a, b, c)$ and $(p, q, r)$ when there is a solution to this problem and when there is no solution. How many solutions are there to this problem when there is a solution, and what is the value of the objective function at a solution point? [4 Marks]

---

## 5. Eigenvalues & Matrix Properties

### Q4 [EC-3 Regular 2025-26, Q1(a) - 5M]

Consider the matrix:

$$A = \begin{bmatrix} 3 & -1 & 0 \\ 1 & 3 & 0 \\ 0 & 0 & 4 \end{bmatrix}$$

Find all the eigenvalues and eigenvectors of $A$. [5 Marks]

### Q5 [EC-3 Makeup 2025-26, Q1(a) - 5M]

Consider the matrix:

$$A = \begin{bmatrix} -2 & 0 & 0 & 0 \\ -1 & 3 & 0 & 0 \\ 0 & -1 & -1 & 0 \\ 1 & 1 & 0 & 5 \end{bmatrix}$$

(a) Find all the eigenvalues of $A$. Find the eigenspace $V$ corresponding to the largest eigenvalue of $A$. Also find a basis and dimension of $V$. [1 + 2 + 2 = 5M]

---

## 6. Vector Spaces & Linear Independence

### Q4 [MFML/MFDS Comprehensive Regular 2025-26, Q1(A) - 4M]

Suppose $A = [C_1, C_2, C_3, C_4]$ where $C_m \in \mathbb{R}^4$, $m = 1, 2, 3, 4$ are columns of $A$. It is known that $\text{rank}(A) = 2$ and $C_2 = 3C_1$ and $C_4 = 2C_1 + 3C_3$. If a particular solution of $Ax = b$ is $(1, 0, 1, 0)^T$ then:

(i) Find the general solution of $Ax = b$. [2 Marks]

(ii) Find $b$ if $\text{RREF}(A) = \hat{A}$. [2 Marks]

### Q5 [MFML/MFDS Comprehensive Regular 2025-26, Q1(B) - 6M]

Consider $M = \{A \in \mathbb{R}^{2\times 2} \mid A = -A^T\}$.

(i) Prove that $M$ is a subspace of vector space $V$ where $V$ is the set of all $2 \times 2$ real matrices. [1.5 Marks]

(ii) Prove or disprove that $\left\{\begin{bmatrix} 0 & 1 \\ -1 & 0 \end{bmatrix}, \begin{bmatrix} 0 & 2 \\ -2 & 0 \end{bmatrix}\right\}$ is a basis for $M$ defined in (i). [2.5 Marks]

(iii) Prove or disprove that $\left\{\begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}, \begin{bmatrix} 0 & 1 \\ -1 & 0 \end{bmatrix}\right\}$ is a linearly independent set. [2 Marks]

---

## 7. Gradients & Jacobians

### Q5 [MFML/MFDS Comprehensive Regular 2025-26, Q4 - 8M]

The block diagram below shows a system with input $I$, output $L$, and the computations:

$x \in \mathbb{R}^2$, $f_1: p = w_1^T x + b_1$, $f_2: q = \frac{1}{1+e^{-p}}$, $f_3: r = w_2^T x + b_2$, $f_4: s = \frac{e^r - e^{-r}}{e^r + e^{-r}}$, $m = q + s$, $L = \frac{1}{2}(m - m^*)^2$

[DIAGRAM IN ORIGINAL]

(A) Draw the computation graph for this system which can be used to compute the gradient of $L$ w.r.t. $x$ using chain rule of partial derivatives. [2 Marks]

(B) Show that: $\frac{\partial q}{\partial p} = q(1-q)$ [2 Marks]

(C) Show that: $\frac{\partial s}{\partial r} = 1 - s^2$ [2 Marks]

(D) Write the expression for each of the below partial derivatives: [2 Marks]
(i) $\frac{\partial L}{\partial m}$
(ii) $\frac{\partial L}{\partial q}$
(iii) $\frac{\partial L}{\partial p}$
(iv) $\frac{\partial p}{\partial w_1}$

---

## 8. Inner Products & Norms

### Q4 [EC-3 Regular 2025-26, Q3 - 8M]

Let $A = \begin{bmatrix} 3 & 1 \\ 1 & 3 \end{bmatrix}$. An inner product on $\mathbb{R}^2$ is defined by $\langle u, v \rangle = u^T A v$, for $u, v \in \mathbb{R}^2$. The norm induced by this inner product is $\|x\| = \sqrt{\langle x, x \rangle}$.

Assume that a signal tower is located at the origin $(0, 0)$. The cost of placing a receiver at a point $(x, y) \in \mathbb{R}^2$ is given by $C(x, y) = 2\|(x, y)\|^2$. Suppose the receiver must be placed in the region $R = \{(x, y) \in \mathbb{R}^2 : x + y - 1 \geq 0, x + y - 3 \leq 0\}$.

(a) State and prove the necessary properties of the matrix $A$ such that $\langle u, v \rangle = u^T A v$ defines an inner product on $\mathbb{R}^2$. [2M]

(b) Formulate the constrained optimization problem to determine the point in the region $R$ at which the cost function $C(x, y)$ is minimized. [1M]

---

## 9. Critical Points (Multivariable)

*(No new questions in this category from MFML Final.pdf)*

---

## 10. Constrained Optimization & KKT

### Q2 [MFML/MFDS Comprehensive Makeup 2025-26, Q1 - 10M]

A signal tower is placed at $(0, 0)$. The cost to place a receiver at a point $(x, y)$ is equal to the square of the Euclidean distance from that point to the point at which the signal tower is placed. The region of interest is $\{(x, y) \mid 7 - 2x + y \leq 0, -5 - x - y \leq 0\}$.

(i) Help the analyst to formulate the optimization problem to find the point at which the cost to place the receiver is minimum in the region of interest. [1.5 Marks]

(ii) Write down the Lagrangian for the constrained optimization problem so obtained in (i). [0.5 Marks]

(iii) What are the KKT conditions for the problem in (i)? [4 Marks]

(iv) Using KKT conditions, find the solution for the optimization problem in (i). [4 Marks]

---

## 11. SVD

*(No new questions in this category from MFML Final.pdf)*

---

## 12. Regularized Loss & Stochastic Gradients

*(No new questions in this category from MFML Final.pdf)*

---

## 13. Null Space & Rank

*(No new questions in this category from MFML Final.pdf)*

---

## 14. Power Method & Iterative Techniques

### Q1 [MFML/MFDS Comprehensive Regular 2025-26, Q3(B) - 2M]

Assume that you are given the matrix $A$ as below:

$$A = \begin{bmatrix} 1 & 2 \\ 1 & 2 \end{bmatrix}$$

You are asked to use an iterative technique (e.g., power method) to obtain the eigenvector corresponding to the dominant eigenvalue. You start with an initial value of $x = [0, 0.5, 1]$ for the iterative technique. To which eigenvalue and eigenvector will the algorithm likely converge? Give reasons for your answer. [2 Marks]
