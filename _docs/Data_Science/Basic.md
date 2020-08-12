---
title: Basic
category: Basic
order: 1
---

> Supervised Learning



> Umsupervised Learning


### Model

> h : X → Y , so that h(x) is a “good” predictor for the corresponding value of y

**Notation:**
a list of m training examples (x^(i) ,y^(i)); i = 1, . . . , m

(x^(i),y^(i));i=1,...,m  ==> is called a training set. 



## Cost Function


> J(θ_0,θ_1) = 1/2m * sum(y^-y)^2 = 1/2m * sum(h(x)-y)^2

why 1/2?: as convenience for the computation of the gradient descent

