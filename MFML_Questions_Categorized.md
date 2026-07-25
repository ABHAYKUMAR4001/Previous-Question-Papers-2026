# MFML (Mathematical Foundation for Machine Learning) - Comprehensive Exam Questions Categorized by Topic

**Papers Covered:**
- 2022-23 Comprehensive (40%)
- 2022-23 Comprehensive Makeup AIML (40%)
- 2023-24 EC3 Regular Solutions (40%)
- 2023-24 EC3 Makeup Solutions (40%)
- Comprehensive Regular AIML (40%)
- Comprehensive Regular AK (Answer Key)
- Comprehensive Makeup AIML (40%)
- Comprehensive Makeup AK (Answer Key)
- MFML Comprehensive March 2025 Solution Key (40%)
- MFML Comprehensive Makeup April 2025 Solution Key (40%)

---

## 1. Principal Component Analysis (PCA) & Dimensionality Reduction

### Q1 [2022-23 Comprehensive, 5M]
A data scientist works on N>10000 points in D>100 dimensions and obtains top 10 principal components (mean-centered data). Every data point (x1,...,xD) needs to be transformed to (alpha1*x1,...,alphaD*xD). Can the scientist simply modify each eigenvector (b1,...,bD) to (alpha1*b1,...,alphaD*bD) to get principal directions for modified problem? Mathematical justification required.

### Q2 [2022-23 Comprehensive, 3M]
Data scientist computes covariance matrix. Then each point (x1,...,xD) is transformed to (alpha1*x1,...,alphaD*xD). Can the modified covariance matrix be computed in O(D^2) time given the old covariance matrix? Demonstrate the method or show why incorrect.

### Q3 [2022-23 Makeup AIML, 2M]
Given 2D data matrix X = [[2,-1],[-2,1],[-4,2],[4,-2]]. Student 1 says direction of max variance is [1,0]^T. Student 2 says [0,1]^T. Student 3 says both are wrong. Find correct v that gives direction of maximum variance.

### Q4 [2023-24 EC3R Solutions, 4M]
Given covariance matrix with 6 eigenvalues:
i) What is dimension of each training sample?
ii) How many components to retain 95% variance? 99% variance?
iii) Compute PCA projection for given data points.

### Q5 [Comprehensive Regular AIML]
i) Given S = sum(xi * xi^T) where xi in R^1024, N=20. S is 1024x1024. You have eig(A) function that works only for matrices with <32 rows.
a) How to find eigenvalues of S? Mathematical reasoning.
b) How to find eigenvectors of S? Mathematical reasoning.

### Q6 [March 2025, 4M]
Given covariance matrix of a dataset:
a) Compute eigenvalues and eigenvectors.
b) Determine the number of principal components needed to retain 90% of variance.
c) Project data onto the reduced space.

---

## 2. Gradient Descent & Optimization

### Q1 [2023-24 EC3M Solutions, 4M]
Given f(x,y) = x^2 + beta*y^2. Gradient descent with momentum term. From given iterates x0,x1,x2, and knowledge of x3, find beta. Using update rule: z_{i+1} = z_i - alpha*grad_f(z_i) + v_i where v_i = beta*(z_i - z_{i-1}).

### Q2 [2023-24 EC3M Solutions, 3M]
f(x,y) = 2x^2 + beta*y^2, start at (1,1). Derive closed form expression for optimal step size. If alpha=0.5, find beta.

### Q3 [Comprehensive Regular AIML, 2M]
g(z) = (1/2)||Az-b||^2 + (1/2)||z||^2 + ||b||^2 where A is symmetric positive definite.
a) Derive expression for gradient descent direction dk.
b) Derive closed form for optimal stepsize for (k+1)th iteration.

### Q4 [2022-23 Makeup AIML, 3+1M]
f(x) = 3x^4 - 20x^3 + 36x^2 + 10.
i) Find stationary points, classify, find global minima.
ii) Suggest whether x=0.5 or x=3.5 is better initial condition for gradient descent. Reasons.

### Q5 [March 2025, 4M]
f(x,y) = 2x^2 + beta*y^2 where beta != 0. Initial point (1,2).
(i) Derive closed form for optimal step size alpha for first iteration.
(ii) If alpha=0.25, find beta.

### Q6 [March 2025, 2M]
f(z) = 3z^4 - 6z^3 - 42z^2 + 2z + 72.
(i) Find all critical points in [-5, 5].
(ii) Classify critical point closest to left end using second derivative test.

### Q7 [April 2025 Makeup, 4M]
f(x,y) = x^2 + beta*y^2 where beta != 0. Initial point (1,1).
(i) Derive closed form for optimal step size.
(ii) If alpha = 1/6, find beta.

