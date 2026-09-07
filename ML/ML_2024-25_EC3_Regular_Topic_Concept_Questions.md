# ML 2024–25 EC-3 Regular — Topic → Concept → Questions

> Source: `ML Regular AK.pdf`. Duplicate questions are omitted individually only.

## Decision Trees / Model Evaluation
### Concept: Training vs true error, overfitting and pruning
- From training/test accuracy curves as tree size grows: judge whether training error is an unbiased estimate of true error; explain why increasing tree depth/nodes increases overfitting; select the best tree size for new data; list and explain at least three pre-pruning strategies. [6]

## Logistic Regression
### Concept: Multicollinearity
- Two highly positively correlated predictors are used for churn prediction. Explain effects on performance, coefficient stability and interpretability, and give at least two remedies such as feature removal/combination, L2 regularization or dimensionality reduction. [5]

## Instance-Based Learning
### Concept: Gower distance + weighted k-NN
- For mixed numerical/categorical/binary property features, compute Gower distances, identify the 3 nearest neighbours, perform inverse-distance weighted voting and predict Buyer Interest. [5]

## Bayesian Learning
### Concept: Multinomial Naive Bayes with Laplace smoothing
- From three labelled Technology/Non-Technology text examples, classify “A new AI gadget” using Multinomial NB with Laplace smoothing and show priors/conditional probabilities. [5]

## Bias–Variance / SVM / Feature Engineering
### Concept: Remedies for underfitting
- A logistic-regression model performs poorly on both training and test data. Evaluate whether linear SVM, increased regularization, RBF SVM, and polynomial feature transformation are promising, with justification. [6]

## Ensemble Learning
### Concept: Gradient Boosting learning rate
- Explain what learning rate means, consequences of values that are too small/large, and the trade-off between learning rate and number of estimators. [5]

### Concept: Majority-vote ensemble error
- Three independent binary classifiers each have error 0.3. Calculate majority-vote ensemble error. [2]

## Unsupervised Learning
### Concept: K-means vs GMM on non-spherical/nonlinear clusters
- Given a three-cluster non-linear distribution, explain what K-means and a 3-component GMM would do and compare their limitations. [3]

### Concept: GMM initialization and EM local optima
- Explain problems caused by random initialization of GMM means/covariances and ways to improve initialization such as K-means initialization or multiple restarts. [3]