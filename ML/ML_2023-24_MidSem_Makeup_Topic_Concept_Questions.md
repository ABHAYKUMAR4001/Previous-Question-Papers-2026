# ML 2023–24 Mid-Sem Make-up — Topic → Concept → Questions

> EC-2 Make-up, AIML ZG565. Duplicate question sets are omitted individually.

## ML Fundamentals
### Concept: Supervised vs Unsupervised vs Reinforcement Learning
- For a hospital diagnosis scenario and patient-response grouping scenario, identify suitable ML technique(s) and justify.
- A Go-playing system first learns from human gameplay and later from rewards while self-playing. Describe the transition in ML approach.

### Concept: Overfitting and generalization
- Model performs very well on training data but poorly on unseen instances. State likely reason and suggest two solutions.

## Linear Regression / Transformations
### Concept: Exponential model linearization and least squares
- For X={1,2,3,4}, Y={exp(2),exp(4),exp(6.3),exp(9.2)} and y=e^(αx), use linear regression to find best α and optimal total squared error.

## Logistic Regression / Regularization / Optimization
### Concept: L2 regularization and overfitting
- Logistic regression with L2 regularization is overfitting. Is the statement “decreasing the regularization parameter reduces overfitting” true or false? Justify.
### Concept: L1 regularization and feature selection
- Which regularization technique can be used for feature selection? Why?
### Concept: Learning-rate selection in gradient descent
- Can η be any random value? Explain consequences of too-small and too-large learning rates.

## Model Evaluation
### Concept: Confusion matrix, class-specific precision and recall
- Tumor classifier on 200 test instances has confusion matrix: true Malignant→(60 Malignant,0 Benign), true Benign→(120 Malignant,20 Benign). Compute precision and recall with respect to both classes and give crisp performance observations.

## Decision Trees
### Concept: ID3, entropy and information gain
- Glasgow Coma Scale dataset with Eye Opening, Verbal Responses and Motor Responses: construct decision tree to depth 1 using ID3/information gain, show calculations and final tree.
### Concept: Categorical features in decision trees
- Justify with an example: unless necessary, converting categorical features to numerical form may be omitted when modelling a decision-tree classifier.