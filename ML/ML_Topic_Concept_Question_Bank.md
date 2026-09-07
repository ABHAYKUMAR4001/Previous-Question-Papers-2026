# Machine Learning Question Bank --- Topic → Concept → Exact Question

> **Purpose:** Organize every question by **Topic → Concept → Exact Question**. As more papers/files are added, questions should be inserted under the closest existing concept. Create a new concept/topic only when necessary.
>
> **Sources currently included:**
> 1. Sample Paper --- Comprehensive Examination (EC-3 Make-up), AIMLCZG565/DSECLZG565.
> 2. NSP4-S2-25_EC3R_AIMLCZG565 --- Machine Learning Question Paper.

## 1. Linear Regression / Regularization

### Concept: Ridge Regression --- Regularization Strength, Bias--Variance & Coefficient Shrinkage

**Question (Sample Paper Q1 --- 4 Marks)**

A data science team is building a linear regression model to predict house prices using 120 correlated features (area, number of rooms, locality index, proximity to schools, etc.).

The training dataset has 8,000 samples, but the validation error fluctuates significantly across folds. To control overfitting, the team applies Ridge Regression and experiments with different values of the regularization parameter λ.

They observe the following behaviors: - Case 1: λ = 0 - Case 2: λ = 0.01 - Case 3: λ = 10⁴

(a) For each case above, describe the expected behavior of the model coefficients and the bias--variance tradeoff. **[3 Marks]**

(b) In Case 3, the team notices that all features still have non-zero coefficients, although many are extremely small. Explain why Ridge Regression does not perform feature selection, even when λ is very large. **[1 Mark]**

---

## 2. Logistic Regression

### Concept: L2-Regularized Logistic Regression --- Cross-Entropy, Gradient Descent & Weight Shrinkage

**Question (NSP4-S2-25 Exam Q2 --- 4 Marks)**

A streaming service wants to predict subscription cancellation (y = 1: cancels, y = 0: stays) using two normalized features: Watch Hours per week (x1) and Customer Complaints (x2), both scaled 0 to 1.

| Customer | Watch Hours x1 | Complaints x2 | Label y |
|---|---:|---:|---:|
| C1 | 0.8 | 0.1 | 0 |
| C2 | 0.2 | 0.9 | 1 |
| C3 | 0.7 | 0.2 | 0 |

Initial weights: w0 = 0, w1 = -1, w2 = 1. Learning rate: α = 0.5. Regularization constant: λ = 0.4.

(a) Write the L2-regularized cross-entropy cost function for logistic regression, and state how its gradient update rule differs from plain (unregularized) logistic regression GD. **[1 Mark]**

(b) Using the data and initial weights above, compute σ(z) for each customer, then perform one step of regularized Gradient Descent to obtain w0*, w1*, w2*. **[2 Marks]**

(c) Compare the magnitude of w1* obtained here with what it would be under plain (unregularized, λ = 0) logistic regression GD. What does this tell you about how L2 regularization affects convergence and weight magnitude in classification models? **[1 Mark]**

---

## 3. Naive Bayes

### Concept: Gaussian Naive Bayes --- Mixed Continuous & Categorical Features

**Question (Sample Paper Q2 --- 5 Marks)**

As a part of efforts to improve students' performance in the exams, you have been given the data showing number of study hours spent by students, their gender and their final results as pass or fail. Using this sample dataset, apply Naïve Bayes classification technique, to classify the test case **{No of study hours = 3.5, Gender = "male"}** either as "Pass", or "Fail".

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

### Concept: Multinomial Naive Bayes --- Laplace Smoothing & Posterior Classification

**Question (NSP4-S2-25 Exam Q6(a,b) --- 3 Marks)**

A movie-review platform wants to tag reviews as Positive or Negative using a Multinomial Naive Bayes (bag-of-words) classifier. From the training corpus, word counts within each class are:

