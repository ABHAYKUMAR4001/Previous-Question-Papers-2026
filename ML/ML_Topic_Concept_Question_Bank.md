# Machine Learning Question Bank --- Topic → Concept → Exact Question

> **Purpose:** Organize every question by **Topic → Concept → Exact
> Question**. As more papers/files are added, questions should be
> inserted under the closest existing concept. Create a new
> concept/topic only when necessary.
>
> **Source currently included:** Sample Paper --- Comprehensive
> Examination (EC-3 Make-up), AIMLCZG565/DSECLZG565.

## 1. Linear Regression / Regularization

### Concept: Ridge Regression --- Regularization Strength, Bias--Variance & Coefficient Shrinkage

**Question (Sample Paper Q1 --- 4 Marks)**

A data science team is building a linear regression model to predict
house prices using 120 correlated features (area, number of rooms,
locality index, proximity to schools, etc.).

The training dataset has 8,000 samples, but the validation error
fluctuates significantly across folds. To control overfitting, the team
applies Ridge Regression and experiments with different values of the
regularization parameter λ.

They observe the following behaviors: - Case 1: λ = 0 - Case 2: λ =
0.01 - Case 3: λ = 10⁴

(a) For each case above, describe the expected behavior of the model
    coefficients and the bias--variance tradeoff. **[3 Marks]**

(b) In Case 3, the team notices that all features still have non-zero
    coefficients, although many are extremely small. Explain why Ridge
    Regression does not perform feature selection, even when λ is very
    large. **[1 Mark]**

---

## 2. Naive Bayes

### Concept: Gaussian Naive Bayes --- Mixed Continuous & Categorical Features

**Question (Sample Paper Q2 --- 5 Marks)**

As a part of efforts to improve students' performance in the exams, you
have been given the data showing number of study hours spent by
students, their gender and their final results as pass or fail. Using
this sample dataset, apply Naïve Bayes classification technique, to
classify the test case **{No of study hours = 3.5, Gender = "male"}**
either as "Pass", or "Fail".

| No. of study hours | Gender | Final result |
|---:|---|---|
| 4.5 | Male | Pass |
| 7 | Female | Pass |
| 2 | Male | Fail |
| 4 | Female | Fail |
| 2.5 | Male | Fail |
| 3 | Female | Fail |
| 8.3 | Male | Fail |
| 8 | Female | Pass |
| 9 | Male | Pass |

---

## 3. K-Nearest Neighbours (KNN) / Local Regression

### Concept: KNN Regression --- Min-Max Normalization & Euclidean Distance

### Concept: Locally Weighted Linear Regression --- Gaussian Kernel & One GD Update

**Question (Sample Paper Q3 --- 6 Marks)**

A consumer electronics company wants to predict the scaled-down selling
price (continuous) of a new gadget based on two features: (i) Size (in
cm) and (ii) Warranty period (in months). The training set has mixed
magnitudes, so you must work in a comparable feature space to compute
neighborhoods reliably. For a query gadget **Q with Size = 7 cm and
Warranty = 18 months**, produce two estimates: (1) a standard k-NN
regression estimate using **k = 4** (simple mean of the 4 nearest
prices), and (2) a locally weighted linear regression estimate using a
Gaussian kernel around the query and **ONE gradient-descent (GD)
update**.

Training data (Size, Warranty, Price): P0(4,6,6.0), P1(6,12,7.5),
P2(7,24,12.0), P3(8,6,8.0), P4(10,12,9.0), P5(12,24,11.0),
P6(5,24,10.5), P7(9,18,10.0)

Instructions:
- Apply min--max normalization separately to Size and Warranty using the min/max from the training set.
- Compute Euclidean distances in the normalized 2D space and find the 4 nearest neighbors.
- Standard k-NN regression: unweighted mean of the 4 neighbor prices.
- Locally weighted linear regression: ŷ = w0 + w1x1 + w2x2, where (x1,x2) are normalized features.
- Kernel: K(d) = exp(−d²/(2b²)), with b = 2.
- Start from w0 = 1.5, w1 = 0.8, w2 = 0.4 and learning rate α = 0.1.
- Perform exactly ONE GD update using only the 4 nearest neighbors.

