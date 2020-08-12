---
title: Basic
category: Basic
order: 1
---

## Supervised Learning

- [x] Linear Regression


## Umsupervised Learning



## Basic

- [x] Cost Function
- [ ] Gradient Descent


### Representation Model

> h : X → Y , so that h(x) is a “good” predictor for the corresponding value of y

**Notation:**
a list of m training examples (x^(i) ,y^(i)); i = 1, . . . , m

(x^(i),y^(i));i=1,...,m  ==> is called a training set. 



### Cost Function

**Goal: choose θ_0 and θ_1 so that h_θ(x) is close to y for our training examples(x,y)**

> J(θ_0,θ_1) = 1/2m * sum(y_i^-y_i)^2 = 1/2m * sum(h_θ(x_i)-y_i)^2

min(θ_0,θ_1): J(θ_0,θ_1) <== to minimize **Cost Function**

why 1/2?: as convenience for the computation of the gradient descent

We can also plot function of the parameter θ_1 (y: J(θ_1), x: θ_1)


### Gradient Descent

we need to estimate the parameters in the hypothesis function.







