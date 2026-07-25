# ML (Machine Learning) - Comprehensive/End-Semester Exam Questions Categorized by Topic

**Papers Covered:**
- 2023-24 End-Semester Regular (EC3R, 40% weightage)
- 2023-24 End-Semester Makeup (EC3M, 40% weightage)
- ML Comprehensive Regular AK (40 marks)
- ML Comprehensive Makeup AK (40 marks)
- ML Comprehensive Sample QP
- Sample QP - EC3
- Sample Question Papers for Students (2 versions)

---

## 1. Bayesian Learning / Naive Bayes Classification

### Q1 [2023-24 EC3 Regular, 4M]
In a specific population, the probability of experiencing a symptom given Meningitis is 80%, without Meningitis is 10%. Prevalence of Meningitis is 5%. Find the probability that a person displaying the symptom indeed has Meningitis. (Apply Bayes' Theorem)

### Q2 [2023-24 EC3 Makeup, 5M]
Consider dataset for text classification with 3 training instances (+/-):
- "Hindi India India" -> +
- "India Kannada Hindi" -> +
- "Chinese Hindi India" -> -

Find classification for "Chinese Kannada Chinese" using Multinomial NB text classification approach. Show all intermediate calculations.

### Q3 [Comprehensive Regular, 5M]
Consider the following Iris flower dataset with features Sepal Length, Sepal Width, Petal Width:
Apply Gaussian Naive Bayes to classify a new instance (Sepal Length=5.0, Sepal Width=3.0, Petal Width=1.5). Show all calculations of prior and posterior probabilities.

### Q4 [Comprehensive Makeup, 5M]
Given a dataset with symptoms and disease outcomes, apply Naive Bayes classification to predict whether a patient has the disease. Show calculations for prior probabilities, likelihoods, and posterior probabilities.

---

## 2. Support Vector Machines (SVM)

### Q1 [2023-24 EC3 Makeup, 4M]
Given training dataset with X1, X2 features and Y (Positive/Negative):
(3,2,+), (5,3,+), (-2,-2,-), (4,4,+), (3,-1,+), (1,0,-), (-1,-1,-), (0,2,-), (1,4,-), (-1,2,-), (4,5,+)
A. Find the support vectors.
B. Determine the equation of hyperplane.

### Q2 [Comprehensive Regular, 5M]
Given training data points, find the maximum margin hyperplane using SVM. Identify support vectors and compute the margin width. Show all steps including Lagrange multiplier formulation.

### Q3 [Sample QP EC3]
Consider the XOR problem. Explain why a linear SVM cannot solve it. Propose a kernel function that would make this problem linearly separable in the transformed feature space. Demonstrate with calculations.

---

## 3. Instance-Based Learning (KNN & Locally Weighted Regression)

### Q1 [2023-24 EC3 Regular, 6M]
Committee of experts data with Readership Base, Writer's Reputation, Distinctive in Style.
Test Instance: <High, High, High>
a) Use 6-NN, 3-NN & 1-NN separately to classify. Use categorical similarity measure.
b) Which k-NN is more robust to outliers? Justify.
c) Create ensemble using majority voting.

### Q2 [2023-24 EC3 Makeup, 3+5=8M]
Glasgow Coma Scale data (Eye Opening, Verbal Responses, Motor Responses).
Query: <5, 5, 5>
i) Predict risk factor using 3-NN model (Manhattan distance).
ii) Apply locally weighted regression with 2-NN kernel K(d)=(-1)/d(xq,xi). Given initial model: Risk = 10 - 0.1*Verbal - 0.1*Motor. Apply gradient descent for one iteration (lr=0.1). Predict risk factor.

### Q3 [Comprehensive Regular, 8M]
Consider a regression problem. Given training data and query point:
a) Apply 3-NN regression to estimate the target value.
b) Apply distance-weighted KNN where weights are inversely proportional to distance.
c) Compare the two approaches and discuss which is more suitable.

