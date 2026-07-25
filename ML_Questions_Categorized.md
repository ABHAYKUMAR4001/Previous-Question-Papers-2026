# ML (Machine Learning) - Comprehensive/End-Semester Exam Questions (Full Verbatim)

**Papers Covered:**
- 2023-24 End-Semester Regular (EC3R, 40% weightage)
- 2023-24 End-Semester Makeup (EC3M, 40% weightage)
- ML Comprehensive Regular AK (40 marks)
- ML Comprehensive Makeup AK (40 marks)
- ML Comprehensive Sample QP
- Sample QP - EC3
- Sample Question Papers for Students

> **Note:** Questions involving diagrams/figures are marked with [DIAGRAM IN ORIGINAL]. Refer to the original PDF for visual content.

---

## 1. Bayesian Learning / Naive Bayes Classification


### Q1 [2023-24 EC3 Regular, Q1 - 4M]

In a specific population, the probability of a person experiencing a particular symptom given they've had a Meningitis is 80%, whereas the chances of experiencing the same symptom without Meningitis is 10%. If the prevalence of Meningitis in the population is 5%, what is the probability that a person displaying the symptom indeed has Meningitis?

Given:
- $P(\text{Symptom} | \text{Disease}) = 80\%$
- $P(\text{Symptom} | \neg\text{Disease}) = 10\%$
- $P(\text{Disease}) = 5\%$

Goal: Find $P(\text{Disease} | \text{Symptom})$

---

### Q2 [2023-24 EC3 Makeup, Q1 - 5M]

Consider the following dataset for text classification where three training instances are given with corresponding classifications into the '+' or '-' category:

| Document | Class |
|----------|-------|
| Hindi India India | + |
| India Kannada Hindi | + |
| Chinese Hindi India | - |

Showing all intermediate calculations, find the appropriate classification for the test instance: "Chinese Kannada Chinese" using the Multinomial NB text classification approach.

---

### Q3 [Comprehensive Regular, Q1 - 5M]

Consider the following Iris flower dataset:

| Sepal Length | Sepal Width | Petal Width | Class |
|-------------|-------------|-------------|-------|
| 5.1 | 3.5 | 0.2 | Setosa |
| 4.9 | 3.0 | 0.2 | Setosa |
| 7.0 | 3.2 | 1.4 | Versicolor |
| 6.4 | 3.2 | 1.5 | Versicolor |
| 6.3 | 3.3 | 2.5 | Virginica |
| 5.8 | 2.7 | 1.9 | Virginica |

Apply Gaussian Naive Bayes to classify a new instance (Sepal Length=5.0, Sepal Width=3.0, Petal Width=1.5). Show all calculations of prior probabilities, likelihoods (using Gaussian PDF), and posterior probabilities.

---

## 2. Support Vector Machines (SVM)

### Q1 [2023-24 EC3 Makeup, Q2 - 4M]

You have been tasked to create a discriminative model using a linear Support Vector Machine method. Consider the below training dataset for training the model, where X1, and X2 are independent features and Y is the target variable.

| X1 | X2 | Y |
|----|----|---|
| 3 | 2 | Positive |
| 5 | 3 | Positive |
| -2 | -2 | Negative |
| 4 | 4 | Positive |
| 3 | -1 | Positive |
| 1 | 0 | Negative |
| -1 | -1 | Negative |
| 0 | 2 | Negative |
| 1 | 4 | Negative |
| -1 | 2 | Negative |
| 4 | 5 | Positive |

Answer the following questions:

A. Find the support vectors [1M]

B. Determine the equation of hyperplane [3M]

---

## 3. Instance-Based Learning (KNN & Locally Weighted Regression)


### Q1 [2023-24 EC3 Makeup, Q3 - 3+5=8M]

Use case: The Glasgow Coma Scale assesses patients according to three aspects of responsiveness: eye-opening, motor, and verbal responses.

| Patient | Eye Opening | Verbal Responses | Motor Responses | Risk Factor |
|---------|-------------|-----------------|-----------------|-------------|
| 1 | 2 | 3 | 2 | 3 |
| 2 | 3 | 4 | 3 | 5 |
| 3 | 4 | 4 | 4 | 7 |
| 4 | 2 | 2 | 3 | 4 |
| 5 | 1 | 1 | 1 | 2 |

