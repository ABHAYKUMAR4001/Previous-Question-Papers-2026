# Machine Learning Question Bank — Topic → Concept → Exact Question

> **Purpose:** Organize every question by **Topic → Concept → Exact Question**. As more papers/files are added, questions should be inserted under the closest existing concept. Create a new concept/topic only when necessary.
>
> **Sources currently included:**
> 1. Sample Paper — Comprehensive Examination (EC-3 Make-up), AIMLCZG565/DSECLZG565.
> 2. NSP4-S2-25_EC3R_AIMLCZG565 — Machine Learning Question Paper.
> 3. First Semester 2023–2024 End-Semester Test (EC-3 Regular), DSE ZG565 / AIML ZG565 — uploaded image set.

## 1. Linear Regression / Regularization

### Concept: Ridge Regression — Regularization Strength, Bias–Variance & Coefficient Shrinkage

**Question (Sample Paper Q1 — 4 Marks)**

A data science team is building a linear regression model to predict house prices using 120 correlated features (area, number of rooms, locality index, proximity to schools, etc.). The training dataset has 8,000 samples, but the validation error fluctuates significantly across folds. To control overfitting, the team applies Ridge Regression and experiments with λ = 0, λ = 0.01 and λ = 10⁴.

(a) For each case, describe the expected behavior of the model coefficients and the bias–variance tradeoff. **[3 Marks]**

(b) In Case 3, all features still have non-zero coefficients although many are extremely small. Explain why Ridge Regression does not perform feature selection even when λ is very large. **[1 Mark]**

### Concept: Polynomial Regression — Least-Squares Curve Fitting / Normal Equations

**Question (2023–24 End-Sem Regular Q3(b) — 3 Marks)**

What is the best curve of the form **y = a + bx + cx²** in terms of minimizing square error that fits the following training dataset (x,y): **(-1,0), (1,10), (2,24), (-2,4)**? **[3 Marks]**

---

## 2. Logistic Regression

### Concept: L2-Regularized Logistic Regression — Cross-Entropy, Gradient Descent & Weight Shrinkage

**Question (NSP4-S2-25 Exam Q2 — 4 Marks)**

A streaming service wants to predict subscription cancellation (y = 1: cancels, y = 0: stays) using two normalized features: Watch Hours per week (x1) and Customer Complaints (x2), both scaled 0 to 1.

| Customer | Watch Hours x1 | Complaints x2 | Label y |
|---|---:|---:|---:|
| C1 | 0.8 | 0.1 | 0 |
| C2 | 0.2 | 0.9 | 1 |
| C3 | 0.7 | 0.2 | 0 |

Initial weights: w0 = 0, w1 = -1, w2 = 1. Learning rate α = 0.5. Regularization constant λ = 0.4.

(a) Write the L2-regularized cross-entropy cost function for logistic regression, and state how its gradient update rule differs from plain logistic regression GD. **[1 Mark]**

(b) Compute σ(z) for each customer, then perform one step of regularized Gradient Descent to obtain w0*, w1*, w2*. **[2 Marks]**

(c) Compare the magnitude of w1* with plain unregularized (λ = 0) logistic regression GD. What does this tell you about L2 regularization's effect on convergence and weight magnitude? **[1 Mark]**

### Concept: Gradient Descent — Learning Rate Too Large, Cost Divergence & Learning Curves

**Question (2023–24 End-Sem Regular Q3(a) — 2 Marks)**

Suppose you tried logistic regression with **2 distinct values of learning rate** and plotted the learning curve for each case where **J(θ)** represents the cost function. For which of the following cases (A or B) is the learning rate possibly too large? Justify your answer. **[2 Marks]**

- Curve A: J(θ) decreases and converges as the number of iterations increases.
- Curve B: J(θ) increases/diverges as the number of iterations increases.

---

## 3. Naive Bayes / Bayesian Learning

### Concept: Bayes' Theorem — Posterior Probability & Law of Total Probability

**Question (2023–24 End-Sem Regular Q1 — 4 Marks)**

In a specific population, the probability of a person experiencing a particular symptom given they've had Meningitis is **80%**, whereas the chances of experiencing the same symptom without Meningitis is **10%**. If the prevalence of Meningitis in the population is **5%**, what is the probability that a person displaying the symptom indeed has Meningitis? **[4 Marks]**