| Word | Count in Positive reviews | Count in Negative reviews |
|---|---:|---:|
| great | 6 | 1 |
| boring | 1 | 5 |
| acting | 4 | 2 |
| slow | 2 | 4 |
| brilliant | 3 | 0 |

Total words in Positive class = 16. Total words in Negative class = 12. Vocabulary size |V| = 5.

Class priors: P(Positive) = 0.6, P(Negative) = 0.4 (6 positive and 4 negative reviews in the training set).

Test review: "acting was slow but great" (only words present in the vocabulary above are used: acting, slow, great).

(a) Using Laplace smoothing (k=1), compute the smoothed likelihood P(word | class) for each of the three test words (acting, slow, great) under both Positive and Negative. **[1.5 Marks]**

(b) Using these likelihoods, compute the unnormalized posterior score for both classes and determine the predicted class. **[1.5 Marks]**

### Concept: Generative vs Discriminative Models --- Naive Bayes vs Logistic Regression

**Question (NSP4-S2-25 Exam Q6(c) --- 1 Mark)**

Naive Bayes here models P(Y) and P(X|Y) separately (a generative approach), while Logistic Regression models P(Y|X) directly (a discriminative approach) - the parametric form of P(Y|X) implied by Gaussian Naive Bayes is actually the same form Logistic Regression uses directly. Briefly explain this generative-vs-discriminative distinction, and why the two approaches can still produce different results despite that shared form. **[1 Mark]**

### Concept: Conditional Independence Assumption --- Correlated Features & Overconfident Posteriors

**Question (NSP4-S2-25 Exam Q6(d) --- 1 Mark)**

Words like "great" and "brilliant" are likely to co-occur strongly in genuinely positive reviews (and "boring"/"slow" in genuinely negative ones) - violating Naive Bayes' word-independence assumption. Explain how this could make Naive Bayes' posterior scores overconfident, and why Logistic Regression might handle such correlated words more gracefully. **[1 Mark]**

---

## 4. K-Nearest Neighbours (KNN) / Local Regression

### Concept: KNN Regression --- Min-Max Normalization & Euclidean Distance

### Concept: Locally Weighted Linear Regression --- Gaussian Kernel & One GD Update

**Question (Sample Paper Q3 --- 6 Marks)**

A consumer electronics company wants to predict the scaled-down selling price (continuous) of a new gadget based on two features: (i) Size (in cm) and (ii) Warranty period (in months). The training set has mixed magnitudes, so you must work in a comparable feature space to compute neighborhoods reliably. For a query gadget **Q with Size = 7 cm and Warranty = 18 months**, produce two estimates: (1) a standard k-NN regression estimate using **k = 4** (simple mean of the 4 nearest prices), and (2) a locally weighted linear regression estimate using a Gaussian kernel around the query and **ONE gradient-descent (GD) update**.

Training data (Size, Warranty, Price): P0(4,6,6.0), P1(6,12,7.5), P2(7,24,12.0), P3(8,6,8.0), P4(10,12,9.0), P5(12,24,11.0), P6(5,24,10.5), P7(9,18,10.0)

Instructions:
- Apply min--max normalization separately to Size and Warranty using the min/max from the training set.
- Compute Euclidean distances in the normalized 2D space and find the 4 nearest neighbors.
- Standard k-NN regression: unweighted mean of the 4 neighbor prices.
- Locally weighted linear regression: ŷ = w0 + w1x1 + w2x2, where (x1,x2) are normalized features.
- Kernel: K(d) = exp(−d²/(2b²)), with b = 2.
- Start from w0 = 1.5, w1 = 0.8, w2 = 0.4 and learning rate α = 0.1.
- Perform exactly ONE GD update using only the 4 nearest neighbors.

(a) Compute the standard 4-NN prediction for Q. **[2 Marks]**

(b) Compute K(d) for the 4 neighbors, perform ONE GD update, and report (w0_new, w1_new, w2_new) and the locally weighted prediction for Q after the update. **[3 Marks]**