**Note:** Wherever applicable use only Manhattan distance & No scaling is required. Round all the calculation to 4 decimal places if any. Use average as the aggregation function for the final estimation wherever required unless specific function is recommended. Show all steps. Calculation error will also be penalized.

**Query Instance:** <Eye Opening = 5, Verbal Responses = 5, Motor Responses = 5>

i) Predict the risk factor using 3-NN model. [3M]

ii) If the initial estimation is proposed as locally weighted regression model instead, use:

$$\text{Patient Risk} = 10 - 0.1 \times X_{\text{VERBAL}} - 0.1 \times X_{\text{MOTOR}}$$

and apply 2-NN with kernel: $K(d(x_q, x_i)) = \frac{-1}{d(x_q, x_i)}$

Apply gradient descent only for one iteration with learning rate = 0.1. Predict the risk factor for the query instance. [5M]

---

### Q2 [2023-24 EC3 Regular, Q4 - 3.5+1.5+1=6M]

Use case: Committee of experts convene every year to nominate literary works to become eligible for the awarded of highest category by assessing the works on multiple parameters.

| Literary Work | Readership Base | Writer's Reputation | Distinctive in Style | Nomination |
|--------------|-----------------|--------------------|--------------------|------------|
| 1 | High | Low | Medium | Medium |
| 2 | Medium | High | High | High |
| 3 | Low | High | Medium | Medium |
| 4 | High | Medium | Low | Low |
| 5 | Medium | Low | High | Medium |
| 6 | Low | Medium | Medium | Low |
| 7 | High | High | High | High |
| 8 | Medium | Medium | Low | Low |
| 9 | Low | Low | Medium | Low |
| 10 | High | Medium | High | Medium |
| 11 | High | High | Medium | High |

**Test Instance:** <Readership Base = High, Writer's Reputation = High, Distinctive in Style = High>

a) Use 6-NN, 3-NN & 1-NN separately to classify the above test instance. Assume all the features are categorical in nature and use only the following measure of similarity for your calculation. Round-off all the proximity values to two decimal places. [3.5M]

$$\text{Similarity}(data_1, data_2) = \frac{\text{Number of matching categorical attributes}}{\text{Total number of categorical attributes}}$$

b) Which of the individual k-NN is more robust to outliers? Justify your answer with plagiarism free explanation in no more than 40 words. [1.5M]

c) Create an ensemble using all the above model with majority voting to predict the class for the given test instance. [1M]

---

## 4. Ensemble Learning (AdaBoost, Random Forest, Bagging)

### Q1 [2023-24 EC3 Makeup, Q5 - 3M]

In a single iteration of AdaBoost on three sample points, we initiate the process with uniform weights assigned to the sample points. The ground truth labels and predictions are binary, taking values of either +1 or −1. The table provided below contains some missing values.

[TABLE IN ORIGINAL - with some missing values for weights and predictions]

Answer the following:

a) Find the updated weight (before normalization) of X1 instance. Note, no need to normalize the values. [1.5M]

b) Identify which instances/data points were misclassified in the first iteration. Justify your answer. [1.5M]

---

### Q2 [2023-24 EC3 Makeup, Q5 continued - 2M]

a) Random Forest is a bagging model that incorporates feature randomness. Clarify the rationale behind introducing feature randomness in Random Forest. [2M]

---

## 5. Unsupervised Learning (Clustering)


### Q1 [2023-24 EC3 Makeup, Q4 - 4+1+2=7M] (K-Modes Clustering)

Use case: The Glasgow Coma Scale. Quantified values of attributes are discretized in below data.

| Patient | Eye Opening | Verbal Responses | Motor Responses |
|---------|-------------|-----------------|-----------------|
| Centroid-1 | Bad | Clear | Weak |
| | Bad | Unclear | Weak |
| Centroid-2 | Good | Others | Weak |
| | Worst | Unclear | Strong |
| | Bad | Unclear | Weak |
| Centroid-3 | Good | Clear | Strong |