### Q4 [Comprehensive Makeup, 6M]
Given patient data with multiple symptoms and risk scores:
a) Use KNN with k=3 to predict the risk category for a new patient.
b) Apply locally weighted regression. Use kernel function K(d) = exp(-d^2). Perform one iteration of gradient descent.

---

## 4. Ensemble Learning (AdaBoost, Random Forest, Bagging)

### Q1 [2023-24 EC3 Makeup, 3M]
In a single iteration of AdaBoost on three sample points with uniform weights:
a) Find the updated weight (before normalization) of X1 instance.
b) Identify which instances were misclassified. Justify.

### Q2 [2023-24 EC3 Makeup, 2M]
Random Forest incorporates feature randomness. Clarify the rationale behind introducing feature randomness in Random Forest.

### Q3 [Comprehensive Regular, 7M]
Consider a binary classification problem:
a) Using AdaBoost with decision stumps, perform 2 iterations showing:
   - Calculation of error rate
   - Amount of say (alpha)
   - Updated sample weights
b) Compute the final ensemble prediction for a given test point.

### Q4 [Comprehensive Makeup, 5M]
Given a dataset:
a) Build 3 decision stumps (weak learners) for AdaBoost.
b) Compute alpha values for each.
c) Show how the final strong classifier makes predictions.

---

## 5. Unsupervised Learning (Clustering - K-Means, K-Modes, GMM)

### Q1 [2023-24 EC3 Makeup, 4+1+2=7M]
K-modes clustering on Glasgow Coma Scale data (categorical). 3 clusters, one iteration.
a) Show step-by-step E-step and M-step using given distance metric.
b) Calculate new centroids.
c) True/False: "If clusters = data points, algorithm converges in at most one EM iteration." Justify.

### Q2 [2023-24 EC3 Regular, 4.5+1.5+2=8M]
Apply Gaussian Mixture Model (GMM) soft clustering for one iteration on literary works data (Readership Base, Number of Translations). 2 clusters with given initial means, SDs, weights.
a) Show all computations. Show final responsibility matrix.
b) Find new mixture weights and cluster means.
c) Give example from healthcare domain where soft clustering is better than hard clustering.

### Q3 [Comprehensive Regular, 8M]
Apply K-Means clustering on given 2D data points. Initial centroids provided.
a) Perform 2 complete iterations showing cluster assignments and centroid updates.
b) Calculate Within-Cluster Sum of Squares (WCSS) after final iteration.
c) Discuss convergence criteria.

### Q4 [Comprehensive Makeup, 6M]
Apply hierarchical clustering (agglomerative) on given data:
a) Show the dendrogram construction step by step using single linkage.
b) If we cut at a threshold to get 3 clusters, what are the clusters?
c) Compare with K-Means on the same data.

---

## 6. Logistic Regression

### Q1 [2023-24 EC3 Makeup, 5M]
Logistic regression for spam detection. Coefficient=0.03, Intercept=-1.2.
Calculate predicted probability for email with subject line length=50 characters. Classify with threshold=70%. Justify the class assignment.

### Q2 [Comprehensive Regular, 5M]
Given a logistic regression model with coefficients, compute:
a) The decision boundary equation.
b) Predicted probabilities for given test points.
c) Classify each test point using threshold=0.5.
d) Compute the log-loss for the predictions.

### Q3 [Sample QP]
Derive the gradient descent update rule for logistic regression. Show how the cost function (binary cross-entropy) is minimized. Perform one iteration of gradient descent for given data.

---

## 7. Linear & Polynomial Regression

### Q1 [2023-24 EC3 Regular, 3M]
Find the best curve of the form y = a + bx + cx^2 minimizing square error that fits: (-1,0), (1,10), (2,24), (-2,4).

### Q2 [Comprehensive Regular, 7M]
Given dataset (height vs weight):
a) Fit a simple linear regression model using least squares.
b) Calculate R-squared value.
c) Predict weight for a given height.
d) Analyze residuals and comment on model adequacy.

### Q3 [Comprehensive Makeup, 5M]
Multiple linear regression with 3 features:
a) Set up the normal equations.
b) Compute the regression coefficients.
c) Make a prediction for a new data point.

---

