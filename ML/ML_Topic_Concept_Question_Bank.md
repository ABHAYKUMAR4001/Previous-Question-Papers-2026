# Machine Learning Question Bank — Topic → Concept → Exact Question

> **Purpose:** Organize every question by **Topic → Concept → Exact Question**. As more papers/files are added, questions should be inserted under the closest existing concept. Create a new concept/topic only when necessary.
>
> **Professor coverage classifier:** Based only on the uploaded lecture transcripts of Prof. Neha Vinayak. `✅ Covered` means the topic/concept is explicitly taught or discussed in the transcripts. `⚠️ Not found explicitly` means that exact concept was not found in the uploaded transcripts; it does **not** mean it is outside the syllabus.
>
> **Sources currently included:**
> 1. Sample Paper — Comprehensive Examination (EC-3 Make-up), AIMLCZG565/DSECLZG565.
> 2. NSP4-S2-25_EC3R_AIMLCZG565 — Machine Learning Question Paper.
> 3. First Semester 2023–2024 End-Semester Test (EC-3 Regular), DSE ZG565 / AIML ZG565 — uploaded image set.
> 4. First/Second Semester 2024–2025 Comprehensive Examination (EC-3 Regular), AIMLZC565/DSECLZC565 — uploaded image set.

## Professor Lecture Coverage — Quick Classifier

| Topic / Concept appearing in this question bank | Professor coverage |
|---|---|
| Ridge Regression — regularization strength, bias–variance, coefficient shrinkage | ⚠️ Not found explicitly as **Ridge Regression** |
| Polynomial Regression / least-squares curve fitting | ✅ Covered |
| Linear Regression and its use/limitations | ✅ Covered |
| Logistic Regression | ✅ Covered |
| L2-regularized Logistic Regression | ⚠️ Logistic Regression and regularization are covered, but this exact combined formulation was not clearly found |
| Gradient Descent / learning rate / convergence | ✅ Covered |
| Bayes' theorem / posterior probability | ✅ Covered |
| Gaussian Naive Bayes | ✅ Covered |
| Multinomial Naive Bayes | ✅ Covered |
| Laplace smoothing | ✅ Covered |
| Generative vs discriminative models — NB vs Logistic Regression | ⚠️ Not found explicitly in this wording |
| Naive Bayes conditional-independence assumption | ✅ Covered |
| KNN classification/regression | ✅ Covered |
| Min-max normalization / distance calculations for KNN | ✅ Covered |
| Locally Weighted Linear Regression / local regression | ✅ Covered |
| Manhattan / Minkowski / Euclidean distance | ✅ Covered |
| Distance-weighted KNN / weighted neighbours | ✅ Covered |
| Gower distance for mixed attributes | ✅ Covered |
| Effect of K / robustness to neighbours and outliers | ✅ Covered |
| Bagging | ✅ Covered |
| Random Forest / feature subsampling | ✅ Covered |
| AdaBoost — weak learners, errors, learner weights, sample reweighting | ✅ Covered |
| Gradient Boosting | ✅ Covered |
| Majority voting / ensemble combination | ✅ Covered |
| GMM / Gaussian Mixture Models | ✅ Covered |
| EM algorithm — E-step, responsibilities, M-step | ✅ Covered |
| GMM vs K-Means / soft vs hard clustering | ✅ Covered |
| K-Means — assignment and centroid update | ✅ Covered |
| K-Means initialization / limitations | ✅ Covered |
| SVM / maximum-margin classifier / support vectors | ✅ Covered |
| Hard-margin SVM primal and Lagrangian | ✅ Covered |
| SVM dual / Lagrange multipliers | ✅ Covered |
| KKT / complementary slackness | ✅ Covered |
| Kernel SVM / kernel trick | ✅ Covered |
| SVM C / soft margin / kernel hyperparameters | ✅ Covered |
| Decision Trees | ✅ Covered |
| Decision-tree overfitting / stopping / depth | ✅ Covered |
| Decision-tree interpretability | ✅ Covered |
| Precision–Recall / classification metric question as written | ⚠️ Not found explicitly enough in the uploaded transcripts to mark this exact concept covered |
| Algorithmic bias / fairness / interpretability | ✅ Covered at a general level |
| Fairness through unawareness / proxy variables | ⚠️ Not found explicitly |