a) Use following distance measure to cluster the given patients into three clusters using k-modes clustering algorithm for only one iteration. Show the step by step working of the Expectation and Maximization step. Assume all the features are categorical in nature and use only the following distance metric for your calculation. Round-off all the proximity values to two decimal places. [4M]

$$\text{distance}(data_1, data_2) = 10 \times \left(1 - \frac{\text{Number of matching categorical attributes}}{\text{Total number of categorical attributes}}\right)$$

$$\text{Median of categorical attributes within a cluster} = \begin{cases} \text{Mode of attribute value} & \text{if cluster size is odd} \\ t & \text{otherwise} \end{cases}$$

where $t$ = Least frequent attribute value observed in the entire training data

b) Calculate the new centroids [1M]

c) State if the below given statement is true or false w.r.t given data whose centroids are sampled with replacements. Justify your statement with plagiarism free explanations. [2M]

"If the number of clusters expected is equivalent to the number of data points/instances given for training, then the algorithm is guaranteed to converge in at most one iteration of Expectation & Maximization"

---

### Q2 [2023-24 EC3 Regular, Q4 - 4.5+1.5+2=8M] (Gaussian Mixture Model)

Use case: Committee of experts data. Build a machine learning model to cluster the original literary work.

| Literary Work ID | Readership Base | Number of Translations |
|-----------------|-----------------|----------------------|
| ID:1 | 70 | 5 |
| ID:2 | 30 | 3 |
| ID:3 | 50 | 7 |

**Note:** Wherever applicable round all the calculation to 4 decimal places. Use the given features as is without scaling.

a) Assume that the above literary works data follows Gaussian Distribution. Apply Gaussian Mixture Model based soft clustering only for one iteration to cluster the points among two clusters. Use initial values of (Mean of features with same order, Standard Deviation of features with same order from above tabulated attributes, weights) for:
- Cluster 1 = ((20, 1), (10, 1), 0.5)
- Cluster 2 = ((50, 7), (10, 1), 0.5)

Show all the step by step computations clearly. Show the final responsibility matrix at the end of the first iteration. [4.5M]

b) Find only the new mixture weights and cluster means at the end of first iteration. Note: No need to calculate other prototypes standard deviations [1.5M]

c) Give a plagiarism free example & sample feature design from the domain of healthcare where soft clustering is best suited than hard clustering. Justify your choice in no more than 40 words [2M]

---

## 6. Logistic Regression

### Q1 [2023-24 EC3 Makeup, Q7a - 5M]

You are fitting a logistic regression model to predict whether an email is spam (class 1) or not (class 0) based on the length of the email's subject line (Feature). The model's coefficients are:

- Coefficient: 0.03
- Intercept: -1.2

Calculate the predicted probability of an email being spam for an instance with a subject line length of 50 characters and classify the instance, assuming 70% is the threshold. Additionally, justify the assignment of a specific class to the given instance.

Formula: $\text{logit}(p) = \beta_0 + \beta_1 \times \text{Feature}$

Sigmoid: $p = \frac{1}{1 + e^{-\text{logit}(p)}}$

---

## 7. Linear & Polynomial Regression

### Q1 [2023-24 EC3 Regular, Q3b - 3M]

What is the best curve of the form $y = a + bx + cx^2$ in terms of minimizing square error that fits the following training dataset $(x, y)$: $(-1, 0), (1, 10), (2, 24), (-2, 4)$?

---

## 8. Decision Trees & Information Gain

### Q1 [2023-24 EC3 Makeup, Q7b - 1.5M]

What are the shortcomings of using Entropy (Information Gain) as a heuristic measure while building decision trees?

---

### Q2 [2023-24 EC3 Regular, Q2a - 1+1=2M]

a) How can Decision Tree models aid in enhancing the Interpretability of Machine Learning Systems? [1M]

b) What are their limitations? [1M]

---

## 9. Model Evaluation & Comparison


### Q1 [2023-24 EC3 Regular, Q2b - 5M]

You are a ML engineer working in a large organization. Your organization is very popular and hackers always want to target your organization to tarnish its image in the market. So, the employees in your organization receive a lot of spam emails. Your boss asks you to build a spam filter for distinguishing between genuine e-mails and unwanted spam e-mails. Assuming spam to be the positive class, answer the following questions:

