---
title: Logistic Regression
category: Supervised Learning
order: 1
---

Supervised Learning (Continuous Variable Prediction)

Logistic Regression



### - Classification and Representation

The classification problem is just like the regression problem, except that the values we now want to predict take on only small number of discrete values.

The binary classification problem in which y can take on only two values: 0 and 1


### - Hypothesis Representation

Sigmoid Function (Logistic Function)

0 ≤ h_θ(x) ≤ 1

h_θ(x) = g(θ^T * x)

z = θ^T * x

g(z) = 1 / (1 + e^-z)

**h_θ(x) will give us the probability that our output is 1. => h_θ(x) = 0.7 gives us a probability of 70% that our output is 1**

h_θ(x) = P(y = 1 / x;θ ) = 1 - P(y = 0 / x;θ)
P(y = 1 / x;θ ) + P(y = 0 / x;θ) = 1

### - Decision Boundary

The Decision Boundary is the line that seperates the area where y = 0 and where y = 1.

h_θ(x) ≥ 0.5 -> y = 1
h_θ(x) < 0.5 -> y = 0

g(z) ≥ 0.5 when z >= 0

z = θ^T * x ≥ 0 -> y = 1
z = θ^T * x < 0 -> y = 0


### - Cost Function of Logistic Regression

J(θ) = 1/m * sum( Cost( h_θ(x^(i)), y^(i) ) )
Cost( h_θ(x^(i)), y^(i) )  = -log(h_θ(x)) if y = 1
Cost( h_θ(x^(i)), y^(i) )  = -log(1 - h_θ(x)) if y = 0

Cost( h_θ(x), y ) -> ∞ if y = 0 and h_θ(x) -> 1
Cost( h_θ(x), y ) -> ∞ if y = 1 and h_θ(x) -> 0

Cost( h_θ(x), y ) = -y * log(h_θ(x)) - (1 - y) * log(1 - h_θ(x))

J(θ) = - (1/m) * sum( y * log(h_θ(x)) + (1 - y) * log(1 - h_θ(x)) )


### - Gradient Descent

θ_j := θ_j − α * (∂/∂θ_j) * J(θ)

θ_j := θ_j − α/m * sum( (h_θ(x^(i)) - y^(i)) * x_j^(i) ) 


### Multiclass Classification: One-vs-all (or one-vs-rest)

y ∈ {0,1...,n}
h_θ^(0)(x) = P(y = 0 / x;θ)
h_θ^(1)(x) = P(y = 1 / x;θ)
h_θ^(2)(x) = P(y = 2 / x;θ)
...
h_θ^(n)(x) = P(y = n / x;θ)


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


### Regularized Regression

**Penalty:** ∑θ_j^2

**Modified Cost Function (linear Regression):** ( (1/2m) * sum(h_θ(x^(i)) - y^(i))^2 ) + ( λ * ∑θ_j^2 )

**Gradient Descent(linear):** (we have to seperate θ_0 and θ_rest, we don't want to penalize θ_0)
- θ_0 := θ_0 − α/m * sum( (h_θ(x^(i)) - y^(i)) * x_0^(i) ) 
- θ_j := θ_j − α * ( (1/m) * sum( (h_θ(x^(i)) - y^(i)) * x_j^(i) ) + (λ/m) * θ_j )  ,j ∈ {1,2,...,n}

**Normal Equation:** θ = ( (X^T * X) + (λ * L))^-1 * X^T * y   ,L = I

**Modified Cost Function (logistic Regression):** - (1/m) * sum( y * log(h_θ(x)) + (1 - y) * log(1 - h_θ(x)) ) + ( (λ/m) * ∑θ_j^2 )

**Gradient Descent(logistic):** (we have to seperate θ_0 and θ_rest, we don't want to penalize θ_0)
- θ_0 := θ_0 − α/m * sum( (h_θ(x^(i)) - y^(i)) * x_0^(i) ) 
- θ_j := θ_j − α * ( (1/m) * sum( (h_θ(x^(i)) - y^(i)) * x_j^(i) ) + (λ/m) * θ_j )  ,j ∈ {1,2,...,n}






