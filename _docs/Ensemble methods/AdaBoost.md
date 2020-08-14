---
title: AdaBoost
category: Ensemble Methods
order: 1
---

## AdaBoost

StatQuest: https://www.youtube.com/watch?v=LsK-xG1cLYA&t=1087s

- Using **Decision Trees** and **Random Forest** to explain the tree main concepts behind **AdaBoost**!


In a **Random Forest**, each time you make a tree, you make a *full sized tree*. Some trees might be bigger than others, but there is no predetermined maximum depth.

In contrast, in a **Forest of Trees** made with **AdaBoost**, the trees are usually just a **node** and two **leaves**. A trees are usually just a **node** and two **leaves** is called a **stump**. So this is really a **Forest of Stumps** rather than trees. **Stumps** are not great at making accurate classification. Because a **Stump** can only use one variable to make a decision. Thus, **Stumps** are technically "weak learners". Howerver, that's the way **AdaBoost** likes it, and it's one of the reasons why they are so commonly combined.

In a **Random Forest**, each tree has an *equal* vote on the final classification. In contrast, in a **Forest of Stumps** made with **AdaBoost**, some stumps get *more* say in the *final* classification than others.

Lastly, in a **Random Forest**, each decision tree is made independently of the others. In other words, it doesn't matter if which tree was made first or later. In contrast, in a **Forest of Stumps** made with **AdaBoost**, **order is important**.

The errors that the first stump makes influence how the second stump is made. And the erros that the second stump makes influence how the third stump is made. etc. etc. etc.

- Summary:
1. **AdaBoost** combines a lot of "weak learners" to make classifications. The weak learners are almost always **stumps**.
2. Some **stumps** get more say in the classification than others.
3. Each **stump** is made by taking the **previous stump's mistakes** into account.

#### Steps: how to create a Forest of Stumps using AdaBoost

1. The first thing we do is give each sample a **weight** that indicates how important it is to be correctly classified.

2. At the start, all samples get the same weight. (one divied by total number of samples.). That makes the samples **all equally important**. However, after we make the first stump, these weights will change in order to guide how the next stump is created. In other words, we'll talk more about the **Sample Weight** later!

3. Now we need to make the first **stump** in the forest. This is done finding the variable that does the best job classifying the samlples. Because all of the wights are the same, we can ignore them(Sample Weight) right now. For example: to see how well **x_1** classifies the **y(samples)**. And we do the same thing for **x_2, x_3, ...**.

4. We calculate the **Gini Index** for the all stumps. For instance, The **Gini Index for x_3** is the lowest. So this will be the first stump in the forest. Now we need to determine how much say this stump will have in the final classification.(Remember, some stumps get mor say in the final classification than others based on how well it classified the samples.) The **Total Error** for a stump is the sum of the weight associated with  the *incorrectly* classified sampels. Because all of the sample weights add up to 1, **Total Error** will always be between **0**, for a perfect stump, and **1**, for a horrible stump.

5. We use the **Total Error** to determine **Amount of Say** this stump has in the final classification with the following formula:

> Amount of Say = 1/2 * log( (1 - Total Error) / Total Error )

6. We can draw a graph of the **Amount of Say** by plugging in a bunch of numbers between **0** and **1** for **Total Error**. When a stump does a good job, and the **Total Error** is small, then the **Abount of Say** is a relatively large, positive value. If **Total Error = 0** then the **Amount of Say** will be **0**. If **Total Error** is **1** or **0**, then this equation of Amount of Say will freak out.

7. After these steps for all x_n, we know how the **Sample Weights** for the incorrectly classified samples are used to determine the **Amount of Say** each stump gets.

8. Now we need to learn how to **modify the weights** so that the **next stump** will take the errors that the current stump made into account.

9. We will emphasize the need for the next stump to coreectly classify it by increasing its **Sample Weight** and decreasing all of the other **Sample Weights**

10. This is the fomular we will use to increase the **Sample Weight** for the sample that was incorrectly classfied.

> New Sample Weight = sample weight * e^**amount of say**

11. Now we need to decrease the **Sample Weights** for all of the correctly classified samples.

> New Sample Weight = sample weight * e^**-amount of say**

12. This means that the **New Sample Weight** will be just a little smaller than the old one.

13. Now we need to normalize the **New Sample Weights** so that they will add up to 1.

14. Now we can use the modified **Sample Weights** to make the secopnd **stump** in the forest. In theory, we could use the **Sample Weights** to calculate **Weighted Gini Indexes** to determine which variable should split the next stump. Alternatively, instead of using a **Weighted Gini Index**, we can make a new collection of samples that contains duplicate copies of the samples with the largest **Sample Weights**. We continue to pick random numbers and add samples to the new collection until we the new collection is the same size as the original.

15. We do the same steps like before.


We need to talk about how a forest of stumps created by **AdaBoost** makes classifications.