1) Describe Precision and Recall with respect to the given problem [1M]

2) Explain what happens if you optimize each of the above parameters [2M]

3) Which would be more important to optimize and why? [2M]

---

### Q2 [2023-24 EC3 Makeup, Q6 last part - 2.5M]

You have trained a ML model and discovered that it yields unacceptably high error on the test data. You also plotted a learning curve for both test data and training data as shown below.

[DIAGRAM IN ORIGINAL - Learning curve showing both training and test error converging at high error]

Comment on the performance of this ML model. Additionally, discuss strategies to address such cases, including the approaches and measures you would take in such scenarios.

---

### Q3 [2023-24 EC3 Regular, Q3a - 2M]

Suppose you tried logistic regression with 2 distinct values of learning rate and plotted the learning curve for each case where $J(\theta)$ represents the cost function. For which of the following cases (A or B), the learning rate is possibly too large? Justify your answer.

[DIAGRAM IN ORIGINAL - Two plots: A shows convergence, B shows divergence/oscillation]

---

### Q4 [2023-24 EC3 Makeup, Q7c - 0.5+1M]

Which of the following charts of Residual Sum of Squares (RSS) and model complexity represent training phase for a fixed dataset? Justify.

[DIAGRAM IN ORIGINAL - Two RSS vs complexity curves]

---

## 10. Interpretability & Ethics in ML

### Q1 [2023-24 EC3 Makeup, Q6 - 2M]

Illustrate a situation in which a lack of interpretability in a model could result in ethical issues. Explain how interpretability could mitigate these concerns.

---

## 11. Comprehensive Regular AK - Full Questions

### Q1 [Comprehensive Regular, Q1 - 5M] (Naive Bayes)

Consider the following dataset for Iris flower classification using Gaussian Naive Bayes. Given training data with 3 classes (Setosa, Versicolor, Virginica) and features (Sepal Length, Sepal Width, Petal Width), classify a new instance by computing:
- Prior probabilities for each class
- Likelihood using Gaussian PDF: $P(x|c) = \frac{1}{\sqrt{2\pi\sigma^2}} e^{-\frac{(x-\mu)^2}{2\sigma^2}}$
- Posterior probabilities

---

### Q2 [Comprehensive Regular, Q2 - 5M] (SVM)

Given training data points in 2D space with binary labels, find the maximum margin hyperplane:
- Identify support vectors
- Compute the margin width $= \frac{2}{||w||}$
- Show the Lagrangian dual formulation:

$$\max_\alpha \sum_{i=1}^{n} \alpha_i - \frac{1}{2} \sum_{i,j} \alpha_i \alpha_j y_i y_j x_i^T x_j$$

subject to $\alpha_i \geq 0$ and $\sum \alpha_i y_i = 0$

---

### Q3 [Comprehensive Regular, Q3 - 8M] (KNN Regression)

Given training data and query point:
a) Apply 3-NN regression to estimate target value using Manhattan distance.
b) Apply distance-weighted KNN where weight $w_i = \frac{1}{d(x_q, x_i)}$
c) Compare the two approaches.

---

### Q4 [Comprehensive Regular, Q4 - 7M] (AdaBoost)

Consider binary classification with 5 data points. Using AdaBoost with decision stumps:

**Iteration 1:**
- Initial weights: $w_i = \frac{1}{5}$ for all i
- Find best decision stump (lowest weighted error)
- Compute error rate: $\epsilon = \sum_{i: h(x_i) \neq y_i} w_i$
- Compute amount of say: $\alpha = \frac{1}{2} \ln\left(\frac{1-\epsilon}{\epsilon}\right)$
- Update weights: $w_i^{new} = w_i \times e^{-\alpha y_i h(x_i)}$

**Iteration 2:**
- Repeat with updated weights

Final prediction: $H(x) = \text{sign}\left(\sum_{t=1}^{T} \alpha_t h_t(x)\right)$

---

### Q5 [Comprehensive Regular, Q5 - 8M] (K-Means)