(c) State one reason why the two predictions differ for this dataset. **[1 Mark]**

### Concept: KNN Classification --- Manhattan Distance & Unweighted Voting

### Concept: Distance-Weighted KNN --- Inverse-Distance Voting

### Concept: Feature-Weighted Distance Metric --- Effect on Neighbourhood & Classification

**Question (NSP4-S2-25 Exam Q7 --- 7 Marks)**

A manufacturing plant records two sensor indicators for machines: vibration score (x1) and temperature-deviation score (x2). Historical machines have been labelled as Normal (N) or Fault (F) after inspection. A newly observed machine must be classified from its sensor readings. Machines with similar sensor patterns tend to have similar operating conditions.

| Machine | Vibration x1 | Temperature deviation x2 | Condition |
|---|---:|---:|---|
| M1 | 5 | 6 | F |
| M2 | 4 | 4 | F |
| M3 | 7 | 6 | N |
| M4 | 8 | 6 | N |
| M5 | 9 | 6 | N |
| M6 | 2 | 2 | F |
| M7 | 10 | 8 | N |
| M8 | 1 | 7 | F |

Query machine: xq = (5, 5)

(a) Why is an instance-based method such as KNN a reasonable choice for this problem, compared with algorithms like decision trees or logistic regression? **[1 Mark]**

(b) Compute the Manhattan distance from xq to each machine and identify the five nearest neighbours. **[1 Mark]**

(c) Classify xq using unweighted 5-NN and show the vote totals for N and F. **[1 Mark]**

(d) Classify xq using distance-weighted 5-NN with wi = 1 / d(xq, xi) and show the total weight for each class. **[2 Marks]**

(e) Compare the predictions in (c) and (d). What advantage of weighted KNN does this case demonstrate? **[1 Mark]**

(f) Now the distance metric is changed so Temperature Deviation (x2) counts twice as much as Vibration (x1): d'(xq, xi) = |Δx1| + 2|Δx2|. Without recomputing all distances from scratch, analyze whether the classification of xq is likely to change under distance-weighted 5-NN with this new metric, and justify your answer using how x1 and x2 vary among the original five nearest neighbours. **[1 Mark]**

---

## 5. Ensemble Learning

### Concept: Bagging vs AdaBoost --- Sources of Learner Diversity

### Concept: Random Forest --- Feature Subsampling & Tree Correlation

### Concept: Majority Voting --- Ensemble Accuracy

**Question (Sample Paper Q4 --- 6 Marks)**

A telecom company is building a machine learning system to predict customer churn (Yes/No) using historical usage and billing data. The dataset contains 20,000 customers and 30 features (call duration, recharge frequency, complaints, etc.).

The data science team experiments with three ensemble approaches:
- Bagging with decision trees
- Random Forest
- AdaBoost with decision stumps

During model evaluation, the team observes:
- Individual decision trees are high-variance models.
- Each base classifier trained independently achieves an accuracy of approximately 70%.
- The business requirement emphasizes robustness and generalization, not just single-model accuracy.

(a) The team trains 100 decision trees using Bagging and 100 weak learners using AdaBoost. Explain, with reference to the training process, how each method creates diversity among its base learners. Your answer must clearly distinguish data-level randomness from error-driven focus. **[2 Marks]**

(b) When switching from Bagging to Random Forest, the team notices improved validation performance. Identify the additional source of randomness introduced by Random Forest and explain numerically or structurally why this reduces correlation among trees compared to standard Bagging. **[2 Marks]**

(c) Suppose the final ensemble uses 3 independently trained classifiers, each with accuracy 0.7, and predictions are combined using majority voting.

1. Compute the probability that the ensemble prediction is correct.
2. Based on your calculation, state whether the ensemble is better than an individual classifier, and justify numerically. **[2 Marks]**

