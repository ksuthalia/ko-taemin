---
title: Multivariate Linear Regression
category: Supervised Learning
order: 1
---

Supervised Learning (Continuous Variable Prediction)

### Multivariate Linear Regression

* h_θ(x) = θ_0 + (θ_1 * x_1) + ... + (θ_n * x_n)

| notation | meaning |
|--|--|
| n | the number of features(j) |
| m | the number of training examples(i) |
| x_j^(i)| value of feature j in the i^th training example |

* h_θ(x) = [ θ_0 θ_1 ... θ_n ] * [x_0 + x_1 + ... + x_n]^T = θ^T * x  (<= vectorized)

for the convenience reasons we assume that x_0^(i) = 1

### Gradient Descent for Multiple Variables

θ_j := θ_j − α * (1/m) * sum( (h_θ(x^(i)) - y^(i)) * x_j^(i) ) for j := 0...n

### Feature Scaling & Mean Normalization

We want to modify the ranges of our input variables so that they are all roughly the same
1. -1 <= x(i) <= 1
2. -0.5 <= x(i) <= 0.5

The goal is to get all input variables into roughly one of these ranges.

- **Feature Scaling** involves dividing the input values by the range(the max - the min) of the input variable, resulting in a new range of just 1.

- **Mean Normalization** involves subtracting the average value for an input variable from the values for that input variable resulting in a new average value for the input variable of just zere.

**x_i := (x_i - u_i) / s_i (where s_i: max-min or standard deviation)**


### Polynominal Regression

h_θ(x) = θ_0 + (θ_1 * x_1) + (θ_2 * x_1^2) + (θ_3 * x_1^3)

we create: x_2 = x_1^2, x_3 = x_1^3







