# MFML (Mathematical Foundation for Machine Learning) - Comprehensive Exam Questions (Full Verbatim)

**Papers Covered:**
- 2022-23 Comprehensive (40%)
- 2022-23 Comprehensive Makeup AIML (40%)
- 2023-24 EC3 Regular Solutions (40%)
- 2023-24 EC3 Makeup Solutions (40%)
- Comprehensive Regular AIML (40%)
- Comprehensive Regular AK
- Comprehensive Makeup AIML (40%)
- Comprehensive Makeup AK
- MFML Comprehensive March 2025 Solution Key (40%)
- MFML Comprehensive Makeup April 2025 Solution Key (40%)

> **Note:** Questions involving diagrams/figures are marked with [DIAGRAM IN ORIGINAL]. Refer to the original PDF for visual content.

---

## 1. Principal Component Analysis (PCA) & Dimensionality Reduction


### Q1 [2022-23 Comprehensive, Q1a - 5M]

A data scientist works on a problem on $N > 10000$ data points on $D > 100$ dimensions, and obtains the top 10 principal components. Assume the given data is mean-centred. The data scientist's manager comes to him and tells him that due to a problem with the way in which the data was collected, every data point in D dimensions $(x_1, x_2, \ldots, x_D)$ needs to be transformed to $(\alpha_1 x_1, \alpha_2 x_2, \ldots, \alpha_D x_D)$ where $(\alpha_1, \alpha_2, \ldots, \alpha_D)$ are fixed constants.

The data scientist believes that he can simply modify each discovered eigenvector $(b_1, b_2, \ldots, b_D)$ to $(\alpha_1 b_1, \alpha_2 b_2, \ldots, \alpha_D b_D)$ to get the principal directions for the modified problem.

Is the data scientist correct in his belief? Give a mathematical justification for his belief. Otherwise explain why he is wrong.

---

### Q2 [2022-23 Comprehensive, Q1b - 3M]

Assume that a data scientist is originally given N points in D dimensions. In order to perform PCA the data scientist computes the covariance matrix. The data scientist is then informed that each given data point of the form $(x_1, x_2, \ldots, x_D)$ needs to be transformed to $(\alpha_1 x_1, \alpha_2 x_2, \ldots, \alpha_D x_D)$ where $(\alpha_1, \alpha_2, \ldots, \alpha_D)$ are fixed constants.

The data scientist thinks that he can compute the modified covariance matrix in only $O(D^2)$ time, given that he has the old covariance matrix with him. Is the data scientist justified in his belief? If so, demonstrate the method used by him. Otherwise, show why he is incorrect.

---

### Q3 [2022-23 Makeup AIML, Q1b - 2M]

A Professor gave a 2 dimensional data matrix:

$$X = \begin{bmatrix} 2 & -1 \\ -2 & 1 \\ -4 & 2 \\ 4 & -2 \end{bmatrix}$$

for dimension reduction. Student 1 suggested that the direction of maximum variance is $[1, 0]^T$. Student 2 suggested that the direction of maximum variance is $[0, 1]^T$. Student 3 claimed that both student 1 and 2 are wrong.

Find the correct $v$ that gives the direction of maximum variance and hence decide on which student is correct.

---

### Q4 [2023-24 EC3R Solutions, Q4B - 4M]

Given covariance matrix eigenvalues: 12, 6.8, 3.5, 1, 0.02, 0.01

i) The dimension of each training sample is $1 \times 6$ as the covariance matrix is having 6 eigenvalues. [1M]

ii) Total variance = sum of all eigenvalues = 23.330. To retain 95% variance, keep top 3 eigenvalues: $(12 + 6.8 + 3.5) \times 100 / 23.330 = 95.7\%$. To retain 99% variance, keep top 4: $(12 + 6.8 + 3.5 + 1) \times 100 / 23.330 = 99.87\%$. [3M]

iii) After PCA, compute projection:
$$\begin{bmatrix} -3 & -2 & 2 & 1 & 2 & 4 \end{bmatrix} \times \begin{bmatrix} 0.115 & 0.205 \\ 0.106 & 0.215 \\ 0.118 & 0.315 \\ 0.082 & 0.428 \\ 0.013 & 0.238 \\ 0.023 & 0.034 \end{bmatrix}$$

---

### Q5 [Comprehensive Makeup AIML, Q3(2) - 3M]

A data scientist came across a dataset $x_1, x_2, \ldots, x_N$ where $x_i \in \mathbb{R}^{1024}$. Here $N = 20$. He wants to find the eigenvalues of a new matrix defined as:

$$S = \sum_{i=1}^{N} x_i x_i^T$$

Observe that $S \in \mathbb{R}^{1024 \times 1024}$. The data scientist has access to a piece of octave code containing a function `[P, D] = eig(A)` which returns eigenvalues and eigenvectors of a square symmetric matrix A as long as it has less than 32 rows.

(a) How will you use the `eig(A)` function to find eigenvalues of S by overcoming the fact that S has 1000 rows. Give a mathematical reasoning of how this can be achieved. [1.5M]

(b) How will you use the `eig(A)` function to find eigenvectors of S by overcoming the fact that S has 1000 rows. Give a mathematical reasoning of how this can be achieved. [1.5M]

---

## 2. Gradient Descent & Optimization


### Q1 [2023-24 EC3M Solutions, Q1(1) - 4M]

