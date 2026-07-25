# ML (Machine Learning) - Comprehensive/End-Semester Exam Questions (Full Verbatim)

**Papers Covered:**
- 2023-24 End-Semester Regular (EC3R, 40% weightage)
- 2023-24 End-Semester Makeup (EC3M, 40% weightage)
- ML Comprehensive Regular AK (40 marks)
- ML Comprehensive Makeup AK (40 marks)
- ML Comprehensive Sample QP
- Sample QP - EC3

> **Note:** Questions involving diagrams/figures are marked with [DIAGRAM IN ORIGINAL]. Refer to the original PDF for visual content.

---

## 1. Bayesian Learning / Naive Bayes Classification

### Q1 [2023-24 EC3 Regular, Q1 - 4M]

In a specific population, the probability of a person experiencing a particular symptom given they've had a Meningitis is 80%, whereas the chances of experiencing the same symptom without Meningitis is 10%. If the prevalence of Meningitis in the population is 5%, what is the probability that a person displaying the symptom indeed has Meningitis?

Given:
- $P(\text{Symptom} | \text{Disease}) = 80\%$
- $P(\text{Symptom} | \neg\text{Disease}) = 10\%$
- $P(\text{Disease}) = 5\%$

Goal: Find $P(\text{Disease} | \text{Symptom})$ using Bayes' Theorem:

$$P(D|S) = \frac{P(S|D) \cdot P(D)}{P(S|D) \cdot P(D) + P(S|\neg D) \cdot P(\neg D)}$$

---

### Q2 [2023-24 EC3 Makeup, Q1 - 5M]

Consider the following dataset for text classification where three training instances are given with corresponding classifications into the '+' or '-' category:

| Document | Class |
|----------|-------|
| Hindi India India | + |
| India Kannada Hindi | + |
| Chinese Hindi India | - |

Showing all intermediate calculations, find the appropriate classification for the test instance: **"Chinese Kannada Chinese"** using the Multinomial NB text classification approach.

---

## 2. Support Vector Machines (SVM)

### Q1 [2023-24 EC3 Makeup, Q2 - 4M]

Create a discriminative model using linear SVM. Training dataset:

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

A. Find the support vectors. [1M]
B. Determine the equation of hyperplane. [3M]

---

## 3. Instance-Based Learning (KNN & Locally Weighted Regression)

### Q1 [2023-24 EC3 Regular, Q4 - 3.5+1.5+1=6M]

Committee of experts data for literary work nomination:

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

a) Use 6-NN, 3-NN & 1-NN separately to classify. Similarity measure: [3.5M]

$$\text{Similarity}(data_1, data_2) = \frac{\text{Number of matching categorical attributes}}{\text{Total number of categorical attributes}}$$

b) Which k-NN is more robust to outliers? Justify (max 40 words). [1.5M]

c) Create ensemble using majority voting to predict class. [1M]

---

### Q2 [2023-24 EC3 Makeup, Q3 - 3+5=8M]

Glasgow Coma Scale data:

| Patient | Eye Opening | Verbal Responses | Motor Responses | Risk Factor |
|---------|-------------|-----------------|-----------------|-------------|
| 1 | 2 | 3 | 2 | 3 |
| 2 | 3 | 4 | 3 | 5 |
| 3 | 4 | 4 | 4 | 7 |
| 4 | 2 | 2 | 3 | 4 |
| 5 | 1 | 1 | 1 | 2 |

**Query Instance:** <Eye Opening = 5, Verbal Responses = 5, Motor Responses = 5>

**Note:** Use only Manhattan distance. No scaling required. Round to 4 decimal places.

i) Predict risk factor using 3-NN model. [3M]

ii) Locally weighted regression with initial model: [5M]

$$\text{Patient Risk} = 10 - 0.1 \times X_{\text{VERBAL}} - 0.1 \times X_{\text{MOTOR}}$$

Apply 2-NN with kernel: $K(d(x_q, x_i)) = \frac{-1}{d(x_q, x_i)}$

Apply gradient descent for ONE iteration with learning rate = 0.1. Predict risk factor.

---

## 4. Ensemble Learning (AdaBoost, Random Forest)

### Q1 [2023-24 EC3 Makeup, Q5 - 3M]

In a single iteration of AdaBoost on three sample points, uniform initial weights. Ground truth labels and predictions are binary (+1 or -1).

[TABLE WITH MISSING VALUES IN ORIGINAL]

a) Find the updated weight (before normalization) of X1 instance. [1.5M]

b) Identify misclassified instances. Justify. [1.5M]

---

### Q2 [2023-24 EC3 Makeup, Q5 continued - 2M]