Given 2D data points: (2,10), (2,5), (8,4), (5,8), (7,5), (6,4), (1,2), (4,9)

Initial centroids: $C_1 = (2,10)$, $C_2 = (5,8)$, $C_3 = (1,2)$

a) Perform 2 complete iterations showing:
- Distance calculation (Euclidean) from each point to each centroid
- Cluster assignment
- New centroid calculation

b) Calculate WCSS (Within-Cluster Sum of Squares) after final iteration:
$$WCSS = \sum_{k=1}^{K} \sum_{x_i \in C_k} ||x_i - \mu_k||^2$$

---

## 12. Comprehensive Makeup AK - Full Questions


### Q1 [Comprehensive Makeup, Q1 - 5M] (Naive Bayes)

Given patient dataset with symptoms (Fever, Cough, Fatigue) and diagnosis (Flu/No Flu):

| Patient | Fever | Cough | Fatigue | Diagnosis |
|---------|-------|-------|---------|-----------|
| 1 | Yes | Yes | Yes | Flu |
| 2 | Yes | No | Yes | Flu |
| 3 | No | Yes | No | No Flu |
| 4 | Yes | Yes | No | Flu |
| 5 | No | No | Yes | No Flu |
| 6 | No | Yes | Yes | No Flu |

Classify new patient: Fever=Yes, Cough=Yes, Fatigue=No using Naive Bayes. Show:
- $P(\text{Flu}) = ?$, $P(\text{No Flu}) = ?$
- All conditional probabilities (likelihoods)
- Posterior computation and final classification

---

### Q2 [Comprehensive Makeup, Q2 - 5M] (AdaBoost)

Given dataset with 4 training samples:

| X1 | X2 | Label |
|----|----|-------|
| 1 | 2 | +1 |
| 2 | 1 | +1 |
| 3 | 3 | -1 |
| 4 | 2 | -1 |

Using AdaBoost:
a) Build 3 decision stumps (weak learners). Show the feature and threshold for each.
b) For each stump, compute:
   - Weighted error $\epsilon_t$
   - Amount of say $\alpha_t = \frac{1}{2}\ln\frac{1-\epsilon_t}{\epsilon_t}$
   - Updated sample weights
c) Show final strong classifier prediction for test point (2.5, 2).

---

### Q3 [Comprehensive Makeup, Q3 - 6M] (Locally Weighted Regression)

Given patient data:

| Patient | Eye Opening | Verbal | Motor | Risk Score |
|---------|-------------|--------|-------|------------|
| 1 | 3 | 4 | 3 | 6 |
| 2 | 2 | 3 | 2 | 4 |
| 3 | 4 | 5 | 4 | 8 |
| 4 | 1 | 2 | 1 | 2 |
| 5 | 3 | 3 | 3 | 5 |

Query: Eye Opening=3, Verbal=4, Motor=3

a) Use KNN with k=3 (Manhattan distance) to predict risk. [2M]
b) Apply locally weighted regression with 2-NN. Kernel: $K(d) = e^{-d^2}$. Initial model: $Risk = 5 + 0.2 \times Verbal + 0.3 \times Motor$. Perform one iteration of gradient descent with learning rate = 0.05. [4M]

---

### Q4 [Comprehensive Makeup, Q4 - 6M] (Hierarchical Clustering)

Given data points: A(1,1), B(2,1), C(4,3), D(5,4), E(5,3)

a) Perform agglomerative hierarchical clustering using single linkage (minimum distance). Show step-by-step:
- Initial distance matrix
- Merge closest clusters at each step
- Updated distance matrix after each merge

b) Draw the dendrogram. [2M]

c) If we cut the dendrogram to get 2 clusters, what are the resulting clusters? [1M]

---

## 13. Sample QP EC3 - Full Questions

### Q1 [Sample QP EC3 - 5M] (Logistic Regression - Gradient Descent)

Given training data:

| X | Y |
|---|---|
| 1 | 0 |
| 2 | 0 |
| 3 | 1 |
| 4 | 1 |

Model: $h_\theta(x) = \sigma(\theta_0 + \theta_1 x)$ where $\sigma(z) = \frac{1}{1+e^{-z}}$

