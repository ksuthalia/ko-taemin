---
title: Basic Regression
category: Supervised Learning
order: 1
---

Supervised Learning (Continuous Variable Prediction)

### Multivariate Linear Regression

h_θ(x) = θ_0 + (θ_1 * x_1) + ... + (θ_n * x_n)

| notation | meaning |
|--|--|
| n | the number of features(j) |
| m | the number of training examples(i) |
| x_j^(i)| value of feature j in the i^th training example |

h_θ(x) = [ θ_0 θ_1 ... θ_n ] * [x_0 + x_1 + ... + x_n]^T = θ^T * x  (<= vectorized)

for the convenience reasons we assume that x_0^(i) = 1