### Q8 [April 2025 Makeup, 2M]
f(z) = 3z^4 - 8z^3 + 6z^2.
(i) Find all critical points in [-3, 3].
(ii) Classify critical point closest to left end.

---

## 3. Support Vector Machines (SVM) & Kernel Methods

### Q1 [2022-23 Comprehensive, 8M]
Three points: (-1,3,+), (1,3,-), (-1,1,-). Find separating hyperplane w^T*x + b = 0 using SVM. Set up Lagrangian dual objective as polynomial in fewest variables and terms. Find optimal separating hyperplane using calculus.

### Q2 [2023-24 EC3M Solutions, 5M]
Find suitable transformation to make data linearly separable: (7,0)->+1, (9,0)->+1, (8,0)->-1, (10,0)->-1. Find decision boundary.

### Q3 [2023-24 EC3M Solutions, 3M]
Compute Kernel matrix K using feature transformation phi(x) = [x1, x2, ||x||] for dataset X = [(4,-3), (0,1)].

### Q4 [2023-24 EC3M Solutions, 2M]
Compute hinge loss for: (y=0.5, y'=1) and (y=1, y'=-1). Identify misclassified sample.

### Q5 [2023-24 EC3R Solutions, 3.5M]
Given 4 data points (2 classes), problem not linearly separable.
i) Explain why not linearly separable.
ii) Define kernel K(x1,x2) = (4 + x1^T*x2)^2. Compute kernel matrix.
iii) Set up and solve dual optimization. Find decision boundary.

### Q6 [March 2025, 8M]
Constrained optimization problem with Lagrangian formulation:
min x + y subject to alpha*x^2 + beta*y^2 <= 1, beta*x^2 + alpha*y^2 <= 1.
(a) Write dual formulation.
(b) Assuming dual optimal is strictly positive, find optimal primal solution.

### Q7 [March 2025, 6M]
K(x,y) is kernel with mapping phi having d components. Find mapping for kernel (K(x,y)+c)^2. How many components does this mapping contain?

### Q8 [April 2025 Makeup, 8M]
Given data points (1,1,+1), (-1,-1,+1), (1,-1,-1), (-1,1,-1):
(a) Write SVM dual optimization (2M).
(b) Solve for Lagrange multipliers (3M).
(c) Find optimal w and b (3M).

---

## 4. Convex Functions & Convex Optimization

### Q1 [2022-23 Comprehensive, 4M]
i) f1(x) = ||x||_1. Prove or disprove convexity using properties of norms.
ii) g(x) is convex, A in R^{nxn}, b in R^n. Prove or disprove h(x) = g(Ax+b) is convex.

### Q2 [Comprehensive Regular AIML, 1M]
Prove or disprove: C = {x | Ax=b} (all solutions of linear system) is a convex set.

### Q3 [2022-23 Makeup AIML, 1+1+2M]
Set M = {(x,y) in R^2 | x^2+y^2<=5, x+2y=4, x>=0, y>=0}.
i) Formulate constrained optimization to find point in M nearest to origin.
ii) Write the Lagrangian function.
iii) Verify (4/5, 8/5) satisfies KKT conditions. Find Lagrangian multipliers.

### Q4 [2023-24 EC3R Solutions, 4M]
Constrained optimization: min (4-x)^2 + (2-y)^2 subject to lines x-2y+3=0 and x+2y+5=0.
Find closest point on each line to (4,2) using Lagrangian method.

### Q5 [March 2025, 8M]
Primal problem: min x+y subject to alpha*x^2 + beta*y^2 <= 1, beta*x^2 + alpha*y^2 <= 1 (alpha>0, beta>0, alpha!=beta).
(a) Write dual formulation expressed as a(lambda) + 1/p(lambda) + 1/q(lambda).
(b) Find optimal primal solution assuming dual optimal is strictly positive.

### Q6 [April 2025 Makeup, 6M]
Constrained optimization: Minimize f(x,y) = x^2 + y subject to g(x,y) = x^2 - y^2 = 1.
Find critical points using Lagrange multipliers. Classify as minima/maxima.

---

## 5. Linear Algebra - Eigenvalues, Eigenvectors & Matrix Properties

### Q1 [2022-23 Comprehensive, 4M]
Matrix A in R^{nxn} with SVD A = U*Sigma*V^T. ||Sigma||_F^2 = gamma. B = A^T*A.
(a) Prove/disprove alpha = B11+B22+...+Bnn = gamma (claim by G1).
(b) Prove/disprove alpha = sqrt(gamma) (claim by G2).
(c) C = A*A^T. Prove/disprove beta = C11+...+Cnn = gamma^2.

### Q2 [2023-24 EC3R Solutions, 4M]
Given matrix C, find eigenvalues. Then compute:
i) Trace(C^6)
ii) det(C^7)