### Concept: AdaBoost --- Weighted Error & Weak-Learner Weight

### Concept: AdaBoost --- Sample-Weight Update & Normalization

### Concept: AdaBoost --- Final Weighted Ensemble Prediction

### Concept: AdaBoost --- Weak Learner with Error > 0.5 & Robustness vs Majority Voting

**Question (NSP4-S2-25 Exam Q3 --- 6 Marks)**

A bank develops an AdaBoost classifier to flag transactions as Fraudulent (+1) or Genuine (-1). At a particular boosting round, the training observations have the following weights, actual classes, and current weak-learner predictions:

| Transaction | Current Weight (wi) | Actual Class (yi) | Weak Learner Prediction ht(xi) |
|---|---:|---:|---:|
| T1 | 0.1 | 1 | 1 |
| T2 | 0.2 | 1 | -1 |
| T3 | 0.25 | -1 | -1 |
| T4 | 0.15 | -1 | 1 |
| T5 | 0.3 | 1 | 1 |

Use: weighted error εt = Σ(wi for misclassified i); learner weight αt = 0.5 × ln[(1-εt)/εt]; unnormalized weight update wi ← wi × exp(-αt · yi · ht(xi)); normalized weight = unnormalized weight / Z, where Z is the sum of all unnormalized weights.

After three boosting rounds, three weak learners are available for a new transaction q:

| Weak Learner | Learner Weight | Prediction for q |
|---|---:|---:|
| h1 | 0.6 | 1 |
| h2 | 0.31 | -1 |
| h3 | 0.8 | -1 |

(a) Identify the misclassified transactions, compute the weighted error εt, the learner weight αt, and interpret what the sign of αt indicates about this weak learner. **[1.5 Marks]**

(b) Compute the unnormalized and normalized updated weight of every transaction. Which transactions receive increased attention in the next round? **[2 Marks]**

(c) Compute the final weighted ensemble score for transaction q using h1, h2, h3, and determine its predicted class. **[1 Mark]**

(d) Suppose a subsequent weak learner produces an error rate of 0.55. Should it be included in its current form? State the corrective action indicated by the boosting procedure, and briefly explain why AdaBoost's weighted combination is generally more robust than plain (unweighted) majority voting when base classifiers have very different competence levels. **[1.5 Marks]**

---

## 6. Gaussian Mixture Models (GMM) / EM

### Concept: EM Algorithm --- E-Step Responsibilities

### Concept: Log-Likelihood

### Concept: EM Algorithm --- M-Step Parameter Updates

### Concept: GMM vs K-Means --- Soft vs Hard Assignment

**Question (Sample Paper Q5 --- 6 Marks)**

A reliability team is analyzing machine vibration data collected from four machines, represented by a single standardized vibration feature:

**X = {−4, −2, 0, 3}**

They believe the data is generated by two latent operating modes and model it using a Gaussian Mixture Model (GMM) with two components.

Initial parameters:
- π1 = 0.6, π2 = 0.4
- μ1 = −3, μ2 = 2
- σ1² = σ2² = 1

Gaussian density: **N(x | μ, σ²) = (1 / √(2πσ²)) exp(−(x−μ)² / (2σ²))**

(a) Perform the E-step. Compute the responsibilities γi1 and γi2 for each data point. **[2 Marks]**

(b) Using the mixture likelihoods obtained above, compute the log-likelihood of the data at iteration 0. **[0.5 Mark]**

(c) Perform the M-step and compute the updated mixing weights, means, and variances. **[2 Marks]**

(d) Now apply one iteration of K-Means with k = 2 using initial centroids −3 and 2. Compute the updated centroids and compare them with the updated GMM means. State one reason for any difference observed. **[1.5 Marks]**

---

## 7. K-Means Clustering

### Concept: K-Means --- One Iteration, Euclidean Distance, Cluster Assignment & Centroid Update

**Question (NSP4-S2-25 Exam Q1(a) --- 3 Marks)**