> **Important:** The classifier is intentionally conservative. If the professor discussed a broad topic but the exact exam-question concept was not explicit in the transcript, it is marked `⚠️` rather than assumed covered.

---

## 1. Linear Regression / Regularization

### Concept: Ridge Regression — Regularization Strength, Bias–Variance & Coefficient Shrinkage

**Question (Sample Paper Q1 — 4 Marks)**

A data science team is building a linear regression model to predict house prices using 120 correlated features. The team applies Ridge Regression and experiments with λ = 0, λ = 0.01 and λ = 10⁴.

(a) For each case, describe coefficient behavior and bias–variance tradeoff. **[3]**
(b) Explain why Ridge does not perform feature selection even for very large λ. **[1]**

### Concept: Polynomial Regression — Least-Squares Curve Fitting / Normal Equations

**Question (2023–24 End-Sem Regular Q3(b) — 3 Marks)**

Find the best curve **y = a + bx + cx²** minimizing squared error for (-1,0), (1,10), (2,24), (-2,4). **[3]**

### Concept: Linear Regression for Classification — Unbounded Predictions & Thresholding

**Question (2024–25 EC3 Regular Q7(a) — 1 Mark)**

A fintech company predicts loan default using normalized income x1 and debt ratio x2. Model A is Linear Regression used with a threshold to classify. During evaluation it sometimes outputs values outside [0,1]. Explain why Model A can produce predictions outside [0,1] while Models B/C cannot, even though all are trained on the same inputs. **[1]**

---

## 2. Logistic Regression

### Concept: L2-Regularized Logistic Regression — Cross-Entropy, Gradient Descent & Weight Shrinkage

**Question (NSP4-S2-25 Exam Q2 — 4 Marks)**

A streaming service predicts cancellation using normalized Watch Hours and Complaints. Initial weights w0=0,w1=-1,w2=1, α=0.5, λ=0.4. (a) Write L2-regularized cross-entropy and explain gradient difference. **[1]** (b) Compute sigmoid outputs and one regularized GD update. **[2]** (c) Compare w1 magnitude with λ=0 and interpret. **[1]**

### Concept: Gradient Descent — Learning Rate Too Large, Cost Divergence & Learning Curves

**Question (2023–24 End-Sem Regular Q3(a) — 2 Marks)**

Two logistic-regression learning curves are shown: A decreases/converges; B increases/diverges. Which learning rate is possibly too large? Justify. **[2]**

---

## 3. Naive Bayes / Bayesian Learning

### Concept: Bayes' Theorem — Posterior Probability & Law of Total Probability

**Question (2023–24 End-Sem Regular Q1 — 4 Marks)**

P(Symptom|Meningitis)=0.8, P(Symptom|no Meningitis)=0.1, prevalence=0.05. Find P(Meningitis|Symptom). **[4]**

### Concept: Gaussian Naive Bayes — Mixed Continuous & Categorical Features

**Question (Sample Paper Q2 — 5 Marks)**

Using student study-hours, gender and Pass/Fail data, classify test case {Study hours=3.5, Gender=Male} using Naive Bayes. **[5]**

### Concept: Multinomial Naive Bayes — Laplace Smoothing & Posterior Classification

**Question (NSP4-S2-25 Exam Q6(a,b) — 3 Marks)**

Movie-review Multinomial NB with word counts for great, boring, acting, slow, brilliant; priors Positive=0.6, Negative=0.4. Test: “acting was slow but great.” (a) Laplace-smoothed likelihoods. **[1.5]** (b) Posterior scores and class. **[1.5]**

### Concept: Generative vs Discriminative Models — Naive Bayes vs Logistic Regression

**Question (NSP4-S2-25 Exam Q6(c) — 1 Mark)**

