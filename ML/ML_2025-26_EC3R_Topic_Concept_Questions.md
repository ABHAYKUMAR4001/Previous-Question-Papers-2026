# Machine Learning — 2025–26 EC-3 Regular Paper: Topic → Concept → Question

> Source: First Semester 2025–2026 Comprehensive Examination (EC-3 Regular), Machine Learning, 30 November 2025 — uploaded image set.

## 1. Model Evaluation / Logistic Regression

### Concept: Confusion Matrix — Precision, Recall and F1 Score

**Question (Q1 — 5 Marks)**

A logistic-regression model predicts whether a person becomes a successful movie actor. In a dataset of 300 individuals, the model predicts 120 as successful. Among these predicted positives, 110 are actually successful and 10 are false positives. The remaining 180 are predicted unsuccessful; among them, 179 are true negatives and 1 is a false negative.

(a) Compute **Precision**.  
(b) Compute **Recall**.  
(c) Compute **F1 Score**.  
Use the confusion-matrix structure and draw conclusions from the measures.

---

## 2. K-Nearest Neighbours (KNN)

### Concept: KNN Classification — Euclidean Distance, k=3, Nearest-Neighbour Voting & Feature Scaling

**Question (Q2 — 6 Marks)**

Training samples with two numerical features are:

| Point | x1 | x2 | Class C |
|---|---:|---:|---:|
| A | 1 | 2 | 0 |
| B | 2 | 3 | 0 |
| C | 3 | 3 | 1 |
| D | 6 | 5 | 1 |
| E | 7 | 7 | 1 |

For query point **Q=(4,4)**:

(a) Compute the **Euclidean distance** between Q and all training points.  
(b) Predict Q using **KNN with k=3**.  
(c) If feature x2 is on a much larger scale (for example, measured in hundreds), explain how that affects KNN and what preprocessing should be done.

---

## 3. Naive Bayes / Bayesian Learning

### Concept: Multinomial Naive Bayes — Laplace Smoothing, Priors, Conditional Probabilities & Posterior Classification

**Question (Q3 — 4 Marks)**

A spam filter uses **Multinomial Naive Bayes with Laplace smoothing (α=1)**. The labelled training emails are:

| Email | Text | Class |
|---|---|---|
| E1 | “win cash now” | Spam |
| E2 | “limited time offer cash prize” | Spam |
| E3 | “meeting schedule attached” | Not Spam |
| E4 | “project discussion tomorrow” | Not Spam |
| E5 | “schedule meeting project” | Not Spam |

Assume words are space-separated and use all unique training words as the vocabulary. For a new email **Q = “cash prize now”**:

(a) Compute the prior probabilities.  
(b) Compute the required conditional probabilities using Laplace smoothing.  
(c) Classify Q as Spam or Not Spam and justify using the Multinomial NB posterior/product of priors and likelihoods.

---

## 4. K-Means Clustering

### Concept: K-Means — One Iteration, Euclidean Distance, Assignment & Centroid Update

**Question (Q4 — 7 Marks)**

Consider the points **A(2,10), B(2,5), C(8,4), D(5,8)**. Perform **one iteration of K-Means with K=2** using Euclidean distance. Initial centroids are:

- Cluster 1 centroid C1=(2,10)
- Cluster 2 centroid C2=(5,8)

Compute distances of each point to both centroids, assign the points to clusters, and recompute the centroids after the first iteration.

---

## 5. ML System / Model Deployment Strategy

### Concept: End-to-End ML Strategy — Count-Data Regression, Preprocessing, Feature Engineering, Model Selection, Evaluation & Deployment

**Question (Q5 — 4 Marks)**

A customer wants a predictive model to estimate the **number of tickets (a non-negative integer count)** for a large customer-service dataset with about 100 features. As the data scientist, discuss in detail the strategy to follow before finalising a model for deployment.

The expected strategy spans the complete ML lifecycle: business-problem clarity; data understanding; exploratory analysis; preprocessing; feature engineering; model candidates appropriate to count data; baseline models; train/validation/test split and cross-validation; hyperparameter tuning; suitable evaluation metrics; diagnostics and interpretability; deployment readiness; and post-deployment monitoring/retraining.

---

## 6. Classification / Model Selection

### Concept: Spam Classification — Choosing an Optimal Classifier & Practical Pipeline

**Question (Q6 — 4 Marks)**

You are building a classifier to distinguish between **spam and non-spam emails**. Explain how you would approximate/select the optimal classifier in practice.

The answer should cover creation of a labelled dataset, text preprocessing and representation, comparison of candidate models (e.g. Naive Bayes, Logistic Regression, SVM), train/validation/test evaluation, model selection using suitable metrics such as precision/recall/F1, and final deployment/monitoring considerations.

---

## 7. Ensemble Learning — AdaBoost

### Concept: AdaBoost — One Iteration, Decision Stump, Weighted Error, Learner Weight & Sample-Weight Update

**Question (Q7 — 7 Marks)**

A fintech company predicts whether a person goes for breakfast using the following training data:

| Age | Likes Pizza | Likes Idly | Going for Breakfast |
|---:|---:|---:|---:|
| 23 | 0 | 0 | 0 |
| 31 | 1 | 1 | 1 |
| 35 | 1 | 0 | 1 |
| 35 | 0 | 0 | 0 |
| 42 | 0 | 0 | 0 |
| 43 | 1 | 1 | 1 |
| 45 | 0 | 1 | 0 |
| 46 | 1 | 1 | 1 |
| 46 | 1 | 0 | 0 |
| 51 | 1 | 1 | 1 |

Apply **AdaBoost for one iteration** using a one-level decision tree (decision stump). Start with equal sample weights **1/N = 0.1**. Show the necessary calculations, including selection of the weak learner, weighted error, learner influence/weight, updating weights of misclassified and correctly classified samples, and normalization of the new weights.

---

## Concepts added/reinforced by this paper

- Confusion matrix → Precision, Recall, F1
- KNN Euclidean-distance classification and feature scaling
- Multinomial Naive Bayes with Laplace smoothing
- One-iteration K-Means
- End-to-end model-selection/deployment strategy
- Practical spam-classifier selection
- AdaBoost decision stump, weighted error, learner influence and sample reweighting
