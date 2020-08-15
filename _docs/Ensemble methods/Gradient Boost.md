---
title: Gradient Boost
category: Ensemble Methods
order: 2
---

Gradient Boost Part 1: Regression Main Ideas

StatQuest: https://www.youtube.com/watch?v=3CC4N4z3GJc&t=44s

## Gradient Boost

When **Gradient Boost** is used to predict a **continuous** value, like weight, we say that we are using **Gradient Boost** for **Regression**.

Using **Gradient Boost** for **Regression** for **Regression** is different from doing **Linear Regression**, so while the two methods are related, don't get them confused with each other.

### Compare and Contrast AdaBoost and Gradient Boost

**Gradient Boost** starts by making a single leaf, instead of a tree or stump. This leaf represent an initial guess for the Weights(y) of all of the samples. When trying to predict a continuous value like Weight, the first geuss is the average value. Then **Gradient Boost** builds a tree. Like **AdaBoost**, this tree is based on the errors made by the previous tree. But unlike **AdaBoost**, this tree is usually larger than a stump. That said, **Gradient Boost** still restricts the size of the tree.
In practice, people often set the maximum number of leaves to be between 8 and 32. Thus like **AdaBoost**, **Gradient Boost** builds fixed sized trees based on the previous tree's errors, but unlike **AdaBoost**, each tree can be larger than a stump. Also like **AdaBoost**, **Gradient Boost** scales the trees. However, **Gradient Boost** scales all trees by the same amount.
**Gradient Boost** contnues to build trees in this fashion until it has made the number of trees you asked for, or additional trees fail to imporve the fit.

**Pseudo Residual**: this term is for **Gradient Boost**. Residuel is from **Linear Regression**.

> Residuel = Observed - Predicted

We have to do a little math(compute:Pseudo Residual)

If we get the same predicted value as the observed value => The Model fits the **Training Data too well**. In other words, we have low **Bias**, but probably very high **Variance**.

**Gradient Boost** deals with this problem by using a **Learning Rate** to scale the contribution from the new tree. The **Learning Rate** is a value between 0 and 1.

Empirical evidence shows that taking lots of small steps in the right direction results in better predictions with a **Testing Dataset** i.e. lower **Variance**.

In practice, the trees can be different each time.

---