Explain generative P(Y),P(X|Y) vs discriminative P(Y|X), and why NB and Logistic Regression may differ despite shared form. **[1]**

### Concept: Conditional Independence Assumption — Correlated Features & Overconfident Posteriors

**Question (NSP4-S2-25 Exam Q6(d) — 1 Mark)**

Explain how correlated words violate NB independence, cause overconfident posteriors, and why Logistic Regression may handle them better. **[1]**

### Concept: Multinomial Naive Bayes — Laplace Smoothing, Priors, Likelihoods & Posterior Classification

**Question (2024–25 EC3 Regular Q4 — 6 Marks)**

A customer-support analytics team classifies emails into **Complaint (C)** and **Inquiry (I)** using a bag-of-words Multinomial Naive Bayes model. Vocabulary V={delay, refund, order, price}. Training statistics: C has 5 emails, I has 5 emails; total word counts C=17, I=15; counts for (delay,refund,order,price) are C=(6,5,2,1), I=(1,1,6,7). A new email contains **“delay refund refund”**.

(a) Compute priors for C and I. **[1]**
(b) With Laplace smoothing α=1, compute conditional probabilities for delay and refund under both classes. **[2]**
(c) Compute unnormalized posterior probabilities and predicted class. **[2]**
(d) Give one advantage of Laplace smoothing. **[1]**

---

## 4. K-Nearest Neighbours (KNN) / Local Regression

### Concept: KNN Regression — Min-Max Normalization & Euclidean Distance
### Concept: Locally Weighted Linear Regression — Gaussian Kernel & One GD Update

**Question (Sample Paper Q3 — 6 Marks)**

For query Q=(7 cm,18 months), use normalized Size/Warranty to obtain a 4-NN regression estimate and locally weighted linear-regression estimate with Gaussian kernel and one GD update. **[6]**

### Concept: KNN Classification — Manhattan Distance & Unweighted Voting
### Concept: Distance-Weighted KNN — Inverse-Distance Voting
### Concept: Feature-Weighted Distance Metric — Effect on Neighbourhood & Classification

**Question (NSP4-S2-25 Exam Q7 — 7 Marks)**

For labelled machine points and query xq=(5,5), compute Manhattan-distance 5-NN, weighted 5-NN with wi=1/d, compare them, then analyze effect of metric d'=|Δx1|+2|Δx2|. **[7]**

### Concept: KNN with Categorical Features — Matching-Attribute Similarity
### Concept: Effect of K / Robustness to Outliers
### Concept: Ensemble of KNN Models — Majority Voting Across Different K

**Question (2023–24 End-Sem Regular Q4(a–c) — 6 Marks)**

For a categorical literary-work dataset and test instance <High,High,High>, use 6-NN, 3-NN and 1-NN with similarity = matching attributes / total attributes; identify which K is more robust to outliers; then ensemble the three predictions by majority voting. **[6]**

### Concept: Distance-Weighted KNN — Mixed Numeric/Nominal/Ordinal Attributes, Normalization & Feature Weights

**Question (2024–25 EC3 Regular Q2 — 6 Marks)**

A fintech company classifies customer risk R1/R2 using distance-weighted KNN. Historical customers:

| Customer | Risk | d_age | d_spend | d_emp | d_city | Gower d | Weight 1/(d²) |
|---|---|---:|---:|---:|---:|---:|---:|
| A0 | R1 | 0.0909 | 0.0577 | 0 | 0 | 0.03715 | 724.56 |
| A1 | R2 | 0.4545 | 0.0192 | 0.5 | 0.5 | 0.36842 | 7.36 |
| A2 | R1 | 0.1364 | 0.0192 | 0 | 0 | 0.03890 | 11.98 |
| A3 | R2 | 0.5909 | 0.5577 | 1 | 0.5 | 0.66215 | 2.28 |
| A4 | R2 | 0.8182 | 0.9423 | 1 | 1 | 0.94012 | 1.13 |

The query customer is Age=32, Monthly Spend=₹41,000, Employment=Self-Employed, City Tier=Tier-3. K=3 and all attributes are equally important.

