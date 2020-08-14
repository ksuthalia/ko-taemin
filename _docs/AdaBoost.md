---
title: AdaBoost
category: Machine Learning
order: 1
---

## AdaBoost

- Using **Decision Trees** and **Random Forest** to explain the tree main concepts behind AdaBoost!


In a **Random Forest**, each time you make a tree, you make a *full sized tree*. Some trees might be bigger than others, but there is no predetermined maximum depth.

In contrast, in a **Forest of Trees** made with **AdaBoost**, the trees are usually just a **node** and two **leaves**. A trees are usually just a **node** and two **leaves** is called a **stump**. So this is really a **Forest of Stumps** rather than trees. **Stumps** are not great at making accurate classification. Because a **Stump** can only use one variable to make a decision. Thus, **Stumps** are technically "weak learners". Howerver, that's the way **AdaBoost** likes it, and it's one of the reasons why they are so commonly combined.

In a **Random Forest**, each tree has an *equal* vote on the final classification. In contrast, in a **Forest of Stumps** made with **AdaBoost**, some stumps get *more* say in the *final* classification than others.

Lastly, in a **Random Forest**, each decision tree is made independently of the others. In other words, it doesn't matter if which tree was made first or later. In contrast, in a **Forest of Stumps** made with **AdaBoost**, **order is important**.

The errors that the first stump makes influence how the second stump is made. And the erros that the second stump makes influence how the third stump is made. etc. etc. etc.

Summary:
1. **AdaBoost** combines a lot of "weak learners" to make classifications. The weak learners are almost aways **stumps**
