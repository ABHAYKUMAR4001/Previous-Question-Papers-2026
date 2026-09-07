# Machine Learning — 2024–25 Second Semester EC-3 Regular

## Topic → Concept → Exact Question Classification

> Source: uploaded 3-page question-paper image set, Course No. DSECLZG565 / AIMLCZG565, Second Semester 2024–2025, Comprehensive Examination (EC-3 Regular), 40 marks.

## 1. Model Evaluation / Classification Metrics

### Concept: Data Leakage — Normalization Before Train/Test Split

**Question Q1(a) — 1 Mark**

A credit scoring model shows 95% accuracy on test data. However, when deployed, it fails catastrophically. You discover that the data scientist normalized all features using the full dataset's statistics before splitting into train/test sets. Explain why this caused the model to fail in production. **[1]**

### Concept: ROC Curve vs Precision–Recall Curve — Imbalanced Classification

A multiclass medical-image classifier has 10,000 images: Normal 4,000 (40%), Pneumonia 3,000 (30%), COVID-19 2,000 (20%), Lung Cancer 1,000 (10%).

**Question Q1(a)(1) — 1 Mark**

Statement A: In this multiclass problem, you can directly compute a single ROC curve and AUC for the entire model. Determine whether TRUE or FALSE and provide detailed reasoning. **[1]**

**Question Q1(a)(2) — 1 Mark**

Statement B: For Lung Cancer, improving recall may reduce precision due to an increase in false positives. Determine whether TRUE or FALSE and provide detailed reasoning. **[1]**

**Question Q1(a)(3) — 1 Mark**

Statement C: Where beta is 1.2, it is often more appropriate than F0.5 score for Lung Cancer detection, but less appropriate than F2 score. Determine whether TRUE or FALSE and provide detailed reasoning. **[1]**

**Question Q1(a)(4) — 1 Mark**

Statement D: If the classifier achieves 85% accuracy, this indicates excellent performance since it is significantly higher than random guessing (25% for 4 classes). Determine whether TRUE or FALSE and provide detailed reasoning. **[1]**

---

## 2. Naive Bayes / Bayesian Learning

### Concept: Multinomial Naive Bayes — MLE, MAP, Laplace Smoothing & Independence Assumption

You are building a Naive Bayes spam classifier for the two words “credit” and “card.” The training dataset is small (~100 spam emails) and contains no occurrence of “credit” in spam. Domain knowledge suggests both words are strongly associated with spam.

**Question Q2(1) — 1.5 Marks**

Explain how the MLE for theta behaves when the training data is very limited, particularly for the word “credit.” **[1.5]**

**Question Q2(2) — 1.5 Marks**

Why is incorporating prior information via MAP estimation important in this setting? **[1.5]**

**Question Q2(3) — 1.5 Marks**

As the training size increases substantially, describe what happens to the difference between the MLE and MAP estimates. **[1.5]**

**Question Q2(4) — 1.5 Marks**

Why might a uniform prior be inappropriate for such a problem? Explain using your domain knowledge. **[1.5]**

**Question Q2(5) — 2 Marks**

Consider the words “credit” and “card,” which are highly correlated in both spam and non-spam emails. Given P(credit|spam)=0.2, P(card|spam)=0.3 and P(credit,card|spam)=0.03, how much higher would Naive Bayes's assumption make the probability than the true likelihood? **[2]**

---

## 3. Support Vector Machines (SVM)

### Concept: Hard-Margin SVM — Optimal Hyperplane, Canonical w,b & Margin Width

Dataset: A(2,1), B(3,1) with class +1; C(1,2), D(0,2) with class -1. A linear SVM is trained and points A and C are support vectors with corresponding Lagrange multipliers equal to 1.

**Question Q3(1) — 3 Marks**

Derive the equation for the optimal hyperplane. Also calculate margin width. **[3]**

### Concept: SVM Support Vectors — Effect of Moving a Non-Support Vector

**Question Q3(2) — 2 Marks**

If the point B(3,1) changes as a result of its movement to B'(4,0), does the optimal hyperplane change? Provide reasoning. **[2]**

### Concept: Soft-Margin SVM — C Parameter, Hyperplane and Support Set

**Question Q3(3) — 2 Marks**

Does the optimal solution (hyperplane and support set) remain identical to the hard-margin solution for any C>0 in the soft-margin formulation? **[2]**

---

## 4. Gaussian Mixture Models (GMM) / EM

### Concept: GMM vs K-Means — Soft vs Hard Assignment, Cluster Shape & Uncertainty

**Question Q4(a) — 1 Mark**

Why is a direct Maximum Likelihood Estimation (MLE) approach difficult for training a GMM? How is this challenge overcome? Explain with an appropriate ML learning approach. **[1]**

**Question Q4(b) — 1 Mark**

How do GMMs provide a more flexible and probabilistic clustering solution than K-Means? Specifically discuss their core assumptions about cluster shape and data point assignments. **[1]**

### Concept: GMM MLE — Hidden Cluster Assignments and EM Algorithm

**Question Q4(c) — 1 Mark**

A bank employs an ML model to assess loan applications. It is later found that the system systematically rejects applicants from certain minority groups. Which FACT principles are being violated? What steps should the bank take to address this issue? **[1]**

### Concept: GMM Covariance — Soft Assignments, Elliptical Clusters & Expectation-Maximization

**Question Q4(a) continuation — 3 Marks**

Direct MLE for a Gaussian Mixture Model is challenging because cluster assignments are hidden/latent. Explain how EM overcomes this through an E-step and M-step, and how covariance matrices allow clusters with varying sizes and orientations rather than only spherical clusters. **[3]**

---

## 5. Algorithmic Fairness / Responsible ML

### Concept: FACT Principles — Fairness, Accountability, Transparency

**Question Q4(c) — 1 Mark**

A bank employs an ML model to assess loan applications. It is later found that the system systematically rejects applicants from certain minority groups. Which FACT principles are being violated? What steps should the bank take to address this issue? **[1]**

---

## 6. Ensemble Learning

### Concept: Bagging vs Random Forest — Training-Set Diversity and Feature Diversity

**Question Q5(a) — 2 Marks**

In the bagging approach to using an ensemble of classifiers (e.g., random forest), the base classifiers may be stable or unstable. Explain the condition under which the base classifier should be stable or unstable. **[2]**

### Concept: AdaBoost — Weighted Misclassification, Sequential Reweighting & Weak Learners

**Question Q5(b) — 3 Marks**

Assume that in the AdaBoost algorithm, we are initially given a dataset of 6 points with classification labels Y={+1,+1,-1,+1,-1,-1}. A base classifier h1 classifies all points with x<2 as one class and all points with x>2 as the other class. Assume that the first classifier misclassifies only the points with x=1 and x=2. What are the possible values of C1 for the first classifier? Explain why. **[2]**

### Concept: Bias–Variance Trade-off — Bagging Reduces Variance

**Question Q5(c) — 1 Mark**

Does Bagging (Bootstrap Aggregating) primarily reduce bias or variance? Explain briefly why. **[1]**

---

## Main Topics in This Paper

1. Model evaluation: data leakage, ROC/AUC, precision-recall, F-beta and class imbalance.
2. Naive Bayes: MLE vs MAP, priors, zero-frequency/limited-data behavior, conditional independence.
3. SVM: hard-margin hyperplane, margin, support vectors, soft-margin C.
4. GMM/EM: why direct MLE is difficult, EM, soft assignments, covariance and comparison with K-Means.
5. Responsible ML: FACT principles and algorithmic fairness.
6. Ensemble learning: bagging/random forest, AdaBoost and bias-variance.