Consider $f(x, y) = x^2 + \beta y^2$. Gradient descent with momentum term. The update step:

$$z_{i+1} = z_i - \alpha \nabla f(z_i) + v_i$$

where $v_i = \beta(z_i - z_{i-1})$ and $v_0 = 0$.

Given: $\nabla f = \begin{bmatrix} 6x \\ 4y \end{bmatrix}$, $x_0 = 2$, $y_0 = 4$, $\alpha = \frac{1}{2}$

From iterates:
- $x_1 = x_0 - \alpha \cdot 6x_0 = 2 - \frac{1}{2} \cdot 12 = -4$
- $x_2 = x_1 - \alpha \cdot 6x_1 + \beta(x_1 - x_0) = 8 - 6\beta$
- $x_3 = x_2 - \alpha \cdot 6x_2 + \beta(x_2 - x_1) = -6\beta^2 + 24\beta - 16$

Given $x_3 = -7.36$, solve: $-6\beta^2 + 24\beta - 16 = -7.36$

Find $\beta$ (where $\beta \in (0,1)$).

---

### Q2 [2023-24 EC3M Solutions, Q1(3) - 3M]

Consider $f(x, y) = x^2 + \beta y^2$ at starting point $(x_0, y_0) = (1, 1)$.

(a) Derive closed form expression for optimal step size $\alpha$:

$$\alpha = \arg\min_\alpha f\left(\begin{bmatrix} x_0 \\ y_0 \end{bmatrix} - \alpha \nabla f(x_0, y_0)\right)$$

$\nabla f(1, 1) = \begin{bmatrix} 2 \\ 2\beta \end{bmatrix}$

Minimize $g(\alpha) = (1 - 2\alpha)^2 + \beta(1 - 2\alpha\beta)^2$

Setting $g'(\alpha) = 0$: $\alpha = \frac{1 + \beta^2}{2 + 2\beta^3}$

(b) If $\alpha = 0.5$, find $\beta$:
$0.5 = \frac{1 + \beta^2}{2 + 2\beta^3} \Rightarrow \beta^2(\beta - 1) = 0 \Rightarrow \beta = 1$ (since $\beta \neq 0$)

---

### Q3 [March 2025, Q4(i) - 4M]

Consider $f(x, y) = 2x^2 + \beta y^2$ where $\beta \in \mathbb{R}$, $\beta \neq 0$. Initial point $\begin{bmatrix} x_0 \\ y_0 \end{bmatrix} = \begin{bmatrix} 1 \\ 2 \end{bmatrix}$.

(i) Derive a closed form expression for the optimal step size $\alpha$ for the first iteration of gradient descent.

$\nabla f(1, 2) = \begin{bmatrix} 4 \\ 4\beta \end{bmatrix}$

Minimize: $g(\alpha) = 2(1 - 4\alpha)^2 + \beta(2 - 4\alpha\beta)^2$

$g'(\alpha) = 32\beta^3\alpha - 16\beta^2 + 64\alpha - 16 = 0$

$$\alpha = \frac{16 + 16\beta^2}{64 + 32\beta^3}$$

(ii) If $\alpha = 0.25$, derive the value of $\beta$:
$\beta^2(\beta - 2) = 0 \Rightarrow \beta = 2$ (since $\beta \neq 0$)

---

### Q4 [March 2025, Q4(ii) - 2M]

Consider $f(z) = 3z^4 - 6z^3 - 42z^2 + 2z + 72$.

(i) Derive all critical points in range $[a, b]$ where $a = -5$ and $b = 5$.

$f'(z) = 12z^3 - 18z^2 - 84z + 2$. Factorize: $6z(2z^2 - 3z - 14) = 0$

Critical points: $z_1 = 0$, $z_2 = -2$, $z_3 = 3.5$

(ii) Using second derivative test, classify the critical point closest to the left end (i.e., 'a'):
$f''(z) = 36z^2 - 36z - 84$. At $z = -2$: $f''(-2) = 144 + 72 - 84 > 0 \Rightarrow$ minimum.

---

### Q5 [April 2025 Makeup, Q4(i) - 4M]

Consider $f(x, y) = x^2 + \beta y^2$ where $\beta \neq 0$. Initial point $(x_0, y_0) = (1, 1)$.

$\nabla f(1, 1) = \begin{bmatrix} 2 \\ 2\beta \end{bmatrix}$

Minimize: $g(\alpha) = (1 - 2\alpha)^2 + \beta(1 - 2\alpha\beta)^2$

$g'(\alpha) = 8\beta^3\alpha - 4\beta^2 + 8\alpha - 4 = 0$

$$\alpha = \frac{4 + 4\beta^2}{8 + 8\beta^3}$$

If $\alpha = \frac{1}{6}$, find $\beta$: solving gives $\beta = 2$.

---

### Q6 [April 2025 Makeup, Q4(ii) - 2M]

$f(z) = 3z^4 - 8z^3 + 6z^2$

(i) Find all critical points in $[-3, 3]$:
$f'(z) = 12z^3 - 24z^2 + 12z = 12z(z^2 - 2z + 1) = 12z(z-1)^2 = 0$

Critical points: $z = 0$, $z = 1$ (repeated)

(ii) Classify $z = 0$ (closest to left end $a = -3$): minimum.

---

### Q7 [2022-23 Makeup AIML, Q1a - 3+1M]

A data science intern arrived at a loss function:
$$f(x) = 3x^4 - 20x^3 + 36x^2 + 10$$

