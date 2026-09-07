# ML 2022–23 End-Sem — Topic → Concept → Questions

> Source: senior-shared 3-page End-Sem paper. Questions are retained unless the same question set already exists in the classified collection.

## KNN / Voronoi / LOOCV
### Concept: Voronoi boundary, 1-NN probability and classification
- Dataset {(-2,-1),(-2,1),(2,-1),(2,1),(0,0)} with (0,0) labelled “-” and the four outer points labelled A/B/C/D. Draw the Voronoi tile around (0,0), specify boundary equations, find probability that a uniformly chosen point from -2≤x≤2,-1≤y≤1 is classified “-” by 1-NN, and identify probabilities of classifications A/B/C/D.

### Concept: Maximum-margin classifier and Leave-One-Out Cross Validation
- For a 2-D binary dataset with 3 positive and 3 negative samples: find the maximum-margin classifier and margin; repeat after leaving out each sample; calculate LOOCV accuracy and LOOCV error rate.

## Naive Bayes / Generative Classification
### Concept: Gaussian class-conditional densities and decision boundary
- Given two 2-D Gaussian class-conditional probability distributions with equal priors, derive the Naive-Bayes decision boundary and analyze its equation/shape for different relationships between σx and σy, including whether the boundary is linear.

### Concept: Multinomial Naive Bayes text classification
- Training set: 200 documents of classes “+” and “-”, vocabulary size 1500 and given total word counts. Classify a 4-word test document using Naive Bayes, with some test words absent from training.

## AdaBoost
### Concept: Decision stump, learner importance and sample-weight update
- Six labelled 1-D points are given. A decision stump x≤c / x>c misclassifies only x=1 and x=2 in its first iteration. Find possible c values, importance of the first classifier and instance weights after the first iteration.

## Linear Regression
### Concept: Uniqueness / identifiability of least-squares parameters
- A least-square fit y=2x+3 is obtained, but only the points (-2,α),(0,1),(2,β) remain. Can α and β be uniquely recovered while preserving y=2x+3 as the best least-square fit? Justify mathematically.

## Logistic Regression
### Concept: Sigmoid decision boundary and classification accuracy
- For O(x,y)=1/(1+exp(-w0-7.5x-7.5y)), find the range of w0 that gives 100% classification accuracy on the four binary input points (0,0),(0,1),(1,0),(1,1), with only (1,1) positive.