(a) Compute the standard 4-NN prediction for Q. **[2 Marks]**

(b) Compute K(d) for the 4 neighbors, perform ONE GD update, and report
    (w0_new, w1_new, w2_new) and the locally weighted prediction for Q
    after the update. **[3 Marks]**

(c) State one reason why the two predictions differ for this dataset.
    **[1 Mark]**

---

## 4. Ensemble Learning

### Concept: Bagging vs AdaBoost --- Sources of Learner Diversity

### Concept: Random Forest --- Feature Subsampling & Tree Correlation

### Concept: Majority Voting --- Ensemble Accuracy

**Question (Sample Paper Q4 --- 6 Marks)**

A telecom company is building a machine learning system to predict
customer churn (Yes/No) using historical usage and billing data. The
dataset contains 20,000 customers and 30 features (call duration,
recharge frequency, complaints, etc.).

The data science team experiments with three ensemble approaches:
- Bagging with decision trees
- Random Forest
- AdaBoost with decision stumps

During model evaluation, the team observes:
- Individual decision trees are high-variance models.
- Each base classifier trained independently achieves an accuracy of approximately 70%.
- The business requirement emphasizes robustness and generalization, not just single-model accuracy.

(a) The team trains 100 decision trees using Bagging and 100 weak
    learners using AdaBoost. Explain, with reference to the training
    process, how each method creates diversity among its base learners.
    Your answer must clearly distinguish data-level randomness from
    error-driven focus. **[2 Marks]**

(b) When switching from Bagging to Random Forest, the team notices
    improved validation performance. Identify the additional source of
    randomness introduced by Random Forest and explain numerically or
    structurally why this reduces correlation among trees compared to
    standard Bagging. **[2 Marks]**

(c) Suppose the final ensemble uses 3 independently trained classifiers,
    each with accuracy 0.7, and predictions are combined using majority
    voting.

1. Compute the probability that the ensemble prediction is correct.
2. Based on your calculation, state whether the ensemble is better than
   an individual classifier, and justify numerically. **[2 Marks]**

---

## 5. Gaussian Mixture Models (GMM) / EM

### Concept: EM Algorithm --- E-Step Responsibilities

### Concept: Log-Likelihood

### Concept: EM Algorithm --- M-Step Parameter Updates

### Concept: GMM vs K-Means --- Soft vs Hard Assignment

**Question (Sample Paper Q5 --- 6 Marks)**

A reliability team is analyzing machine vibration data collected from
four machines, represented by a single standardized vibration feature:

**X = {−4, −2, 0, 3}**

They believe the data is generated by two latent operating modes and
model it using a Gaussian Mixture Model (GMM) with two components.

Initial parameters:
- π1 = 0.6, π2 = 0.4
- μ1 = −3, μ2 = 2
- σ1² = σ2² = 1

Gaussian density: **N(x | μ, σ²) = (1 / √(2πσ²)) exp(−(x−μ)² / (2σ²))**

(a) Perform the E-step. Compute the responsibilities γi1 and γi2 for
    each data point. **[2 Marks]**

(b) Using the mixture likelihoods obtained above, compute the
    log-likelihood of the data at iteration 0. **[0.5 Mark]**

(c) Perform the M-step and compute the updated mixing weights, means,
    and variances. **[2 Marks]**

(d) Now apply one iteration of K-Means with k = 2 using initial
    centroids −3 and 2. Compute the updated centroids and compare them
    with the updated GMM means. State one reason for any difference
    observed. **[1.5 Marks]**

---

## 6. Gradient Boosting

### Concept: Gradient Boosting Regression --- Initial Prediction & Pseudo-Residuals

### Concept: Regression Tree Leaf Predictions

### Concept: Learning-Rate Update After One Boosting Iteration

**Question (Sample Paper Q6 --- 3 Marks)**

A logistics company wants to predict Delivery Time (in minutes) for
short intra-city deliveries using Gradient Boosting Regression with
squared loss.