### Concept: Gaussian Naive Bayes — Mixed Continuous & Categorical Features

**Question (Sample Paper Q2 — 5 Marks)**

Using the following student data, apply Naïve Bayes classification to classify the test case **{No. of study hours = 3.5, Gender = Male}** as Pass or Fail.

| Study hours | Gender | Result |
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

### Concept: Multinomial Naive Bayes — Laplace Smoothing & Posterior Classification

**Question (NSP4-S2-25 Exam Q6(a,b) — 3 Marks)**

A movie-review platform wants to tag reviews as Positive or Negative using a Multinomial Naive Bayes classifier. Word counts are: great (6,1), boring (1,5), acting (4,2), slow (2,4), brilliant (3,0) for Positive and Negative respectively. Total words: Positive = 16, Negative = 12, |V| = 5. Priors: P(Positive)=0.6, P(Negative)=0.4. Test review: **“acting was slow but great.”**

(a) Using Laplace smoothing (k=1), compute P(word|class) for acting, slow and great under both classes. **[1.5 Marks]**

(b) Compute the unnormalized posterior score for both classes and determine the predicted class. **[1.5 Marks]**

### Concept: Generative vs Discriminative Models — Naive Bayes vs Logistic Regression

**Question (NSP4-S2-25 Exam Q6(c) — 1 Mark)**

Naive Bayes models P(Y) and P(X|Y) separately (generative), while Logistic Regression models P(Y|X) directly (discriminative). Briefly explain this distinction and why the two approaches can produce different results despite a shared parametric form. **[1 Mark]**

### Concept: Conditional Independence Assumption — Correlated Features & Overconfident Posteriors

**Question (NSP4-S2-25 Exam Q6(d) — 1 Mark)**

Words like “great” and “brilliant” are likely to co-occur strongly in positive reviews (and “boring”/“slow” in negative ones), violating Naive Bayes' word-independence assumption. Explain how this could make NB posterior scores overconfident and why Logistic Regression might handle correlated words more gracefully. **[1 Mark]**

---

## 4. K-Nearest Neighbours (KNN) / Local Regression

### Concept: KNN Regression — Min-Max Normalization & Euclidean Distance
### Concept: Locally Weighted Linear Regression — Gaussian Kernel & One GD Update

**Question (Sample Paper Q3 — 6 Marks)**

A consumer electronics company wants to predict the scaled-down selling price of a gadget using Size and Warranty. For query Q = (7 cm, 18 months), produce (1) a standard 4-NN regression estimate and (2) a locally weighted linear regression estimate using a Gaussian kernel and one GD update. Apply min-max normalization, Euclidean distances, K(d)=exp(-d²/(2b²)), b=2, initial w=(1.5,0.8,0.4), α=0.1. Training points: P0(4,6,6.0), P1(6,12,7.5), P2(7,24,12.0), P3(8,6,8.0), P4(10,12,9.0), P5(12,24,11.0), P6(5,24,10.5), P7(9,18,10.0).

(a) Compute the standard 4-NN prediction. **[2 Marks]**
(b) Compute K(d), perform one GD update, and report new weights and locally weighted prediction. **[3 Marks]**
(c) State one reason why the predictions differ. **[1 Mark]**

### Concept: KNN Classification — Manhattan Distance & Unweighted Voting
### Concept: Distance-Weighted KNN — Inverse-Distance Voting
### Concept: Feature-Weighted Distance Metric — Effect on Neighbourhood & Classification

**Question (NSP4-S2-25 Exam Q7 — 7 Marks)**

A manufacturing plant has labelled machines with vibration x1 and temperature-deviation x2. M1(5,6,F), M2(4,4,F), M3(7,6,N), M4(8,6,N), M5(9,6,N), M6(2,2,F), M7(10,8,N), M8(1,7,F). Query xq=(5,5).

(a) Why is KNN reasonable compared with decision trees or logistic regression? **[1]**
(b) Compute Manhattan distances and five nearest neighbours. **[1]**
(c) Classify with unweighted 5-NN. **[1]**
(d) Classify with distance-weighted 5-NN, wi=1/d. **[2]**
(e) Compare and state the advantage of weighted KNN. **[1]**
(f) Change metric to d'=|Δx1|+2|Δx2| and analyze whether classification is likely to change. **[1]**