i) Find stationary points and classify, hence find global minima. [3M]

$f'(x) = 12x^3 - 60x^2 + 72x = 12x(x^2 - 5x + 6) = 12x(x-2)(x-3) = 0$

Stationary points: $x = 0, 2, 3$

ii) Suggest whether $x = 0.5$ or $x = 3.5$ is a better initial condition to find global minima using simple gradient descent method with reasons. [1M]

---

## 3. Support Vector Machines (SVM) & Kernel Methods


### Q1 [2022-23 Comprehensive, Q1c - 8M]

We are given three points and their associated classifications in the format $(x, y, \text{category})$ as follows: $(-1, 3, +)$, $(1, 3, -)$, $(-1, 1, -)$, and would like to find a separating hyperplane in the form $w^T x + b = 0$ using SVM.

Let $\alpha_i, 1 \leq i \leq 3$ be the Lagrangian multipliers for the given points. Set up the Lagrangian dual objective for this problem in terms of only the Lagrangian parameters as a polynomial in the fewest number of variables and the fewest number of terms. If possible, find the optimal separating hyperplane from this expression using the methods of calculus. Give adequate justifications.

---

### Q2 [2023-24 EC3M Solutions, Q2(1) - 5M]

Find a suitable transformation to make the following 1D data linearly separable:

| Point | Label |
|-------|-------|
| (7, 0) | +1 |
| (9, 0) | +1 |
| (8, 0) | -1 |
| (10, 0) | -1 |

Suitable transformation: $\phi(x) = x \mod 2$

$\phi(7) = 1$, $\phi(9) = 1$, $\phi(8) = 0$, $\phi(10) = 0$

Decision boundary: $x = 0.5$

---

### Q3 [2023-24 EC3M Solutions, Q2(2) - 3M]

Compute the Kernel matrix $K$ using the feature transformation $\phi(x) = [x_1, x_2, ||x||]$ for dataset $X = [(4, -3), (0, 1)]$.

Transformed features:
- $\phi((4, -3)) = [4, -3, 5]$
- $\phi((0, 1)) = [0, 1, 1]$

$K_{ij} = \phi(x_i) \cdot \phi(x_j)$

$$K = \begin{bmatrix} 50 & 2 \\ 2 & 2 \end{bmatrix}$$

---

### Q4 [2023-24 EC3M Solutions, Q2(3) - 2M]

Compute the hinge loss for each data sample:

$$\text{Hinge Loss} = \max(0, 1 - y \cdot y')$$

1. $y = 0.5$, $y' = 1$: Hinge Loss $= \max(0, 1 - 0.5 \times 1) = 0.5$
2. $y = 1$, $y' = -1$: Hinge Loss $= \max(0, 1 - 1 \times (-1)) = 2$

The misclassified sample is sample 2 (higher non-zero hinge loss).

---

### Q5 [2023-24 EC3R Solutions, Q3B - 3.5M]

Given 4 data points: $(1,1,+1)$, $(-1,-1,+1)$, $(1,-1,-1)$, $(-1,1,-1)$.

i) The problem is not linearly separable (XOR-like pattern). [1M]

ii) Kernel: $K(x_1, x_2) = (4 + x_1^T x_2)^2$. Compute kernel matrix: [1M]

$$K = \begin{bmatrix} 144 & 16 & 16 & 16 \\ 16 & 144 & 16 & 16 \\ 16 & 16 & 144 & 16 \\ 16 & 16 & 16 & 144 \end{bmatrix}$$

iii) Set up dual: [0.5M]
$$Q(\alpha) = \sum_{i=1}^{4}\alpha_i - \frac{1}{2}(144\alpha_i^2 + \text{cross terms})$$

Solving: $\alpha_i = \frac{1}{128}$, $w = (0, 0, 22.6, 0, 0, 0)$, $b = 0$

Decision boundary: $x_1 x_2 = 0$ [2M]

---

### Q6 [March 2025, Q5 - 8M]

Given primal optimization problem:

$$\min\ x + y \quad \text{subject to} \quad \alpha x^2 + \beta y^2 \leq 1, \quad \beta x^2 + \alpha y^2 \leq 1$$

Known: $\alpha > 0$, $\beta > 0$, $\alpha \neq \beta$, $f(x)$ is convex.

(a) Write the dual formulation. The objective function in the dual should be expressed in the form $a(\lambda) + \frac{1}{p(\lambda)} + \frac{1}{q(\lambda)}$ where $a(\lambda), p(\lambda), q(\lambda)$ are linear functions. [4M]

Lagrangian: $L = x + y + \lambda_1(\alpha x^2 + \beta y^2 - 1) + \lambda_2(\beta x^2 + \alpha y^2 - 1)$

Setting $\frac{\partial L}{\partial x} = 0$, $\frac{\partial L}{\partial y} = 0$:
- $1 + 2x(\alpha\lambda_1 + \beta\lambda_2) = 0$
- $1 + 2y(\beta\lambda_1 + \alpha\lambda_2) = 0$

$$D(\lambda) = -\lambda_1 - \lambda_2 - \frac{1}{4(\alpha\lambda_1 + \beta\lambda_2)} - \frac{1}{4(\alpha\lambda_2 + \beta\lambda_1)}$$

(b) Find optimal primal solution assuming dual optimal is strictly positive. [4M]