| Job | Traffic Level | Distance (km) | Vehicle | Actual Time (y) |
|---|---|---:|---|---:|
| J1 | High | 3 | Bike | 34 |
| J2 | High | 6 | Van | 52 |
| J3 | Low | 4 | Bike | 28 |
| J4 | Low | 8 | Van | 46 |
| J5 | High | 5 | Bike | 40 |

Setup:
- Initial model F₀ predicts a constant value equal to the mean of y.
- Squared loss is used, so pseudo-residuals are rᵢ = yᵢ − F₀(xᵢ).
- Learning rate η = 0.2.
- First weak learner h₁(x): If Traffic Level = Low → Leaf L_A; otherwise, if Distance ≤ 4 → Leaf L_B; else → Leaf L_C.
- Each leaf predicts the average residual of the samples reaching that leaf.

(a) Compute F₀ and the pseudo-residuals for all samples. **[1 Mark]**

(b) Compute the leaf predictions L_A, L_B, and L_C. **[1 Mark]**

(c) Compute the updated prediction F₁(x) and the new residual for Job J2
    after one boosting iteration. **[1 Mark]**

---

## 7. Support Vector Machines (SVM)

### Concept: Maximum-Margin Hyperplane --- Geometric Construction from Support Vectors

### Concept: Canonical Margin --- Computing w and b

### Concept: Dual Formulation --- Lagrange Multipliers & Support Vectors

### Concept: Margin Width & Robustness

### Concept: Kernelized SVM --- Computational Cost

**Question (Sample Paper Q7 --- 8 Marks)**

A financial institution is using a Support Vector Machine (SVM) to
classify transactions as High Risk (+1) or Low Risk (−1). Each
transaction is represented using two structured numeric features x₁ and
x₂. In later stages, the bank plans to include unstructured text
embeddings from transaction remarks.

Training data:

| Point | x₁ | x₂ | Class y |
|---|---:|---:|---:|
| P1 | 1 | 4 | +1 |
| P2 | 2 | 3 | +1 |
| P3 | 4 | 1 | −1 |
| P4 | 5 | 2 | −1 |

Assume that in the optimal maximum-margin solution, only P2 and P3 are
support vectors.

(a) Using geometric reasoning, identify the equation of the
    maximum-margin separating hyperplane for the given data. Clearly
    justify your choice based on the support vectors. **[2 Marks]**

(b) Assuming that the support vectors satisfy the canonical margin
    conditions yᵢ(wᵀxᵢ + b) = 1, compute a valid weight vector w and
    bias b. Write the resulting decision function f(x) = wᵀx + b. **[2 Marks]**

(c) State the condition on the Lagrange multipliers αᵢ that identifies a
    support vector in the dual formulation of SVM. Explain why only P2
    and P3 influence the final classifier. **[1.5 Marks]**

(d) Compute ||w|| and the margin width 2/||w||. What does a
    larger margin imply about the classifier's robustness? **[2 Marks]**

(e) To incorporate text embeddings, the bank switches to a kernelized
    SVM. Consider the kernels:

- K₁(x,z) = (xᵀz + 2)²
- K₂(x,z) = exp(−0.5||x−z||²)
- K₃(x,z) = sin(xᵀz)

State one reason why kernelized SVMs may become computationally
expensive. **[0.5 Mark]**

---

## 8. Decision Trees

### Concept: Overfitting --- Tree Depth & Minimum Leaf Size

### Concept: Stopping Conditions --- Complexity vs Generalization

**Question (Sample Paper Q8 --- 2 Marks)**

A bank trains two Decision Tree models to predict loan default:

**Model A:**
- The tree is allowed to grow without depth restriction.
- A leaf node may contain even a single training sample.
- Training Accuracy = 99%
- Test Accuracy = 71%

**Model B:**
- The tree depth is restricted to 4 levels.
- Each leaf must contain at least 25 training samples.
- Training Accuracy = 86%
- Test Accuracy = 83%

(a) Which model is overfitting? **[0.5 Mark]**

(b) Why does the other model perform well? **[0.5 Mark]**

(c) Briefly explain how the stopping conditions influence model
    complexity and generalization. **[1 Mark]**