Random Forest is a bagging model that incorporates feature randomness. Clarify the rationale behind introducing feature randomness in Random Forest.

**Key point:** Decision trees in a Random Forest may be highly correlated, especially when there are a few dominating features. Feature randomness decorrelates the trees.

---

## 5. Unsupervised Learning (K-Modes, GMM, K-Means)

### Q1 [2023-24 EC3 Makeup, Q4 - 4+1+2=7M]

Glasgow Coma Scale data (categorical). K-modes clustering into 3 clusters, one iteration.

| Patient | Eye Opening | Verbal Responses | Motor Responses |
|---------|-------------|-----------------|-----------------|
| **Centroid-1** | Bad | Clear | Weak |
| | Bad | Unclear | Weak |
| **Centroid-2** | Good | Others | Weak |
| | Worst | Unclear | Strong |
| | Bad | Unclear | Weak |
| **Centroid-3** | Good | Clear | Strong |

Distance metric:
$$\text{distance}(data_1, data_2) = 10 \times \left(1 - \frac{\text{Number of matching categorical attributes}}{\text{Total number of categorical attributes}}\right)$$

Median rule: Mode if cluster size odd; else least frequent attribute value in entire training data.

a) Show E-step and M-step. [4M]
b) Calculate new centroids. [1M]
c) TRUE/FALSE: "If clusters = data points, algorithm converges in at most one EM iteration." Justify. [2M]

---

### Q2 [2023-24 EC3 Regular, Q4 - 4.5+1.5+2=8M]

Literary works data - Gaussian Mixture Model soft clustering:

| Literary Work ID | Readership Base | Number of Translations |
|-----------------|-----------------|----------------------|
| ID:1 | 70 | 5 |
| ID:2 | 30 | 3 |
| ID:3 | 50 | 7 |

Round to 4 decimal places. No scaling.

Initial values:
- Cluster 1: Mean=(20,1), SD=(10,1), Weight=0.5
- Cluster 2: Mean=(50,7), SD=(10,1), Weight=0.5

a) Apply GMM soft clustering for one iteration. Show responsibility matrix. [4.5M]

Gaussian PDF: $P(x|\mu,\sigma) = \frac{1}{\sqrt{2\pi}\sigma} e^{-\frac{(x-\mu)^2}{2\sigma^2}}$

b) Find new mixture weights and cluster means. [1.5M]

c) Healthcare example where soft clustering > hard clustering. Max 40 words. [2M]

---

## 6. Logistic Regression

### Q1 [2023-24 EC3 Makeup, Q7a - 5M]

Spam prediction model. Coefficient=0.03, Intercept=-1.2.

Calculate probability for subject line length=50 characters. Threshold=70%.

$\text{logit}(p) = \beta_0 + \beta_1 \times \text{Feature} = -1.2 + 0.03 \times 50 = 0.3$

$p = \frac{1}{1 + e^{-0.3}} = \frac{1}{1 + 0.7408} \approx 0.5744$

Since $57.44\% < 70\%$ threshold → **Not Spam**

---

## 7. Linear & Polynomial Regression

### Q1 [2023-24 EC3 Regular, Q3b - 3M]

Best curve $y = a + bx + cx^2$ minimizing square error for: $(-1,0), (1,10), (2,24), (-2,4)$.

Set up normal equations: $X^T X \beta = X^T y$ where:

$$X = \begin{bmatrix} 1 & -1 & 1 \\ 1 & 1 & 1 \\ 1 & 2 & 4 \\ 1 & -2 & 4 \end{bmatrix}, \quad y = \begin{bmatrix} 0 \\ 10 \\ 24 \\ 4 \end{bmatrix}$$

---

## 8. Decision Trees & Information Gain

### Q1 [2023-24 EC3 Makeup, Q7b - 1.5M]

Shortcomings of using Entropy (Information Gain) as heuristic in decision trees:

**Answer:** Information gain measure is biased towards attributes with a large number of distinct values. E.g., Product_ID (unique for every tuple), resulting in large number of partitions as $\text{Info}_{\text{ProductID}}(D) = 0$. Such partitioning is useless.

---

### Q2 [2023-24 EC3 Regular, Q2a - 2M]

a) How can Decision Tree models aid in enhancing Interpretability? [1M]
- Visual Representation: tree structure easily visualized
- Simple Rules: if-then rules understood by non-experts

b) Limitations? [1M]
- Overfitting with complex datasets
- Large trees become unwieldy
- Biased with imbalanced data

---

## 9. Model Evaluation (Precision, Recall, Bias-Variance)

### Q1 [2023-24 EC3 Regular, Q2b - 5M]

Spam filter (spam = positive class):