By complementary slackness: $\alpha x^2 + \beta y^2 = 1$ and $\beta x^2 + \alpha y^2 = 1$

Subtracting: $(\alpha - \beta)x^2 = (\alpha - \beta)y^2 \Rightarrow x = \pm y$

Then $x^2 = \frac{1}{\alpha + \beta}$, giving minimum objective $= \frac{-2}{\sqrt{\alpha + \beta}}$

---

### Q7 [March 2025, Q6 - 6M]

Let $K(x, y)$ be a kernel function corresponding to the mapping $\phi$ which has $d$ components. Find the mapping for the kernel function $(K(x, y) + c)^2$? How many components does this mapping contain?

Expanding $(K(x,y) + c)^2 = K^2(x,y) + 2cK(x,y) + c^2$

New transformation $\psi(x) = \begin{bmatrix} \alpha_1(x) \\ \alpha_2(x) \\ \alpha_3(x) \end{bmatrix}$ where:
- $\alpha_1(x) = c$ (corresponds to $c^2$)
- $\alpha_2(x) = [\sqrt{2c}\phi_1(x), \ldots, \sqrt{2c}\phi_d(x)]$ (corresponds to $2cK$)
- $\alpha_3(x) = [\phi_i(x)\phi_j(x)]_{i,j=1}^d$ (corresponds to $K^2$)

Total components: $1 + d + d^2$

---

### Q8 [April 2025 Makeup, Q3 - 8M]

Given data points: $(1, 1, +1)$, $(-1, -1, +1)$, $(1, -1, -1)$, $(-1, 1, -1)$

(a) Write the SVM dual optimization problem. [2M]

$$\max_\alpha \sum_{i=1}^{4}\alpha_i - \frac{1}{2}\sum_{i,j}\alpha_i\alpha_j y_i y_j K(x_i, x_j)$$

subject to $\alpha_i \geq 0$ and $\sum_i \alpha_i y_i = 0$

(b) Solve for Lagrange multipliers. [3M]

(c) Find optimal $w$ and $b$. [3M]

---

## 4. Convex Functions & Convex Optimization


### Q1 [2022-23 Comprehensive, Q2a - 4M]

Assume that $x \in \mathbb{R}^n$. Consider the following functions:

i) $f_1(x) = ||x||_1$. Prove or disprove that $f_1(x)$ is a convex function by using the properties of norms discussed in the course. [2M]

ii) Let $g(x)$ be a convex function and $A \in \mathbb{R}^{n \times n}$ and $b \in \mathbb{R}^n$. Prove or disprove that $h(x) = g(Ax + b)$ is a convex function using the definition of convex functions discussed in the course. [2M]

---

### Q2 [Comprehensive Makeup AIML, Q3(1)ii - 1M]

Consider the set $C = \{x \mid Ax = b\}$ where $A \in \mathbb{R}^{n \times n}$ is a square matrix and $b \in \mathbb{R}^n$ and $C$ here represents all possible solutions of a linear system $Ax = b$. Prove or disprove that $C$ is a convex set.

---

### Q3 [2022-23 Makeup AIML, Q1c - 4M]

The set of interest for a data scientist was:
$$M = \{(x, y) \in \mathbb{R}^2 \mid x^2 + y^2 \leq 5, \quad x + 2y = 4, \quad x \geq 0, \quad y \geq 0\}$$

i) Formulate a constrained optimization problem to find a point in $M$ nearest to the origin $(0, 0)$. [1M]

ii) Write the Lagrangian function for the above problem. [1M]

iii) Verify and find the values of Lagrangian multipliers such that the point $\left(\frac{4}{5}, \frac{8}{5}\right)$ satisfies the KKT conditions for the above problem. Justify your steps. [2M]

---

### Q4 [2023-24 EC3R Solutions, Q1A - 4M]

i) Find the closest point on the line $x - 2y + 3 = 0$ to point $(4, 2)$:

$$\min\ (4-x)^2 + (2-y)^2 \quad \text{subject to} \quad x - 2y + 3 = 0$$

Lagrangian: $L(x, y, \lambda) = (4-x)^2 + (2-y)^2 + \lambda(x - 2y + 3)$

Solving $\nabla L = 0$: $x = \frac{17}{5}$, $y = \frac{16}{5}$, distance $= \sqrt{\frac{9}{5}}$

ii) Find the closest point on the line $x + 2y + 5 = 0$ to point $(4, 2)$:

Solving: $x = \frac{7}{5}$, $y = -\frac{16}{5}$, distance $= \sqrt{\frac{169}{5}}$

---

### Q5 [April 2025 Makeup, Q2 - 6M]

Constrained optimization: Minimize $f(x, y) = x^2 + y$ subject to $g(x, y) = x^2 - y^2 = 1$.

Using Lagrange multipliers: $\nabla f = \lambda \nabla g$

$2x = \lambda(2x) \Rightarrow \lambda = 1$ or $x = 0$

$1 = \lambda(-2y)$

If $\lambda = 1$: $y = -\frac{1}{2}$ and $x = \pm\sqrt{\frac{5}{4}}$

Function value at both points: $f = \frac{3}{4}$

Also $f(x, y) = (y^2 + 1) + y = y^2 + y + 1 = (y + \frac{1}{2})^2 + \frac{3}{4}$

These points represent minima.

---

## 5. Linear Algebra - Eigenvalues, Eigenvectors & Matrix Properties

