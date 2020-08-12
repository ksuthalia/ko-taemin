---
title: Logistic Regression
category: Supervised Learning
order: 1
---

Supervised Learning (Continuous Variable Prediction)

Logistic Regression



### - Classification and Representation

The classification problem is just like the regression problem, except that the values we now want to predict take on only small number of discrete values.

The binart classification problem in which y can take on only two values: 0 and 1


### - Hypothesis Representation

Sigmoid Function (Logistic Function)

0 <= h_θ(x) <= 1

h_θ(x) = g(θ^T * x)

z = θ^T * x

g(z) = 1 / (1 + e^-z)

**h_θ(x) will give us the probability that our output is 1. => h_θ(x) = 0.7 gives us a probability of 70% that our output is 1**

h_θ(x) = P(y = 1|x;θ ) = 1 - P(y = 0|x;θ)
P(y = 1|x;θ ) + P(y = 0|x;θ) = 1

### - Decision Boundary

The Decision Boundary is the line that seperates the area where y = 0 and where y = 1.

h_θ(x) >= 0.5 -> y = 1
h_θ(x) < 0.5 -> y = 0

g(z) >= 0.5 when z >= 0

z = θ^T * x >= 0 -> y = 1
z = θ^T * x < 0 -> y = 0


### - Logistic Regression Model





### - Overfitting and Underfitting

1. Overfitting(high variance): fits the available data but does not generalize well to predict new data
2. Underfitting(high bias): hypothesis function h maps poorly to the trend of the data (causes: too simple or too few feature)

There is a terminology applied to both linear and logistic regression. There are two main options to address the issue of overfitting

1) Reduce the number of features

- manually select which featues to keep
- use a model selection algorithm

2) Regulariztion

- keep all the features, but reduce the magnitude of parameters θ_j
- Regularization works well when we have a lot of slightly useful features