Cost function: $J(\theta) = -\frac{1}{m}\sum_{i=1}^{m}[y^{(i)}\log(h_\theta(x^{(i)})) + (1-y^{(i)})\log(1-h_\theta(x^{(i)}))]$

Starting with $\theta_0 = 0$, $\theta_1 = 0$, learning rate $\alpha = 0.1$:

a) Compute initial predictions $h_\theta(x_i)$ for all data points.
b) Compute cost $J(\theta)$.
c) Compute gradients $\frac{\partial J}{\partial \theta_0}$ and $\frac{\partial J}{\partial \theta_1}$.
d) Perform one iteration of gradient descent and report new $\theta$ values.

---

### Q2 [Sample QP EC3 - 8M] (Decision Tree with Information Gain)

Given dataset:

| Outlook | Temperature | Humidity | Wind | PlayTennis |
|---------|-------------|----------|------|------------|
| Sunny | Hot | High | Weak | No |
| Sunny | Hot | High | Strong | No |
| Overcast | Hot | High | Weak | Yes |
| Rain | Mild | High | Weak | Yes |
| Rain | Cool | Normal | Weak | Yes |
| Rain | Cool | Normal | Strong | No |
| Overcast | Cool | Normal | Strong | Yes |
| Sunny | Mild | High | Weak | No |
| Sunny | Cool | Normal | Weak | Yes |
| Rain | Mild | Normal | Weak | Yes |

a) Calculate entropy of the entire dataset: $H(S) = -\sum p_i \log_2 p_i$ [1M]

b) Calculate Information Gain for each attribute: [4M]
$$IG(S, A) = H(S) - \sum_{v \in Values(A)} \frac{|S_v|}{|S|} H(S_v)$$

c) Select root node and show first split. [1M]

d) Continue building tree for one more level. [2M]

---

### Q3 [Sample QP EC3 - 5M] (Cross Validation & Model Selection)

a) Explain 5-fold cross validation with a diagram. How does it differ from Leave-One-Out? [2M]

b) Given a model with the following performance across 5 folds:

| Fold | Training Accuracy | Validation Accuracy |
|------|-------------------|---------------------|
| 1 | 95% | 82% |
| 2 | 94% | 80% |
| 3 | 96% | 79% |
| 4 | 95% | 81% |
| 5 | 94% | 83% |

Comment on the model's performance. Is it overfitting? What would you suggest? [3M]

---

## 14. Bias-Variance & Regularization

### Q1 [Sample QP Students - Multi-part]

a) Explain the bias-variance tradeoff. How does model complexity affect each? [2M]

b) For a polynomial regression with degree d on the dataset below:

| X | Y |
|---|---|
| 1 | 2.1 |
| 2 | 3.9 |
| 3 | 6.2 |
| 4 | 7.8 |
| 5 | 10.1 |

- What happens when d=1? (underfitting/high bias)
- What happens when d=10? (overfitting/high variance)
- What is the optimal d?

c) Compare L1 (Lasso) vs L2 (Ridge) regularization: [3M]

L1: $J(\theta) = \text{MSE} + \lambda\sum|\theta_i|$

L2: $J(\theta) = \text{MSE} + \lambda\sum\theta_i^2$

- Effect on model coefficients
- Feature selection property of L1
- When to use each

---

## 15. Gradient Descent Variants

### Q1 [Sample QP Students - Multi-part]

Consider linear regression: $h_\theta(x) = \theta_0 + \theta_1 x$

Cost function: $J(\theta) = \frac{1}{2m}\sum_{i=1}^{m}(h_\theta(x^{(i)}) - y^{(i)})^2$

Update rule: $\theta_j := \theta_j - \alpha \frac{\partial J}{\partial \theta_j}$

Given data: (1,1), (2,2), (3,3), (4,4)

Starting: $\theta_0 = 0$, $\theta_1 = 0$, $\alpha = 0.01$

a) Compute gradient for Batch GD (use all 4 points). [2M]

b) Compute gradient for SGD (use only point (1,1)). [1M]

c) Compute gradient for Mini-Batch GD (batch size=2, use first 2 points). [1M]

d) Compare convergence behavior of the three methods. [2M]

---