### Concept: KNN with Categorical Features — Matching-Attribute Similarity
### Concept: Effect of K / Robustness to Outliers
### Concept: Ensemble of KNN Models — Majority Voting Across Different K

**Question (2023–24 End-Sem Regular Q4(a–c) — 6 Marks)**

A committee classifies literary works as **High, Medium or Low** chance of nomination using three categorical attributes: Readership Base, Writer's Reputation spread in other countries, and Distinctive in Style. For the given test instance **<Readership Base = High, Writer's Reputation = High, Distinctive in Style = High>**:

(a) Use **6-NN, 3-NN and 1-NN separately** to classify the test instance. Assume all features are categorical and use only the following measure of similarity, rounding proximity values to two decimal places:

**Similarity(data1,data2) = Number of matching categorical attributes / Total number of categorical attributes.** **[3.5 Marks]**

(b) Which of the individual k-NN models is more robust to outliers? Justify your answer in no more than 40 words. **[1.5 Marks]**

(c) Create an ensemble using all the above models with **majority voting** to predict the class for the given test instance. **[1 Mark]**

---

## 5. Ensemble Learning

### Concept: Bagging vs AdaBoost — Sources of Learner Diversity
### Concept: Random Forest — Feature Subsampling & Tree Correlation
### Concept: Majority Voting — Ensemble Accuracy

**Question (Sample Paper Q4 — 6 Marks)**

A telecom company compares Bagging, Random Forest and AdaBoost for churn prediction. (a) Explain how Bagging and AdaBoost create learner diversity, distinguishing data-level randomness from error-driven focus. **[2]** (b) Identify Random Forest's additional randomness and explain why it reduces tree correlation. **[2]** (c) For 3 independent classifiers each with accuracy 0.7, compute majority-vote accuracy and compare with an individual classifier. **[2]**

### Concept: AdaBoost — Weighted Error & Weak-Learner Weight
### Concept: AdaBoost — Sample-Weight Update & Normalization
### Concept: AdaBoost — Final Weighted Ensemble Prediction
### Concept: AdaBoost — Weak Learner with Error > 0.5 & Robustness vs Majority Voting

**Question (NSP4-S2-25 Exam Q3 — 6 Marks)**

A bank develops an AdaBoost fraud classifier. Current weights/classes/predictions: T1(0.1,+1,+1), T2(0.2,+1,-1), T3(0.25,-1,-1), T4(0.15,-1,+1), T5(0.3,+1,+1). Use εt=sum of weights of misclassified points; αt=0.5 ln[(1-εt)/εt]; wi←wi exp(-αt yi ht(xi)), then normalize. For new q: h1 weight 0.6 predicts +1; h2 weight 0.31 predicts -1; h3 weight 0.8 predicts -1.

(a) Identify misclassified transactions, compute εt and αt, interpret sign. **[1.5]**
(b) Update and normalize every transaction weight. **[2]**
(c) Compute final weighted ensemble score and class. **[1]**
(d) If a learner has error 0.55, should it be included? State corrective action and why weighted AdaBoost is more robust than unweighted majority voting. **[1.5]**

### Concept: AdaBoost Decision Stump — Threshold Selection, Learner Importance & Instance-Weight Update

**Question (2023–24 End-Sem Regular Q5 — 5 Marks)**

Assume that in the **AdaBoost algorithm**, we are initially given a dataset of 6 points with classification **(x,y=class): (1,+), (2,+), (3,-), (4,-), (5,+), (6,+)**. The classifier is a decision-tree stump choosing a constant **c** such that all points with **x > c** are labeled one class and all points with **x ≤ c** are labeled the other class. Assume the first classifier (at the end of the first iteration) misclassifies only the points at **x=1 and x=2**.

What are possible values of **c** for the first classifier? Find the **importance of the first classifier**, and values of **instance weights at the end of the first iteration**. **[5 Marks]**

---

## 6. Gaussian Mixture Models (GMM) / EM