(a) Identify an appropriate distance measure and compute the distance-weighted class scores for R1 and R2; determine the predicted class. **[3]**
(b) Why does R1 win despite fewer samples? **[1]**
(c) Recompute distance and weighted class scores assuming City Tier is nominal rather than ordinal; does prediction change? **[2]**

---

## 5. Ensemble Learning

### Concept: Bagging vs AdaBoost — Sources of Learner Diversity
### Concept: Random Forest — Feature Subsampling & Tree Correlation
### Concept: Majority Voting — Ensemble Accuracy

**Question (Sample Paper Q4 — 6 Marks)**

Compare Bagging, Random Forest and AdaBoost diversity; explain Random Forest feature randomness; compute majority-vote accuracy for three independent classifiers each 70% accurate. **[6]**

### Concept: Ensemble vs Linear Model — Accuracy, Influential Features, Correlation & Explainability Trade-off

**Question (2024–25 EC3 Regular Q1 — 3 Marks)**

You are the Lead ML Engineer for a global bank building a regression model to predict **Annual Default Risk**. Dataset size=60,000; 50 correlated numeric/categorical features; domain experts say only 10–15 are truly influential; model must be correct and explainable; any single-feature prediction must be explainable. A standardized linear model gives RMSE=0.0841; a complex Ensemble Regressor (Random Forest/Gradient Boosting) gives RMSE=0.0632.

(a) Which model is most appropriate given data size and domain constraints? Justify. **[1]**
(b) Explain two specific disadvantages of deploying the Ensemble Regressor in this regulatory setting. **[2]**

### Concept: AdaBoost — Weighted Error, Learner Weight & Sample-Weight Update
### Concept: AdaBoost — Final Weighted Ensemble Prediction

**Question (NSP4-S2-25 Exam Q3 — 6 Marks)**

Given sample weights/classes/weak-learner predictions, compute weighted error, learner α, updated normalized weights, final weighted prediction, and discuss a weak learner with error 0.55. **[6]**

### Concept: AdaBoost Decision Stump — Threshold Selection, Learner Importance & Instance-Weight Update

**Question (2023–24 End-Sem Regular Q5 — 5 Marks)**

For six 1D points with classes (+,+,-,-,+,+), choose a decision-stump threshold c such that only x=1,2 are misclassified; find classifier importance and updated instance weights. **[5]**

### Concept: AdaBoost — Misclassified Samples, Weighted Error, Learner Weight & Sequential Reweighting

**Question (2024–25 EC3 Regular Q3 — 8 Marks)**

An AdaBoost classifier is at iteration 3 with four samples. Current weights are **(0.10, 0.30, 0.15, 0.45)**, true labels **(+1,+1,-1,-1)** and weak learner h3 predictions **(+1,-1,-1,-1)**.

(a) Identify samples misclassified by h3. **[0.5]**
(b) Compute weighted error ε3. **[0.5]**
(c) Compute learner weight α3 = ½ ln((1-ε3)/ε3). **[1]**
(d) Compute updated sample weights and normalize them. **[2]**
(e) Explain why the highest-weight sample has the highest weight in terms of previous weak learners. **[2.5]**
(f) State one advantage and one disadvantage of AdaBoost compared with a single decision tree. **[1.5]**

---

## 6. Gaussian Mixture Models (GMM) / EM

### Concept: EM Algorithm — E-Step Responsibilities, Log-Likelihood & M-Step
### Concept: GMM vs K-Means — Soft vs Hard Assignment

**Question (Sample Paper Q5 — 6 Marks)**

For X={-4,-2,0,3}, fit a two-component GMM with given initial π, μ and σ²; compute responsibilities, log-likelihood, M-step updates, then compare with one K-Means iteration. **[6]**

### Concept: Gaussian Mixture Model — One EM Iteration with Multivariate Features
### Concept: Responsibility Matrix — Soft Cluster Membership
### Concept: M-Step — Updated Mixture Weights & Cluster Means
### Concept: Soft Clustering — Appropriate Application Scenario