### Q1 [2022-23 Comprehensive, Q2b - 4M]

A matrix $A \in \mathbb{R}^{n \times n}$ with SVD $A = U\Sigma V^T$ where $\Sigma$ is the matrix of singular values. It is known that $||\Sigma||_F^2 = \gamma$ (Frobenius norm). Define $B = A^T A$ and:
$$\alpha = B_{11} + B_{22} + \ldots + B_{nn}$$

Student G1 claimed $\alpha = \gamma$. Student G2 claimed $\alpha = \sqrt{\gamma}$.

(a) Prove or disprove the claim made by G1. [1.5M]
(b) Prove or disprove the claim made by G2. [1.5M]
(c) Consider $C = AA^T$. Let $\beta = C_{11} + C_{22} + \ldots + C_{nn}$. Prove or disprove that $\beta = \gamma^2$. [1M]

---

### Q2 [2023-24 EC3R Solutions, Q1B - 4M]

Given matrix $C$, find eigenvalues. The characteristic equation:
$$\det(C - \lambda I) = \lambda^3 - 14\lambda^2 - 9\lambda + 126 = (\lambda - 3)(\lambda + 3)(\lambda - 14) = 0$$

Eigenvalues: $\lambda_1 = 14$, $\lambda_2 = 3$, $\lambda_3 = -3$

i) $\text{Trace}(C^6) = \lambda_1^6 + \lambda_2^6 + \lambda_3^6 = 14^6 + 3^6 + (-3)^6$

ii) $\det(C^7) = \det(C)^7 = (\lambda_1 \cdot \lambda_2 \cdot \lambda_3)^7 = (14 \times 3 \times (-3))^7 = (-126)^7$

---

### Q3 [2023-24 EC3M Solutions, Q1(2) - 2.5M]

Given positive definite matrix $A$. Find Cholesky decomposition $A = LL^T$.

The lower triangular matrix: $L = \begin{bmatrix} l_{11} & 0 & 0 \\ l_{21} & l_{22} & 0 \\ l_{31} & l_{32} & l_{33} \end{bmatrix}$

Result: $l_{11} = 2$, $l_{21} = 1$, $l_{22} = 4$, $l_{31} = 3$, $l_{32} = 1$, $l_{33} = 5$

Eigenvalues of $L$: $|L - \lambda I| = (\lambda - 2)(\lambda - 4)(\lambda - 5) = 0$

Eigenvalues: $\lambda_1 = 2$, $\lambda_2 = 4$, $\lambda_3 = 5$

---

### Q4 [April 2025 Makeup, Q1 - 5M]

Given matrix $A$:
(a) Find eigenvalues.
(b) Find corresponding eigenvectors.
(c) Determine if matrix is diagonalizable. If yes, find $P$ and $D$ such that $A = PDP^{-1}$.

---

## 6. Linear Algebra - Vector Spaces, Subspaces & Linear Independence


### Q1 [2023-24 EC3R Solutions, Q1C - 3M]

Given $a, b, c$ are linearly independent. Prove that $\{x, y, z\} = \{b-c, a+c, a-b\}$ is linearly independent.

Consider $\alpha_1 x + \alpha_2 y + \alpha_3 z = 0$:
$$\alpha_1(b-c) + \alpha_2(a+c) + \alpha_3(a-b) = 0$$
$$a(\alpha_2 + \alpha_3) + b(\alpha_1 - \alpha_3) + c(\alpha_2 - \alpha_1) = 0$$

Since $a, b, c$ are linearly independent:
- $\alpha_2 + \alpha_3 = 0$
- $\alpha_1 - \alpha_3 = 0$
- $\alpha_2 - \alpha_1 = 0$

Solving: $\alpha_1 = \alpha_2 = \alpha_3 = 0 \Rightarrow \{x, y, z\}$ is linearly independent.

---

### Q2 [2023-24 EC3M Solutions, Q3A - 4M]

Given matrix $A$ with rows $R_1, \ldots, R_m$:

$$A = \begin{bmatrix} R_1^T \\ \vdots \\ R_m^T \end{bmatrix}$$

i) Show $Ax = 0$ when $\langle R_i, x \rangle = 0$ for all $i = 1, \ldots, m$. [1M]

Therefore $Ax = \begin{bmatrix} R_1^T x \\ \vdots \\ R_m^T x \end{bmatrix} = 0$ since $\langle R_i, x \rangle = 0$.

ii) Show $S = \{x \in \mathbb{R}^m \mid \langle R_i, x \rangle = 0, i = 1, \ldots, m\} = N(A)$ is a subspace. [2M]

$N(A)$ is a subspace of $\mathbb{R}^m$ when $A$ is of order $m \times m$.

iii) If $\text{rank}(A) = m$, find $\dim S$: [1M]

By rank-nullity theorem: $\dim S = \dim N(A) = m - \text{rank}(A) = 0 \Rightarrow S = \{0\}$

---

### Q3 [Comprehensive Makeup AIML, Q2 - 10M]

i) Find the rank of an $A_{n \times n}$ matrix whose $jk$-th entry is $a_{jk} = j + k - 1$. Would it change if $a_{jk} = j + k - \alpha$, where $\alpha$ is a positive integer? Justify. [2M]

ii) Prove or disprove the statement that the dimension of a vector space is independent of the field over which it is defined. [2M]