### Concept: EM Algorithm — E-Step Responsibilities
### Concept: Log-Likelihood
### Concept: EM Algorithm — M-Step Parameter Updates
### Concept: GMM vs K-Means — Soft vs Hard Assignment

**Question (Sample Paper Q5 — 6 Marks)**

For X={-4,-2,0,3}, fit a two-component GMM with π1=0.6, π2=0.4, μ1=-3, μ2=2, σ1²=σ2²=1. (a) E-step responsibilities. **[2]** (b) Log-likelihood. **[0.5]** (c) M-step updated weights, means and variances. **[2]** (d) One K-Means iteration with centroids -3 and 2 and comparison with GMM means. **[1.5]**

### Concept: Gaussian Mixture Model — One EM Iteration with Multivariate Features
### Concept: Responsibility Matrix — Soft Cluster Membership
### Concept: M-Step — Updated Mixture Weights & Cluster Means
### Concept: Soft Clustering — Appropriate Application Scenario

**Question (2023–24 End-Sem Regular Q4 — 8 Marks; GMM variant in uploaded image set)**

A committee wants to cluster literary works using two features: **Readership Base** and **Number of Translations**.

| Literary Work | Readership Base | Number of Translations |
|---|---:|---:|
| ID:1 | 70 | 5 |
| ID:2 | 30 | 3 |
| ID:3 | 50 | 7 |

Use the features as-is without scaling and round calculations to four decimal places.

(a) Assume the data follows a **Gaussian Distribution**. Apply **Gaussian Mixture Model based soft clustering for one iteration** to cluster the points into two clusters. Initial values (mean vector, standard-deviation vector, weight) are: Cluster 1 = **((20,1),(10,1),0.5)** and Cluster 2 = **((50,7),(10,1),0.5)**. Show step-by-step computations and the final **responsibility matrix** at the end of the first iteration. **[4.5 Marks]**

(b) Find only the **new mixture weights and cluster means** at the end of the first iteration. No need to calculate other prototypes' standard deviations. **[1.5 Marks]**

(c) Give a plagiarism-free example and sample feature design from the domain of **healthcare where soft clustering is best suited than hard clustering**. Justify your choice in no more than 40 words. **[2 Marks]**

---

## 7. K-Means Clustering

### Concept: K-Means — One Iteration, Euclidean Distance, Cluster Assignment & Centroid Update

**Question (NSP4-S2-25 Exam Q1(a) — 3 Marks)**

For delivery locations P(2,3), Q(3,4), R(4,5), S(5,5), T(6,6), U(7,7), V(8,6), W(9,7), use K-Means with C1=(2,3), C2=(9,7). Perform one Euclidean-distance iteration, show distances, assignments and updated centroids. **[3]**

### Concept: K-Means — Sensitivity to Initial Centroids

**Question (NSP4-S2-25 Exam Q1(b) — 2 Marks)**

If initial centroids were C1'=(4,5) and C2'=(5,5), reason without fully recomputing whether this is likely to produce good final clustering and explain K-Means sensitivity to initialization. **[2]**

### Concept: K-Means — Limitations & Alternative Clustering Approaches

**Question (NSP4-S2-25 Exam Q1(c) — 2 Marks)**

Describe one scenario involving differing cluster sizes, densities, non-globular shapes or outliers where K-Means fails, and name a better alternative. **[2]**

---

## 8. Gradient Boosting

### Concept: Gradient Boosting Regression — Initial Prediction & Pseudo-Residuals
### Concept: Regression Tree Leaf Predictions
### Concept: Learning-Rate Update After One Boosting Iteration

**Question (Sample Paper Q6 — 3 Marks)**

A logistics company uses Gradient Boosting Regression with squared loss. Initial F0 is mean(y), pseudo-residual ri=yi-F0(xi), η=0.2. First weak learner partitions by Traffic Level and Distance. (a) Compute F0 and residuals. **[1]** (b) Compute leaf predictions. **[1]** (c) Compute F1 and new residual for J2. **[1]**

---

## 9. Support Vector Machines (SVM)

### Concept: Maximum-Margin Hyperplane — Geometric Construction from Support Vectors
### Concept: Canonical Margin — Computing w and b
### Concept: Dual Formulation — Lagrange Multipliers & Support Vectors
### Concept: Margin Width & Robustness
### Concept: Kernelized SVM — Computational Cost