**Question (2023–24 End-Sem Regular Q4 — 8 Marks; GMM variant)**

Cluster three literary works using Readership Base and Number of Translations with a two-component GMM for one iteration; compute responsibility matrix, updated mixture weights/means, and give a healthcare scenario where soft clustering is preferable. **[8]**

### Concept: K-Means vs GMM — Hard Assignment, Soft Responsibilities & Overlapping Clusters

**Question (2024–25 EC3 Regular Q6 — 6 Marks)**

Customer points are **A(1,2), B(2,1), C(2,3), D(6,5), E(7,6), F(8,5)**.

(a) Apply **K-Means for one iteration** using initial centroids at **(1,2)** and **(8,5)**. Show assignments and updated representative points/centroids. **[3]**
(b) Model the same data using a **Gaussian Mixture Model (GMM)** with two components. **[2]**
(c) Explain one key difference between K-Means cluster assignments and GMM responsibilities using a specific point, and state when GMM would produce better clusters than K-Means. **[1]**

---

## 7. K-Means Clustering

### Concept: K-Means — One Iteration, Euclidean Distance, Cluster Assignment & Centroid Update

**Question (NSP4-S2-25 Exam Q1(a) — 3 Marks)**

For delivery locations P(2,3) through W(9,7), use K-Means with C1=(2,3), C2=(9,7). Perform one iteration, show distances, assignments and updated centroids. **[3]**

### Concept: K-Means — Sensitivity to Initial Centroids

**Question (NSP4-S2-25 Exam Q1(b) — 2 Marks)**

Reason whether nearby initial centroids C1'=(4,5), C2'=(5,5) are likely to produce good final clustering and explain sensitivity to initialization. **[2]**

### Concept: K-Means — Limitations & Alternative Clustering Approaches

**Question (NSP4-S2-25 Exam Q1(c) — 2 Marks)**

Describe one scenario where K-Means fails (different sizes/densities, non-globular shapes, outliers) and name a better alternative. **[2]**

### Concept: K-Means — One Iteration & Comparison with GMM

**Question (2024–25 EC3 Regular Q6(a,c) — part of 6 Marks)**

Using A(1,2), B(2,1), C(2,3), D(6,5), E(7,6), F(8,5), perform one K-Means iteration from centroids (1,2) and (8,5), then compare hard K-Means assignments with GMM soft responsibilities. **[part of Q6]**

---

## 8. Gradient Boosting

### Concept: Gradient Boosting Regression — Initial Prediction, Pseudo-Residuals, Leaf Predictions & Learning-Rate Update

**Question (Sample Paper Q6 — 3 Marks)**

With squared loss, compute F0=mean(y), pseudo-residuals, first-tree leaf predictions and updated prediction after one boosting iteration. **[3]**

---

## 9. Support Vector Machines (SVM)

### Concept: Maximum-Margin Hyperplane — Geometric Construction, Canonical Margin & Support Vectors
### Concept: Dual Formulation — Lagrange Multipliers
### Concept: Margin Width & Robustness
### Concept: Kernelized SVM — Computational Cost

**Question (Sample Paper Q7 — 8 Marks)**

Given four 2D points and specified support vectors P2/P3, geometrically find the maximum-margin hyperplane, compute canonical w,b, identify dual support-vector condition, compute margin width and discuss kernel cost. **[8]**

### Concept: SVM Hyperparameters — C, Gamma, Overfitting & Linear Boundary Suitability

**Question (NSP4-S2-25 Exam Q4(a) — 3 Marks)**

Compare Linear SVM C=0.5 (91% train,89% test) with polynomial SVM C=100,gamma=20 (100% train,76% test). Identify overfitting and explain C/gamma and boundary suitability. **[3]**

### Concept: Hard-Margin SVM — Primal Formulation, Lagrangian & Stationarity Conditions

**Question (NSP4-S2-25 Exam Q4(b) — 3 Marks)**

Write hard-margin primal, formulate Lagrangian, derive ∂L/∂w=0 and ∂L/∂b=0, and explain optimal w. **[3]**