1) Describe Precision and Recall w.r.t. the problem. [1M]
2) What happens if you optimize each? [2M]
   - Optimize recall → capture more spam, but more genuine emails flagged as spam
   - Optimize precision → fewer false positives, but may miss some spam
3) Which more important? Why? [2M]
   - **Precision** — OK if spam goes to inbox, NOT OK if genuine email goes to spam folder

---

### Q2 [2023-24 EC3 Makeup, Q6 last part - 2.5M]

Learning curve shows high error on both training and test data (converging at high error).

[DIAGRAM IN ORIGINAL]

Comment: **High Bias** (underfitting). Strategies: increase model complexity, add features, reduce regularization.

---

### Q3 [2023-24 EC3 Regular, Q3a - 2M]

Two learning rate curves for logistic regression. Which case has learning rate too large?

[DIAGRAM IN ORIGINAL - A: converges, B: diverges/oscillates]

**Answer:** B — instead of converging, it is diverging.

---

### Q4 [2023-24 EC3 Makeup, Q7c - 1.5M]

Which RSS vs model complexity chart represents training phase?

**Answer:** Training RSS always decreases with complexity (more complex model fits training data better).

---

## 10. Interpretability & Ethics

### Q1 [2023-24 EC3 Makeup, Q6 - 2M]

Illustrate a situation where lack of interpretability causes ethical issues.

**Example:** Automated hiring systems — ML model screens applicants, may discriminate based on gender/ethnicity without providing rationale.

**Mitigation:** Bias detection, accountability, regulatory compliance through interpretable models.

---

## 11. Comprehensive Regular AK - Additional Questions

### Q1 [Comprehensive Regular - 5M] (Naive Bayes with Gaussian)

Apply Gaussian Naive Bayes on Iris data. Compute:
- Prior: $P(C_k) = \frac{n_k}{N}$
- Likelihood: $P(x|C_k) = \frac{1}{\sqrt{2\pi\sigma_k^2}} e^{-\frac{(x-\mu_k)^2}{2\sigma_k^2}}$
- Posterior: $P(C_k|x) \propto P(x|C_k) \cdot P(C_k)$

---

### Q2 [Comprehensive Regular - 8M] (K-Means)

Given 2D data: (2,10), (2,5), (8,4), (5,8), (7,5), (6,4), (1,2), (4,9)

Initial centroids: $C_1=(2,10)$, $C_2=(5,8)$, $C_3=(1,2)$

Perform 2 iterations:
- Euclidean distance from each point to each centroid
- Assign clusters
- Recompute centroids

WCSS: $\sum_{k=1}^{K} \sum_{x_i \in C_k} ||x_i - \mu_k||^2$

---

### Q3 [Comprehensive Regular - 7M] (AdaBoost)

5 data points, binary classification. Decision stumps:

**Iteration 1:**
- Initial weights: $w_i = 1/5$
- Find best stump (lowest weighted error)
- Error: $\epsilon = \sum_{i: h(x_i) \neq y_i} w_i$
- Amount of say: $\alpha = \frac{1}{2}\ln\frac{1-\epsilon}{\epsilon}$
- Update: $w_i^{new} = w_i \times e^{-\alpha y_i h(x_i)}$
- Normalize weights

**Iteration 2:** Repeat

Final: $H(x) = \text{sign}\left(\sum_t \alpha_t h_t(x)\right)$

---

## 12. Sample QP EC3 - Full Questions

### Q1 [Sample QP EC3 - 5M] (Logistic Regression GD)

Training data: (1,0), (2,0), (3,1), (4,1)

Model: $h_\theta(x) = \sigma(\theta_0 + \theta_1 x)$

Cost: $J(\theta) = -\frac{1}{m}\sum[y\log(h_\theta(x)) + (1-y)\log(1-h_\theta(x))]$

Start: $\theta_0=0$, $\theta_1=0$, $\alpha=0.1$

a) Initial predictions (all = 0.5 since $\sigma(0)=0.5$)
b) Compute cost $J$
c) Gradients: $\frac{\partial J}{\partial \theta_j} = \frac{1}{m}\sum(h_\theta(x^{(i)}) - y^{(i)}) \cdot x_j^{(i)}$
d) One iteration update

---

### Q2 [Sample QP EC3 - 8M] (Decision Tree - Information Gain)

PlayTennis dataset (10 instances):

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

a) Entropy of dataset: $H(S) = -\sum p_i \log_2 p_i$ [1M]

b) Information Gain for each attribute: [4M]
$$IG(S, A) = H(S) - \sum_{v \in Values(A)} \frac{|S_v|}{|S|} H(S_v)$$

c) Select root node, show first split. [1M]
d) Continue for one more level. [2M]

---