### Q3 [2023-24 EC3M Solutions, 2.5M]
Given positive definite matrix A. Find Cholesky decomposition A = LL^T. Find eigenvalues of L.

### Q4 [Comprehensive Regular AIML, 2M]
Find rank of A_{nxn} matrix whose entry a_{jk} = j+k-1. Would it change if a_{jk} = j+k-alpha (alpha positive integer)?

### Q5 [April 2025 Makeup, 5M]
Given matrix A:
(a) Find eigenvalues.
(b) Find corresponding eigenvectors.
(c) Determine if matrix is diagonalizable. If yes, find P and D such that A = PDP^{-1}.

---

## 6. Linear Algebra - Vector Spaces, Subspaces & Linear Independence

### Q1 [2023-24 EC3R Solutions, 3M]
Given a,b,c are linearly independent. Prove that {x,y,z} = {b-c, a+c, a-b} is linearly independent.

### Q2 [2023-24 EC3M Solutions, 4M]
Given matrix A with rows R1,...,Rm:
i) Show Ax=0 when <Ri,x>=0 for all i.
ii) Show S={x | <Ri,x>=0} = N(A) is a subspace.
iii) If rank(A)=m, find dim(S).

### Q3 [Comprehensive Regular AIML, 2M]
Prove/disprove: dimension of vector space is independent of field over which it is defined.

### Q4 [Comprehensive Regular AIML, 2M]
Prove: if v1+v2+v3=0, then {v1,v2} spans same subspace as {v2,v3}.

### Q5 [Comprehensive Regular AIML, 2M]
RREF: Two students get same RREF. Another says it's impossible. A senior says both could be correct and X can be recovered if no element is zero. Who is correct?

### Q6 [Comprehensive Regular AIML, 2M]
Given distinct eigenvalues lambda1,...,lambdan, is it possible to generate an orthogonal matrix of order n?

### Q7 [2023-24 EC3R Solutions, 3M]
Given 6x6 matrix A where C1 = sum(C2...C6) = 2*C2. Find two vectors in null space of A.

---

## 7. Calculus - Gradients & Jacobians

### Q1 [2022-23 Comprehensive, 4M]
f(x) = ||Ax-b||^2 + c^T*x + d and g(x) = ||A1^T*A1*x||^2 + ||A2^T*x||^2.
i) Derive gradient of f(x) w.r.t. x.
ii) Derive gradient of g(x) w.r.t. x.

### Q2 [2022-23 Comprehensive, 1+2M]
f(x) = [x^T*Q*x, b^T*x]^T where Q is 3x3 symmetric positive definite.
i) Find gradient (Jacobian) of f.
ii) Find linear approximation of f about (0,0,0).

### Q3 [2023-24 EC3M Solutions - Q3B]
Sigmoid sigma(z) = (1+e^{-z})^{-1}.
i) Derive d(sigma)/dz = sigma(z)(1-sigma(z)).
ii) Given f(x,y) involving log and sigma, simplify f.
iii) Compute partial f/partial x and partial f/partial y.
iv) Find Taylor polynomial of degree 1 at (0,0).

### Q4 [2023-24 EC3R Solutions, 3.5M]
Given loss function L(beta) = (1/2p)||y-beta||^2 + lambda*||W*beta||^2:
i) Express as sum of individual losses Lj(beta).
ii) Derive gradient of Lj(beta).
iii) Derive gradient of L(beta).

### Q5 [March 2025, 4M]
f(x,y) = 2x^2 + beta*y^2. Derive gradient and use for optimal step size calculation.

### Q6 [April 2025 Makeup, 4M]
f(x,y) = x^2 + beta*y^2. Derive gradient and closed form optimal step size.

---

## 8. Inner Products, Norms & Distance Functions

### Q1 [2022-23 Comprehensive, 3+3M]
Matrix A = [[1,0,rho],[0,1,rho],[rho,rho,1]].
i) Find conditions on rho such that <x,y>_A = x^T*A*y is an inner product on R^3.
ii) Is [1,0,0]^T perpendicular to [0,1,0]^T w.r.t. this inner product? Find all z perpendicular to both.

### Q2 [Comprehensive Regular AIML, 2M]
d(x,y) = sum|xi-yi|. Prove or disprove this is a valid distance function by verifying all properties.

### Q3 [2022-23 Comprehensive, 3M]
Find 2x2 matrix M with trace(M)=0 such that (||M-A||_2)^2 is minimum where A = [[1,0],[0,2]].

---

## 9. Critical Points & Function Analysis (Multivariable Calculus)

### Q1 [2023-24 EC3R Solutions, 3M]
f(x,y) = (x^2+y^2)*e^{-(x^2+y^2)}. Find set A of all critical points. Determine nature of (0,0) using Hessian.

