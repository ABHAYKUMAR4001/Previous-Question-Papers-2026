# ML Final Compilation — Unique Topic → Concept → Questions

> Source: `ML Final.pdf` (32-page scan/compilation containing multiple papers). Questions already represented by the other classified papers are omitted individually; the entries below capture distinct question patterns visible in this compilation.

## Regularization / Bias–Variance
### Concept: Cross-validation selection of λ
- Logistic regression with 100,000 bag-of-words features and 5,000 samples is evaluated at several λ values using 5-fold CV. Use the results to explain λ’s bias–variance trade-off, choose the best λ, identify likely regularization type, explain underfitting at large λ, and compare L1 vs L2 with highly correlated features.

## Model Evaluation
### Concept: Precision–recall trade-off in healthcare
- For a rare-condition classifier, explain why lowering the decision threshold increases recall but reduces precision, and justify why high recall can be preferable in healthcare despite more false positives.

## Instance-Based Learning
### Concept: Algorithm selection for streaming recommendation
- For a streaming-service recommendation system that must adapt immediately to new ratings without frequent retraining, choose an appropriate learning algorithm and justify in terms of training time, prediction time, memory and generalization.

## Naive Bayes
### Concept: Feature evidence and imbalanced data
- From spam/not-spam feature counts, identify the strongest evidence for spam, predict a test email without full probability calculation, explain why Naive Bayes may misclassify a particular email, and discuss whether accuracy or precision/recall is preferable on an imbalanced spam dataset.

## Support Vector Machines
### Concept: Kernel trick, soft margin and dual α
- Explain what happens when data are not linearly separable with hard-margin SVM; interpret a supplied polynomial kernel without explicitly constructing transformed features; explain why kernel SVM can create nonlinear boundaries; explain why soft-margin SVM allows violations; interpret αᵢ=0 versus αᵢ>0.

## AdaBoost
### Concept: Decision-stump enumeration and weak-learner weight
- For four ordered 1-D points, determine initial sample weights, enumerate possible decision stumps, identify misclassified points for a stump, compute its error/importance, update sample weights, and reason about statements concerning nonseparable data and training error.

## Unsupervised Learning
### Concept: K-means/GMM assumptions and preprocessing
- For elliptical customer clusters, explain why K-means can perform poorly, how standardization affects results, what problems arise from poor centroid initialization, and compare GMM’s covariance modelling with K-means assumptions.

## Bayesian Learning
### Concept: Bayes theorem in medical diagnosis
- Given disease prevalence plus sensitivity/symptom likelihoods, calculate the posterior probability of disease after observing the symptom.

## Decision Trees / Interpretability
### Concept: Decision-tree interpretability and limitations
- Explain how decision trees improve interpretability and state limitations such as overfitting, complexity with deep trees and majority-class bias.

## Optimization / Regression
### Concept: Gradient-descent learning curve
- Given two cost-versus-iteration curves for logistic regression, identify which learning-rate behaviour indicates divergence versus convergence.

### Concept: Least-squares parameter fitting
- Minimize a supplied sum-of-squares expression in parameters a, b and c and determine the optimum values.

## KNN / Ensemble
### Concept: k-NN robustness to outliers and ensemble voting
- Apply 6-NN, 3-NN and 1-NN to a supplied literary-work dataset, discuss which k is more vulnerable to an outlier, and combine multiple models by majority voting.

## Gaussian Mixture Models
### Concept: One EM iteration with supplied initial parameters
- For a two-cluster Gaussian mixture with supplied initial means/variances/weights, calculate responsibilities, new mixture weights and updated cluster means after one EM iteration.