iii) Prove that if $v_1, v_2, v_3$ are elements of a vector space V over a field F such that $v_1 + v_2 + v_3 = 0$, then $\{v_1, v_2\}$ spans the same subspace as $\{v_2, v_3\}$. [2M]

iv) Two students A and B perform RREF on a given matrix X and obtain the same matrix $\tilde{X}$. Student C says both A and B cannot have the same RREF whereas D says that it is possible. A senior student E says that both A and B could be correct and it is actually possible to get X from $\tilde{X}$, provided none of the elements in X is zero. Who all are correct and why? [2M]

v) Given distinct eigenvalues $\lambda_1, \lambda_2, \ldots, \lambda_n$, is it possible to generate an orthogonal matrix of order $n$? Justify your answer. [2M]

---

### Q4 [2023-24 EC3R Solutions, Q3A - 2M]

Given $6 \times 6$ matrix $A$ where $C_1 = \sum_{i=2}^{6} C_i = 2C_2$.

Find two vectors in null space of $A$:

From $C_1 = 2C_2$: $C_1 - 2C_2 + 0C_3 + 0C_4 + 0C_5 + 0C_6 = 0$
$$A[1, -2, 0, 0, 0, 0]^T = 0$$

From $C_1 = 2\sum_{i=3}^{6} C_i$: $-C_1 + 0C_2 + 2C_3 + 2C_4 + 2C_5 + 2C_6 = 0$
$$A[-1, 0, 2, 2, 2, 2]^T = 0$$

---

## 7. Calculus - Gradients & Jacobians

### Q1 [2022-23 Comprehensive, Q2c - 4M]

Let $x \in \mathbb{R}^n$, $c \in \mathbb{R}^n$, $b \in \mathbb{R}^n$, $d \in \mathbb{R}$, $A \in \mathbb{R}^{n \times n}$, $A_1 \in \mathbb{R}^{n \times n}$, $A_2 \in \mathbb{R}^{n \times n}$.

$$f(x) = ||Ax - b||_2^2 + c^T x + d$$
$$g(x) = ||A_1^T A_1 x||_2^2 + ||A_2^T x||_2^2$$

i) Derive the gradient of $f(x)$ with respect to variable $x$. [2M]

ii) Derive the gradient of $g(x)$ with respect to variable $x$. [2M]

---

### Q2 [2022-23 Comprehensive, Q3b - 3M]

A data scientist had arrived at a model $f(x) = [x^T Q x, b^T x]^T$ where $Q$ is a $3 \times 3$ symmetric positive definite matrix and $x, b \in \mathbb{R}^3$.

i) Find the gradient (Jacobian) $\nabla_x f$. [1M]

ii) Find the linear approximation of $f$ about $(0, 0, 0)$. [2M]

---

### Q3 [2023-24 EC3M Solutions, Q3B - 5M]

Sigmoid: $\sigma(z) = (1 + e^{-z})^{-1}$

i) Derive: $\frac{d\sigma}{dz} = \sigma(z)(1 - \sigma(z))$ [1M]

ii) Given:
$$f(x, y) = \alpha \ln\left(\frac{1}{\sigma(x + \beta y)}\right) + (1-\alpha)\ln\left(\frac{1}{1-\sigma(x+\beta y)}\right)$$

Simplify to: $f(x,y) = (1-\alpha)(x+\beta y) - \ln(\sigma(x+\beta y))$ [2M]

iii) Compute: [1M]
$$\frac{\partial f}{\partial x} = -\alpha + \sigma(x + \beta y)$$
$$\frac{\partial f}{\partial y} = \beta(-\alpha + \sigma(x + \beta y))$$

iv) Taylor's polynomial of degree 1 at $(0, 0)$: [1M]
$$T_1(x,y) = \ln(2) + \left(-\alpha + \frac{1}{2}\right)(x + \beta y)$$

---

### Q4 [2023-24 EC3R Solutions, Q2A - 3.5M]

Given loss function:
$$L(\beta) = \frac{1}{2p}||y - \beta||^2 + \lambda ||W\beta||^2$$

i) Express as sum of individual losses: $L(\beta) = \frac{1}{p}\sum_{j=1}^{p} L_j(\beta)$ where $L_j(\beta) = \frac{1}{2}(y_j - \beta_j)^2 + \lambda\beta^T W^T W\beta$ [1.5M]

ii) Derive gradient of $L_j(\beta)$: [1M]
$$\nabla L_j(\beta) = [v + 2\lambda W^T W\beta]^T$$

iii) Derive gradient of $L(\beta)$: [1M]
$$\nabla L(\beta) = -\frac{1}{p}(y - \beta)^T + 2\lambda(W^T W\beta)^T$$

---

## 8. Inner Products, Norms & Distance Functions

### Q1 [2022-23 Comprehensive, Q3a - 6M]

Matrix $A = \begin{bmatrix} 1 & 0 & \rho \\ 0 & 1 & \rho \\ \rho & \rho & 1 \end{bmatrix}$

i) Find the conditions on $\rho$ such that $\langle x, y \rangle_A = x^T A y$ is an inner product defined on $\mathbb{R}^3$. [3M]

(Requires $A$ to be positive definite, so all eigenvalues > 0)

ii) Is $x = [1, 0, 0]^T$ perpendicular to $y = [0, 1, 0]^T$ with respect to the inner product defined in (i)? Find all $z$ perpendicular to both $x$ and $y$ with respect to the inner product defined in (i). [3M]

---