### Concept: KKT Complementary Slackness — Identifying Support Vectors & Functional Margin

**Question (NSP4-S2-25 Exam Q4(c) — 2 Marks)**

Given αA=0, αB=2.5, αC=0, αD=1.8 and complementary slackness, identify support vectors and state margin condition for non-support vectors. **[2]**

### Concept: SVM Kernel Choice — Linear vs Polynomial, C, Degree, Overfitting & Margin

**Question (2024–25 EC3 Regular Q5 — 8 Marks)**

A bank predicts loan defaults with two SVMs:
- **Model A:** Linear SVM, C=0.1, training accuracy=85%, test accuracy=84%.
- **Model B:** Polynomial-kernel SVM, C=100, degree=6, training accuracy=98%, test accuracy=72%.

(a) Which model is overfitting? Explain what C and degree do and why the chosen values produce the observed behavior. **[2]**
(b) Model A has w=[0.5,-0.3]ᵀ and b=0.2. For x=[2,1]ᵀ compute f(x)=wᵀx+b and determine default (+) or non-default (-). **[2]**
(c) Compute geometric margin of Model A and explain what a larger margin means for confidence/generalization. **[2]**
(d) Why might the bank prefer a soft-margin SVM over hard-margin SVM? **[1]**
(e) Draw/describe an overfitting diagram and explain soft vs hard margin. **[1]**

### Concept: SVM Model Selection — Linear vs Polynomial Boundary Under Small Data

**Question (2024–25 EC3 Regular Q7(b,c) — 2 Marks)**

For loan-default data, Model B is a polynomial SVM with C=10, degree=3, while Model C is a depth-3 decision tree. As training data decreases, which model is most likely to overfit and why, explicitly referring to how each represents its decision boundary? A regulator wants the model whose prediction changes most smoothly for small changes in input values; identify and justify. **[2]**

---

## 10. Decision Trees

### Concept: Overfitting — Tree Depth & Minimum Leaf Size
### Concept: Stopping Conditions — Complexity vs Generalization

**Question (Sample Paper Q8 — 2 Marks)**

Compare unrestricted tree (99% train,71% test) with depth-4/min-25-leaf tree (86% train,83% test); identify overfitting and explain stopping conditions/generalization. **[2]**

### Concept: Decision Trees — Interpretability & Limitations

**Question (2023–24 End-Sem Regular Q2(a) — 2 Marks)**

How can Decision Tree models enhance interpretability of ML systems, and what are their limitations? **[2]**

### Concept: Decision Tree — Piecewise-Constant Boundaries, Abrupt Prediction Changes & Small-Data Behavior

**Question (2024–25 EC3 Regular Q7 — part of 3 Marks)**

Model C is a Decision Tree (maximum depth=3) for loan-default prediction. It shows sudden changes in predicted class for small changes in x2. Compare this behavior with linear-regression and polynomial-SVM models when discussing overfitting and stability under small input changes. **[part of Q7]**

---

## 11. Model Evaluation / Classification Metrics

### Concept: Precision & Recall — Contextual Interpretation
### Concept: Precision–Recall Trade-off — False Positives vs False Negatives
### Concept: Metric Selection — Cost-Sensitive Choice for Spam Filtering

**Question (2023–24 End-Sem Regular Q2(b) — 5 Marks)**

For a spam filter with spam as positive class: define Precision/Recall in context, explain effects of optimizing each, and choose the more important metric with justification. **[5]**

---

## 12. Algorithmic Fairness / Bias

### Concept: Algorithmic Bias — Bias Originating from Training Data

**Question (NSP4-S2-25 Exam Q5(a) — 1 Mark)**

A bank removes gender/race but Zip Code and Language Preference strongly split approvals. Explain how algorithmic bias can still enter. **[1]**

### Concept: Fairness Through Unawareness — Proxy Variables & Indirect Discrimination

**Question (NSP4-S2-25 Exam Q5(b) — 2 Marks)**

Explain why removing protected attributes can fail due to proxies and why fairness-through-unawareness is hard to guarantee. **[2]**