A logistics company wants to group delivery locations using two operational features: x1 = average delivery time (minutes) and x2 = average number of packages delivered per trip.

| Location | x1: Avg. delivery time | x2: Packages/trip |
|---|---:|---:|
| P | 2 | 3 |
| Q | 3 | 4 |
| R | 4 | 5 |
| S | 5 | 5 |
| T | 6 | 6 |
| U | 7 | 7 |
| V | 8 | 6 |
| W | 9 | 7 |

Using K-Means with initial centroids C1 = (2,3) and C2 = (9,7), perform one iteration using Euclidean distance. Show the distance of every point to both centroids, the resulting cluster assignments, and the updated centroids. **[3 Marks]**

### Concept: K-Means --- Sensitivity to Initial Centroids

**Question (NSP4-S2-25 Exam Q1(b) --- 2 Marks)**

Suppose instead the initial centroids had been chosen as C1' = (4,5) and C2' = (5,5) - two nearby, very similar points, rather than two well-separated extremes. Without recomputing fully, reason about whether this choice is likely to produce a good final clustering, and explain why K-Means' outcome is sensitive to the choice of initial centroids. **[2 Marks]**

### Concept: K-Means --- Limitations & Alternative Clustering Approaches

**Question (NSP4-S2-25 Exam Q1(c) --- 2 Marks)**

K-Means assumes clusters are roughly compact and similar in size. Describe one scenario (from the limitations covered in class - differing cluster sizes, differing densities, non-globular shapes, or outliers) where K-Means would fail to produce a meaningful clustering, and name an alternative approach that better handles that specific scenario. **[2 Marks]**

---

## 8. Gradient Boosting

### Concept: Gradient Boosting Regression --- Initial Prediction & Pseudo-Residuals

### Concept: Regression Tree Leaf Predictions

### Concept: Learning-Rate Update After One Boosting Iteration

**Question (Sample Paper Q6 --- 3 Marks)**

A logistics company wants to predict Delivery Time (in minutes) for short intra-city deliveries using Gradient Boosting Regression with squared loss.

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

(c) Compute the updated prediction F₁(x) and the new residual for Job J2 after one boosting iteration. **[1 Mark]**

---

## 9. Support Vector Machines (SVM)

### Concept: Maximum-Margin Hyperplane --- Geometric Construction from Support Vectors

### Concept: Canonical Margin --- Computing w and b

### Concept: Dual Formulation --- Lagrange Multipliers & Support Vectors

### Concept: Margin Width & Robustness

### Concept: Kernelized SVM --- Computational Cost

**Question (Sample Paper Q7 --- 8 Marks)**

A financial institution is using a Support Vector Machine (SVM) to classify transactions as High Risk (+1) or Low Risk (−1). Each transaction is represented using two structured numeric features x₁ and x₂. In later stages, the bank plans to include unstructured text embeddings from transaction remarks.

Training data:

| Point | x₁ | x₂ | Class y |
|---|---:|---:|---:|
| P1 | 1 | 4 | +1 |
| P2 | 2 | 3 | +1 |
| P3 | 4 | 1 | −1 |
| P4 | 5 | 2 | −1 |

Assume that in the optimal maximum-margin solution, only P2 and P3 are support vectors.

(a) Using geometric reasoning, identify the equation of the maximum-margin separating hyperplane for the given data. Clearly justify your choice based on the support vectors. **[2 Marks]**

(b) Assuming that the support vectors satisfy the canonical margin conditions yᵢ(wᵀxᵢ + b) = 1, compute a valid weight vector w and bias b. Write the resulting decision function f(x) = wᵀx + b. **[2 Marks]**

(c) State the condition on the Lagrange multipliers αᵢ that identifies a support vector in the dual formulation of SVM. Explain why only P2 and P3 influence the final classifier. **[1.5 Marks]**

