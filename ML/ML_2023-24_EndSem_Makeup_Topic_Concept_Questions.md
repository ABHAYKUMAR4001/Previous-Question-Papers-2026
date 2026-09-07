# ML 2023–24 End-Sem Make-up — Topic → Concept → Questions

> Source: `2023-24_ML_End-Semester_Make-up_QP_Anwer-keys.pdf`. Repeated question sets already present in the classified collection are omitted question-by-question; non-duplicate questions are retained.

## Naive Bayes / Bayesian Learning
### Concept: Multinomial Naive Bayes text classification
- Given three labelled text documents using Hindi/India/Kannada/Chinese, classify “Chinese Kannada Chinese” using Multinomial NB with all intermediate calculations. [5]

## Support Vector Machines
### Concept: Support vectors and maximum-margin hyperplane
- Given a 2-D labelled dataset, identify the support vectors and determine the linear SVM hyperplane equation; Lagrange-method solution is also acceptable. [4]

## Instance-Based Learning
### Concept: k-NN regression with Manhattan distance
- For a Glasgow Coma Scale dataset, predict a new patient’s risk using 3-NN, Manhattan distance and average aggregation. [3]

### Concept: Locally weighted regression + nearest neighbours + one GD update
- Starting from a supplied local regression equation, use the two nearest neighbours, the supplied distance kernel, and one gradient-descent iteration to update weights and predict the query patient’s risk. [5]

## Unsupervised Learning
### Concept: k-Modes clustering for categorical features
- Cluster categorical Glasgow Coma Scale observations into three clusters for one E/M iteration using the supplied matching-distance formula; calculate new centroids and reason about convergence when k equals the number of data points. [7]

## Ensemble Learning
### Concept: AdaBoost sample-weight update
- From a partially filled one-iteration AdaBoost table with uniform initial weights, calculate an updated unnormalised instance weight and identify which points were misclassified. [3]

### Concept: Random Forest feature randomness
- Explain why Random Forest introduces feature randomness and how it reduces correlation among trees when dominant features exist. [2]

## Model Evaluation / Responsible ML
### Concept: Interpretability and ethics
- Give a situation where lack of model interpretability creates ethical concerns and explain how interpretability mitigates them.

### Concept: Learning curves and high bias
- Given training/test learning curves with unacceptably high test error, diagnose model behaviour and suggest remedies. [2.5]

## Logistic Regression
### Concept: Probability, sigmoid and non-default threshold
- With coefficient 0.03 and intercept −1.2, calculate spam probability for subject length 50 and classify using a 70% threshold, with justification. [5]

## Decision Trees
### Concept: Limitation of Information Gain
- Explain why Information Gain is biased toward attributes with many distinct values. [1.5]

## Regression / Model Complexity
### Concept: RSS versus model complexity
- Select the chart representing training RSS as model complexity increases and justify. [1.5]