### Q2 [2022-23 Makeup AIML, 3+1M]
f(x) = 3x^4 - 20x^3 + 36x^2 + 10.
i) Find stationary points, classify, find global minima.
ii) Better initial condition for GD: x=0.5 or x=3.5?

### Q3 [March 2025, 2M]
f(z) = 3z^4 - 6z^3 - 42z^2 + 2z + 72. Find critical points in [-5,5]. Classify using second derivative test.

### Q4 [April 2025 Makeup, 2M]
f(z) = 3z^4 - 8z^3 + 6z^2. Find critical points in [-3,3]. Classify closest to left end.

### Q5 [April 2025 Makeup, 6M]
f(x,y) = x^2 + y subject to x^2 - y^2 = 1. Find critical points using Lagrange multipliers.

---

## 10. Singular Value Decomposition (SVD)

### Q1 [2022-23 Comprehensive, 4M]
SVD of A = U*Sigma*V^T where ||Sigma||_F^2 = gamma. Prove/disprove claims about trace of A^T*A and A*A^T.

### Q2 [April 2025 Makeup, 5M]
Given matrix A:
(a) Compute A^T*A.
(b) Find singular values of A.
(c) Construct U, Sigma, V matrices for SVD.

---

## 11. Kernel Methods & Feature Transformations

### Q1 [2023-24 EC3M, 5M]
Find transformation to make 1D data linearly separable. Points: (7,0)->+1, (9,0)->+1, (8,0)->-1, (10,0)->-1.

### Q2 [2023-24 EC3M, 3M]
Compute kernel matrix using phi(x) = [x1, x2, ||x||] for X = [(4,-3), (0,1)].

### Q3 [2023-24 EC3R, 3.5M]
Kernel K(x1,x2) = (4+x1^T*x2)^2. Compute kernel matrix for 4 points. Set up dual optimization.

### Q4 [2023-24 EC3R Solutions, 2M]
Feature transformation phi(x) = [x1,...,xm, x1^3,...,xm^3, x1*x2*x3,...,x_{m-2}*x_{m-1}*xm].
Dimension of transformed data? Derive kernel function K(x,y).

### Q5 [March 2025, 6M]
K(x,y) is kernel with mapping phi of d components. Find mapping for (K(x,y)+c)^2. Number of components?

---

## 12. Constrained Optimization & KKT Conditions

### Q1 [2022-23 Makeup AIML, 4M]
M = {(x,y) | x^2+y^2<=5, x+2y=4, x>=0, y>=0}. Find nearest point to origin.
Write Lagrangian. Verify (4/5, 8/5) satisfies KKT conditions.

### Q2 [2023-24 EC3R, 6M]
Primal: min x^2_1 + x^2_2 - 4x1 - 4x2 subject to x^2_1 - x_2 <= 0, x1+x2-2 <= 0.
i) Find Lagrangian and solve for x1, x2.
ii) Does strong duality hold? Justify.

### Q3 [March 2025, 8M]
min x+y subject to alpha*x^2 + beta*y^2 <= 1, beta*x^2 + alpha*y^2 <= 1.
Write dual. Find primal solution from complementary slackness.

### Q4 [April 2025 Makeup, 6M]
Minimize x^2 + y subject to x^2 - y^2 = 1. Use Lagrange multipliers.

---

## 13. Matrix Decomposition (Cholesky, LU)

### Q1 [2023-24 EC3M, 2.5M]
Given positive definite matrix A:
Find Cholesky decomposition A = LL^T. Find eigenvalues of L.

---

## 14. Taylor Series & Linear Approximation

### Q1 [2022-23 Comprehensive, 2M]
f(x) = [x^T*Q*x, b^T*x]^T. Find linear approximation about (0,0,0).

### Q2 [2023-24 EC3M, 1M]
Find Taylor polynomial of degree 1 of f(x,y) = (1-alpha)(x+beta*y) - ln(sigma(x+beta*y)) at (0,0).

---

## 15. Loss Functions (Hinge Loss, Cross-Entropy)

### Q1 [2023-24 EC3M, 2M]
Compute hinge loss for samples: (y=0.5, y'=1) and (y=1, y'=-1). Identify misclassified sample.

### Q2 [2023-24 EC3M - Q3B]
Cross-entropy loss involving sigmoid function. Derive gradient expressions.

---

## 16. Null Space & Column Space

### Q1 [2023-24 EC3M, 4M]
Given A with rows R1,...,Rm. Show S = {x | <Ri,x>=0} = N(A). If rank(A)=m, find dim(S).

### Q2 [2023-24 EC3R, 2M]
6x6 matrix where C1 = sum(C2..C6) = 2*C2. Find two independent vectors in null space.

---
