# Introduction
In this repo, we will show an example on estimating the claim frequency using the CART algorithm with R. Before tackling the ensemble methods, let’s set the up the basis explaining how the algorithm works. And first thing first, a real tree looks like this:
![Example of real tree](https://github.com/william-tiritilli/Regression-Tree/assets/46381506/b24b829e-bdb7-4499-94ba-d08a22db9ea0)

Hope you got the reference ;-). More explantions below.

# Explanation
In a nutshell, the Classification And Regression Tree algorithm, aka CART, (Breiman, 1984) works by partitioning the feature space into a number of smaller (non-overlapping) regions with similar response values usint a set of splitting rules.
We say “Binary Recursive Partitioning”, because the objective is that at each node, the algorithm finds the best feature xi to partition the data into two regions R1 and R2, such as the overall error between the actual response yi an the predicted constant ci is minimized:

![image](https://github.com/william-tiritilli/Regression-Tree/assets/46381506/9fe1c59c-5b45-4ee4-96a5-41f936ee8033)

In classification, we want to minimize the Gini index. In regression, the most common loss function is the SSE. However, as we are dealing with a claim count, we want to minimize the Poisson Deviance:

![image](https://github.com/william-tiritilli/Regression-Tree/assets/46381506/3e5b3a54-35d9-49a0-a4b7-756f338198f6)

More explanation about this process implying hyperparameters tuning is available in the power point. 

# Main Results
We show here the final tree after pruning, composed of 7 terminal nodes (aka “leaves”).

![image](https://github.com/william-tiritilli/Regression-Tree/assets/46381506/f6da669b-0765-4845-941c-a5d875c042ab)

The model estimates that a driver with less than 2 years of experience and less than 34 years old, has a probability of claim of 29%.

![image](https://github.com/william-tiritilli/Regression-Tree/assets/46381506/037d654e-4953-441f-be75-d9deb0325424)

The variable [yrs.licenced] is the “most important” in the sense that it reduces the loss function the most at each split.

# Conclusion
Trees are very easy to interpret. However, they suffer from high variance and are generally outperformed by Ensemble methods like Random Forest or GBM. 






