# ML 2022–23 Mid-Sem — Topic → Concept → Questions

> Source: senior-shared 2-page Mid-Sem paper. Repeated question sets are omitted individually rather than dropping the whole paper.

## Decision Trees
### Concept: Entropy, information gain and best split
- For the 9-instance dataset with attributes a1,a2,a3 and binary class, compute class entropy, information gain of a1 and a2, and determine the best split between a1 and a2.
### Concept: Number of possible decision trees
- How many distinct decision trees can be generated with 4 Boolean attributes?

## K-Means / Geometric Classification / LOOCV
### Concept: Class centroids and equidistant decision boundary
- For a 2-D binary dataset with 4 black-diamond and 3 gray-diamond points, find the K-means/mean class centers and the linear boundary equidistant from the two centers.
### Concept: Training error and leave-one-out cross-validation
- Find training error rate; determine whether removing a sample can change the boundary so that the removed sample lies on the opposite side; calculate LOOCV error rate.

## Logistic Regression
### Concept: NOT gate with sigmoid and gradient update
- Logistic-regression classifier implements NOT gate. At iteration t, w=(0), w1=1. Find loss at t; update w0,w1 at t+1 with learning rate η=1; repeat with L2 (ridge) regularization λ=1.

## Basis-Function / Weighted Regression
### Concept: Gaussian basis functions and optimal weights
- Response y is a linear combination of two Gaussian basis functions centered at -1 and +1 with variances 1 and 2. Given target values at x=-1 and x=1, find optimal w1,w2, optimal fitting error, and estimated response at x=0.