### Q2 [Comprehensive Makeup AIML, Q3(1)i - 2M]

Let $x \in \mathbb{R}^n$ and $y \in \mathbb{R}^n$. Consider:

$$d(x, y) = \sum_{i=1}^{n} |x_i - y_i|$$

Prove or disprove that $d(x, y)$ is a valid distance function by verifying all the properties:
1. $d(x, y) \geq 0$ (non-negativity)
2. $d(x, y) = 0 \iff x = y$ (identity)
3. $d(x, y) = d(y, x)$ (symmetry)
4. $d(x, z) \leq d(x, y) + d(y, z)$ (triangle inequality)

---

### Q3 [2022-23 Comprehensive, Q3c - 3M]

The Manager asked the data analyst to find a $2 \times 2$ matrix $M$ with $\text{trace}(M) = 0$ such that $(||M - A||_2)^2$ is minimum where $A = \begin{bmatrix} 1 & 0 \\ 0 & 2 \end{bmatrix}$.

Help the data analyst in finding $M$.

---

## 9. Critical Points & Function Analysis

### Q1 [2023-24 EC3R Solutions, Q2C - 3M]

$f(x, y) = (x^2 + y^2)e^{-(x^2+y^2)}$

Find set $A$ of all critical points:

$f_x = 2xe^{-(x^2+y^2)}[1 - x^2 - y^2] = 0 \Rightarrow x = 0$ or $x^2 + y^2 = 1$

$f_y = 2ye^{-(x^2+y^2)}[1 - x^2 - y^2] = 0 \Rightarrow y = 0$ or $x^2 + y^2 = 1$

Therefore: $A = \{(0,0)\} \cup \{(x,y) \in \mathbb{R}^2 \mid x^2 + y^2 = 1\}$

Nature of $(0,0)$: $f_{xx}(0,0) = 2$, $f_{yy}(0,0) = 2$, $f_{xy}(0,0) = 0$

$H(0,0) = \begin{bmatrix} 2 & 0 \\ 0 & 2 \end{bmatrix}$ (positive definite) $\Rightarrow (0,0)$ is a minimum.

---

## 10. Constrained Optimization & KKT Conditions


### Q1 [2023-24 EC3R Solutions, Q4A - 6M]

Primal: $\min x_1^2 + x_2^2 - 4x_1 - 4x_2$ subject to $x_1^2 - x_2 \leq 0$, $x_1 + x_2 - 2 \leq 0$

i) Lagrangian: $L(x, \lambda) = x_1^2 + x_2^2 - 4x_1 - 4x_2 + \lambda_1(x_1^2 - x_2) + \lambda_2(x_1 + x_2 - 2)$

$\frac{\partial L}{\partial x_1} = 0$, $\frac{\partial L}{\partial x_2} = 0$

$$x_1 = \frac{4 - \lambda_2}{2(1+\lambda_1)}, \quad x_2 = \frac{\lambda_1 - \lambda_2 + 4}{2}$$

ii) Dual and primal objective function value will be the same as the primal objective function is convex and the constraints are convex. (Strong duality holds) [2M]

---

### Q2 [Comprehensive Makeup AIML, Q1c - 4M]

$M = \{(x,y) \in \mathbb{R}^2 \mid x^2 + y^2 \leq 5, x + 2y = 4, x \geq 0, y \geq 0\}$

i) Formulate: $\min x^2 + y^2$ subject to $x^2 + y^2 \leq 5$, $x + 2y = 4$, $x \geq 0$, $y \geq 0$ [1M]

ii) Lagrangian: $L = x^2 + y^2 + \lambda_1(x^2 + y^2 - 5) + \lambda_2(x + 2y - 4) - \mu_1 x - \mu_2 y$ [1M]

iii) Verify $\left(\frac{4}{5}, \frac{8}{5}\right)$ satisfies KKT conditions. Find multiplier values. [2M]

KKT conditions:
- Stationarity: $\nabla f + \lambda_1 \nabla g_1 + \lambda_2 \nabla h = 0$
- Primal feasibility: $g_i(x^*) \leq 0$, $h_j(x^*) = 0$
- Dual feasibility: $\lambda_i \geq 0$
- Complementary slackness: $\lambda_i g_i(x^*) = 0$

---

## 11. Singular Value Decomposition (SVD)

### Q1 [2022-23 Comprehensive, Q2b - 4M]

SVD of $A = U\Sigma V^T$ where $||\Sigma||_F^2 = \gamma$.

$B = A^T A = V\Sigma^T U^T U\Sigma V^T = V\Sigma^2 V^T$

$\alpha = \text{trace}(B) = \text{trace}(V\Sigma^2 V^T) = \text{trace}(\Sigma^2) = \sum \sigma_i^2 = ||\Sigma||_F^2 = \gamma$

Therefore G1 is **correct**: $\alpha = \gamma$ ✓

G2 claims $\alpha = \sqrt{\gamma}$: **incorrect** ✗

$C = AA^T = U\Sigma^2 U^T$, $\beta = \text{trace}(C) = \text{trace}(\Sigma^2) = \gamma$

Claim $\beta = \gamma^2$ is **incorrect** (it equals $\gamma$, not $\gamma^2$) ✗

---

### Q2 [April 2025 Makeup, Q1 - 5M]

Given matrix $A$:
(a) Compute $A^T A$.
(b) Find singular values of $A$ (square roots of eigenvalues of $A^T A$).
(c) Construct $U$, $\Sigma$, $V$ matrices for full SVD decomposition.

