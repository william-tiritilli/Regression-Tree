# Introduction
In this repo, we will show an example on estimating the claim frequency using the CART algorithm with R. Before tackling the ensemble methods, let’s set the up the basis explaining how the algorithm works. And first thing first, a real tree looks like this:
![Example of real tree](https://github.com/william-tiritilli/Regression-Tree/assets/46381506/b24b829e-bdb7-4499-94ba-d08a22db9ea0)

Hope you got the reference ;-). More explantions below.

# Explanation
In a nutshell, the Classification And Regression Tree algorithm, aka CART, (Breiman, 1984) works by partitioning the feature space into a number of smaller (non-overlapping) regions with similar response values usint a set of splitting rules.
The goal is at each threshold, the minimum sum squared of residuals between the observed value and the predicted value is minimal.
In classification, we want to minimize the Gini index. In regression, other Loss function are candidates. Here, we want to minimize the Poisson Deviance, as we are dealing with a claim count.

![image](https://github.com/william-tiritilli/Regression-Tree/assets/46381506/3e5b3a54-35d9-49a0-a4b7-756f338198f6)

# Main Results
We show here the final tree after pruning, composed of 7 terminal nodes (aka “leaves”).

![image](https://github.com/william-tiritilli/Regression-Tree/assets/46381506/f6da669b-0765-4845-941c-a5d875c042ab)

The model estimates that a driver with less than 2 years of experience and less than 34 years old, has a probability of claim of 29%.

![image](https://github.com/william-tiritilli/Regression-Tree/assets/46381506/037d654e-4953-441f-be75-d9deb0325424)

The variable [yrs.licenced] is the “most important” in the sense that it reduces the loss function the most at each split

# Conclusion
Trees are very easy to interpret. However, they suffer from high variance and are generally outperformed by Ensemble methods like Random Forest or GBM. 






