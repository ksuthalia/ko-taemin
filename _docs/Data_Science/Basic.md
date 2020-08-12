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

---
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

---

### Gradient Descent

we need to estimate the parameters in the hypothesis function.

The gradient descent algorithm is:

θ_j := θ_j − α * (∂/∂θ) *  J(θ_0,θ_1) (simultaneously!!)

**α:** If α is too small, gradint descent can be slow. If α is too big, gradient descent can overshoot the minimum. It may fail to converge, or even diverge.
1. Gradient descent can converge to a local minimum, even with the learning rate α fixed
2. As we approach a local minimum, gradient descent will automatically take smaller steps. So no need to decrease α over time.

>A cost function is something we want to minimize. For example, our cost function might be the sum of squared errors over the training set. Gradient descent is a method for finding the minimum of a function of multiple variables. So we can use gradient descent as a tool to minimize our cost function.