(d) Compute ||w|| and the margin width 2/||w||. What does a larger margin imply about the classifier's robustness? **[2 Marks]**

(e) To incorporate text embeddings, the bank switches to a kernelized SVM. Consider the kernels:

- K₁(x,z) = (xᵀz + 2)²
- K₂(x,z) = exp(−0.5||x−z||²)
- K₃(x,z) = sin(xᵀz)

State one reason why kernelized SVMs may become computationally expensive. **[0.5 Mark]**

### Concept: SVM Hyperparameters --- C, Gamma, Overfitting & Linear Boundary Suitability

**Question (NSP4-S2-25 Exam Q4(a) --- 3 Marks)**

A semiconductor company uses an SVM classifier to identify defective chips from two normalized inspection features: surface irregularity and thermal deviation. Two candidate models are trained:

- Model A: Linear SVM, C = 0.5; training accuracy = 91%, test accuracy = 89%
- Model B: polynomial-kernel SVM, C = 100, gamma = 20; training accuracy = 100%, test accuracy = 76%

Which model is overfitting? Explain the effect of C and gamma. What do the results suggest about the suitability of a linear boundary for this dataset? **[3 Marks]**

### Concept: Hard-Margin SVM --- Primal Formulation, Lagrangian & Stationarity Conditions

**Question (NSP4-S2-25 Exam Q4(b) --- 3 Marks)**

Write the primal formulation for Model A's hard-margin SVM (minimize ½||w||² subject to yi(wᵗxi+b) ≥ 1 for all i), then formulate the Lagrangian L(w, b, α) using Lagrange multipliers αi ≥ 0. Derive the two stationarity conditions from ∂L/∂w = 0 and ∂L/∂b = 0, and briefly state what these conditions tell you about how the optimal w is built from the training data. **[3 Marks]**

### Concept: KKT Complementary Slackness --- Identifying Support Vectors & Functional Margin

**Question (NSP4-S2-25 Exam Q4(c) --- 2 Marks)**

The optimizer has already assigned Lagrange multipliers to four inspection chips (no need to solve for these - they are given): αA = 0, αB = 2.5, αC = 0, αD = 1.8. Using the KKT complementary-slackness condition αi[yi(wᵗxi+b) - 1] = 0, identify which chips are support vectors. For the chips that are NOT support vectors, what must be true about their functional margin yi(wᵗxi+b)? **[2 Marks]**

---

## 10. Decision Trees

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

(c) Briefly explain how the stopping conditions influence model complexity and generalization. **[1 Mark]**

---

## 11. Algorithmic Fairness / Bias

### Concept: Algorithmic Bias --- Bias Originating from Training Data

**Question (NSP4-S2-25 Exam Q5(a) --- 1 Mark)**

A bank builds a loan-approval ML model. To ensure fairness, the data science team removes gender and race/ethnicity entirely before training. An external auditor later reviews a sample of the model's decisions:

| Applicant | Zip Code | Language Preference | Loan Approved? |
|---|---|---|---|
| A | 90210 | English | Yes |
| B | 60623 | Spanish | No |
| C | 90210 | English | Yes |
| D | 60623 | Spanish | No |

The auditor finds that Zip Code and Language Preference are among the model's most heavily weighted features, and that approval outcomes split almost perfectly along these two features.

Even though the developers had no intention to discriminate, explain how algorithmic bias can still enter a model like this - referencing where bias typically originates in the training data. **[1 Mark]**

### Concept: Fairness Through Unawareness --- Proxy Variables & Indirect Discrimination

**Question (NSP4-S2-25 Exam Q5(b) --- 2 Marks)**

The bank's specific fix - removing race/gender directly from the inputs ("Fairness Through Unawareness") - appears to satisfy fairness on the surface. Using the auditor's finding as evidence, explain why this approach still failed, name the phenomenon it illustrates, and state one general reason this kind of fix is hard to guarantee in real-world data. **[2 Marks]**
