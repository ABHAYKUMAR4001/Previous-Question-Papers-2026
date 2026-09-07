# ML 2023–24 Mid-Sem Regular — Topic → Concept → Questions

> Source: AIML ZG565 Mid-Semester Regular answer-key paper. Repeated question sets are omitted individually rather than excluding the paper.

## Data Preprocessing / Data Quality
### Concept: Missing values, outliers, inconsistent formats and units
- Given a master-data sample containing inconsistent names, impossible age, missing height, kg/lb mismatch, malformed blood group and inconsistent binary COVID-result representations, identify at least five data-quality issues and suggest remedies.

## Generative vs Discriminative Learning
### Concept: Density estimation and classifier choice
- Need to classify job applications as good/bad and detect applicants who lie using density estimation/outlier detection. Recommend discriminative or generative classifier and justify.

## Ridge Regression / Bias–Variance
### Concept: High bias vs high variance and λ selection
- Ridge regression has training and validation errors almost equal and fairly high. Diagnose high bias/high variance, suggest steps, and state whether λ should increase or decrease with justification.

## Linear Regression / Optimization
### Concept: Gradient descent vs normal equation at very high dimension
- For n=2,000,000 instances and m=300,000 features in multivariate linear regression, choose gradient descent or least-squares/normal-equation methods and justify computationally.

## Logistic Regression
### Concept: Zero training cost and generalization
- Logistic-regression cost J(θ0,θ1)=0. Evaluate several statements: perfect unseen-data performance; whether hθ(x(i))=y(i) for every training example; whether θ0=θ1=0 is necessary; and whether J can equal zero. Justify each.
### Concept: Feature scaling and gradient-descent convergence
- Explain importance of feature scaling while learning logistic-regression parameters θ.

## Model Evaluation
### Concept: Confusion matrix and imbalanced classifier behavior
- Fraud classifier evaluated on 200 transactions: true Fraud→(60 Fraud,0 Not Fraud), true Not Fraud→(120 Fraud,20 Not Fraud). Give crisp point-wise observations on classifier performance with supporting justification.

> Note: This uses the same numerical confusion-matrix pattern as the 2023–24 Make-up paper, but the task is not identical: this question asks for performance observations, while the Make-up explicitly asks class-wise precision and recall. Therefore it is retained rather than discarded.

## Decision Trees
### Concept: ID3, entropy, information gain and root selection
- Literary-work nomination dataset: use ID3 to determine which of Readership Base and Writer's Reputation spread in other countries is the best root node, show calculations, and draw the resulting decision tree.
### Concept: Training-set evaluation and overfitting
- Justify with an example why assessing a decision-tree classifier only on its training dataset is detrimental.