**Question (Sample Paper Q7 — 8 Marks)**

Training data: P1(1,4,+1), P2(2,3,+1), P3(4,1,-1), P4(5,2,-1), with only P2 and P3 support vectors. (a) Geometrically identify maximum-margin hyperplane. **[2]** (b) Use yi(wᵀxi+b)=1 to compute w,b and f(x). **[2]** (c) State αi condition for support vectors and why only P2/P3 influence classifier. **[1.5]** (d) Compute ||w|| and 2/||w|| and interpret larger margin. **[2]** (e) State why kernelized SVM may be computationally expensive. **[0.5]**

### Concept: SVM Hyperparameters — C, Gamma, Overfitting & Linear Boundary Suitability

**Question (NSP4-S2-25 Exam Q4(a) — 3 Marks)**

Model A: Linear SVM C=0.5, train=91%, test=89%. Model B: polynomial SVM C=100, gamma=20, train=100%, test=76%. Which overfits? Explain C and gamma and suitability of linear boundary. **[3]**

### Concept: Hard-Margin SVM — Primal Formulation, Lagrangian & Stationarity Conditions

**Question (NSP4-S2-25 Exam Q4(b) — 3 Marks)**

Write hard-margin primal min ½||w||² subject to yi(wᵀxi+b)≥1, formulate L(w,b,α), derive stationarity from ∂L/∂w=0 and ∂L/∂b=0, and state how optimal w is built from training data. **[3]**

### Concept: KKT Complementary Slackness — Identifying Support Vectors & Functional Margin

**Question (NSP4-S2-25 Exam Q4(c) — 2 Marks)**

Given αA=0, αB=2.5, αC=0, αD=1.8 and αi[yi(wᵀxi+b)-1]=0, identify support vectors and state what must be true of the functional margin for non-support vectors. **[2]**

---

## 10. Decision Trees

### Concept: Overfitting — Tree Depth & Minimum Leaf Size
### Concept: Stopping Conditions — Complexity vs Generalization

**Question (Sample Paper Q8 — 2 Marks)**

Model A: unrestricted depth, leaf can contain one sample, training accuracy 99%, test 71%. Model B: depth restricted to 4, at least 25 samples per leaf, training 86%, test 83%. (a) Which overfits? **[0.5]** (b) Why does the other perform well? **[0.5]** (c) Explain how stopping conditions affect complexity/generalization. **[1]**

### Concept: Decision Trees — Interpretability & Limitations

**Question (2023–24 End-Sem Regular Q2(a) — 2 Marks)**

**How can Decision Tree models aid in enhancing the Interpretability of Machine Learning Systems, and what are their limitations? [1+1 Marks]**

---

## 11. Model Evaluation / Classification Metrics

### Concept: Precision & Recall — Contextual Interpretation
### Concept: Precision–Recall Trade-off — False Positives vs False Negatives
### Concept: Metric Selection — Cost-Sensitive Choice for Spam Filtering

**Question (2023–24 End-Sem Regular Q2(b) — 5 Marks)**

You are an ML engineer working in a large organization that receives many spam emails. Your boss asks you to build a spam filter to distinguish genuine emails from unwanted spam emails. **Assume spam is the positive class.**

1. Describe **Precision and Recall** with respect to the given problem. **[1 Mark]**
2. Explain what happens if you optimize each of the above parameters. **[2 Marks]**
3. Which would be more important to optimize and why? **[2 Marks]**

---

## 12. Algorithmic Fairness / Bias

### Concept: Algorithmic Bias — Bias Originating from Training Data

**Question (NSP4-S2-25 Exam Q5(a) — 1 Mark)**

A bank removes gender and race/ethnicity before training a loan model, but Zip Code and Language Preference strongly split approvals. Explain how algorithmic bias can still enter the model, referencing where bias originates in training data. **[1]**

### Concept: Fairness Through Unawareness — Proxy Variables & Indirect Discrimination

**Question (NSP4-S2-25 Exam Q5(b) — 2 Marks)**

Explain why removing race/gender directly still failed, name the phenomenon illustrated by Zip Code/Language Preference, and state why such a fix is hard to guarantee in real-world data. **[2]**