## 8. Decision Trees & Information Gain

### Q1 [2023-24 EC3 Makeup, 1.5M]
What are the shortcomings of using Entropy (Information Gain) as a heuristic measure while building decision trees?

### Q2 [2023-24 EC3 Regular, 1+1M]
How can Decision Tree models aid in enhancing Interpretability of ML systems? What are their limitations?

### Q3 [Comprehensive Regular, 8M]
Build a decision tree for the given dataset:
a) Calculate information gain for each attribute at root.
b) Show the tree construction process with splits.
c) Classify a new test instance using the constructed tree.
d) Discuss pre-pruning vs post-pruning strategies.

### Q4 [Sample QP]
Given a dataset with categorical and numerical features:
a) Compute Gini index for each possible split.
b) Select the best split at each node.
c) Build the tree to maximum depth of 3.

---

## 9. Model Evaluation & Comparison

### Q1 [2023-24 EC3 Regular, 5M]
Spam filter scenario (spam = positive class):
1) Describe Precision and Recall with respect to the problem.
2) Explain what happens if you optimize each parameter.
3) Which would be more important to optimize and why?

### Q2 [2023-24 EC3 Makeup, 2.5M]
Learning curve shows high error on test data. Comment on performance. Discuss strategies to address (high bias scenario).

### Q3 [2023-24 EC3 Makeup, 0.5M]
Which chart of RSS vs model complexity represents training phase for a fixed dataset? Justify.

### Q4 [2023-24 EC3 Regular, 2M]
Two learning curves with different learning rates. For which case is learning rate too large? Justify.

### Q5 [Comprehensive Regular, 5M]
Given confusion matrix for a multi-class classification problem:
a) Calculate accuracy, precision, recall, F1-score for each class.
b) Calculate macro-averaged and micro-averaged F1.
c) Discuss when micro vs macro averaging is more appropriate.

### Q6 [Comprehensive Makeup, 4M]
Compare and contrast:
a) K-fold cross validation vs Leave-One-Out cross validation.
b) Stratified sampling vs Random sampling for train-test split.
c) When would you prefer one over the other?

---

## 10. Bias-Variance Tradeoff & Regularization

### Q1 [Sample QP - Students, multi-part]
- Discuss bias-variance tradeoff with examples.
- How does model complexity affect bias and variance?
- Explain L1 vs L2 regularization and their effects on model parameters.
- What is the role of regularization parameter lambda?

### Q2 [Comprehensive Regular, 4M]
Given training and validation error curves:
a) Identify if the model suffers from high bias or high variance.
b) Suggest remedies for each case.
c) How does adding more training data help in each case?

---

## 11. Gradient Descent & Optimization

### Q1 [Sample QP - Students]
- Derive gradient descent update rule for linear regression.
- Show effect of learning rate (too large, too small, optimal).
- Perform calculations for first iteration with given data.

### Q2 [Comprehensive Makeup, 5M]
Compare Batch Gradient Descent, Stochastic Gradient Descent, and Mini-Batch Gradient Descent:
a) Mathematical formulation of each.
b) Convergence properties.
c) When to use each approach.

---

## 12. Interpretability & Ethics in ML

### Q1 [2023-24 EC3 Makeup, 2M]
Illustrate a situation where lack of interpretability in a model could result in ethical issues. Explain how interpretability could mitigate these concerns.

---

## 13. Feature Engineering & Preprocessing

### Q1 [Sample QP - Students]
- Discuss feature scaling: Standardization vs Normalization.
- When is each appropriate?
- Impact on distance-based algorithms.

### Q2 [Sample QP - Students]
- Discuss handling missing values: imputation strategies.
- Feature selection methods: Filter, Wrapper, Embedded.
- Dimensionality reduction techniques.

---

## 14. Hyperparameters in ML

### Q1 [Sample QP - Students]
Discuss various hyperparameters used in regression models:
- Learning Rate
- Regularization parameters
- Number of Trees (tree-based methods)
- Maximum Depth
- Number of Neighbors (KNN)
- Kernel Type (SVM)
- Batch Size (SGD)

---