---

## 12. Kernel Methods & Feature Transformations

### Q1 [2023-24 EC3R Solutions, Q2B - 2M]

Feature transformation: $\phi(x) = [x_1, \ldots, x_m, x_1^3, \ldots, x_m^3, x_1x_2x_3, x_2x_3x_4, \ldots, x_{m-2}x_{m-1}x_m]^T$

Dimension of transformed data $= m + m + (m-2) = 3m - 1$

Kernel:
$$K(x, y) = \phi(x)^T\phi(y) = \sum_{i=1}^m x_i y_i + \sum_{i=1}^m x_i^3 y_i^3 + \sum_{i=1}^{m-2} x_i x_{i+1} x_{i+2} y_i y_{i+1} y_{i+2}$$

---

## 13. Gradient Descent with Momentum

### Q1 [2023-24 EC3M Solutions, Q1(1) - Full - 4M]

Given $f(x,y) = 3x^2 + 2y^2$. Update rule with momentum:
$$z_{i+1} = z_i - \alpha\nabla f(z_i) + v_i, \quad v_i = \beta(z_i - z_{i-1}), \quad v_0 = 0$$

Given: $(x_0, y_0) = (2, 4)$, $\alpha = \frac{1}{2}$

Using x-updates:
- $x_1 = 2 - \frac{1}{2}(12) = -4$
- $x_2 = -4 - \frac{1}{2}(6 \times -4) + \beta(-4 - 2) = 8 - 6\beta$
- $x_3 = (8-6\beta) - 3(8-6\beta) + \beta((8-6\beta) - (-4)) = -6\beta^2 + 24\beta - 16$

If $x_3 = -7.36$: $-6\beta^2 + 24\beta - 16 = -7.36$

Solving quadratic: $\beta = 0.4$ or $\beta = 3.6$. Since $\beta \in (0,1)$: $\beta = 0.4$

---

## 14. Regularized Loss Functions & Gradients

### Q1 [Comprehensive Makeup AIML, Q3(3) - 4M]

Consider $g(z) = \frac{1}{2}||Az - b||_2^2 + \frac{1}{2}||z||_2^2 + ||b||_2^2$ where $A \in \mathbb{R}^{n \times n}$ is symmetric positive definite, $b \in \mathbb{R}^n$.

Minimize using gradient descent: $z_{k+1} = z_k + \alpha d_k$

(a) Derive expression for $d_k$ (gradient descent direction): [2M]

$\nabla g(z) = A^T(Az - b) + z = (A^T A + I)z - A^T b$

$d_k = -\nabla g(z_k) = A^T b - (A^T A + I)z_k$

(b) Derive closed form expression for optimal stepsize: [2M]

$$\alpha^* = \frac{d_k^T d_k}{d_k^T (A^T A + I) d_k}$$

---

## 15. Taylor Series & Linear Approximation

### Q1 [2022-23 Comprehensive, Q3b - 2M]

$f(x) = [x^T Q x, \quad b^T x]^T$ where $Q$ is $3 \times 3$ SPD.

Jacobian: $\nabla_x f = \begin{bmatrix} 2x^T Q \\ b^T \end{bmatrix}$

Linear approximation about $(0,0,0)$:
$$f(x) \approx f(0) + \nabla_x f(0) \cdot x = \begin{bmatrix} 0 \\ 0 \end{bmatrix} + \begin{bmatrix} 0 \\ b^T \end{bmatrix} x = \begin{bmatrix} 0 \\ b^T x \end{bmatrix}$$

---

### Q2 [2023-24 EC3M Solutions, Q3B(iv) - 1M]

Taylor polynomial of degree 1 of $f(x,y) = (1-\alpha)(x+\beta y) - \ln(\sigma(x+\beta y))$ at $(0,0)$:

$$T_1(x,y) = f(0,0) + \left[\frac{\partial f}{\partial x}(0,0), \frac{\partial f}{\partial y}(0,0)\right] \begin{bmatrix} x \\ y \end{bmatrix}$$

$$= \ln(2) + \left(-\alpha + \frac{1}{2}\right)(x + \beta y)$$

---

## 16. Null Space, Column Space & Rank

### Q1 [2023-24 EC3R Solutions, Q3A - 2M]

$6 \times 6$ matrix $A$ where $C_1 = \sum_{i=2}^{6} C_i$ and $C_1 = 2C_2$.

Two independent null space vectors:
1. $[1, -2, 0, 0, 0, 0]^T$ (from $C_1 = 2C_2$)
2. $[-1, 0, 2, 2, 2, 2]^T$ (from $C_1 = 2\sum_{i=3}^{6} C_i$)

Therefore $\dim(N(A)) \geq 2$, so $\text{rank}(A) \leq 4$.

---

### Q2 [Comprehensive Makeup AIML, Q2i - 2M]

Find the rank of $A_{n \times n}$ matrix whose $jk$-th entry is $a_{jk} = j + k - 1$.

Note: Each column $C_k$ has entries $k, k+1, \ldots, k+n-1$. So $C_k = C_1 + (k-1)\mathbf{1}$ where $\mathbf{1}$ is all-ones vector.

This means all columns lie in span of $\{C_1, \mathbf{1}\}$, so rank $= 2$.

For $a_{jk} = j + k - \alpha$: Same structure, rank remains 2.

---
