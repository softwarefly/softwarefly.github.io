---
layout: post
title: Overfitting and Regularization
categories: Machine_Learning
description: Overfitting and Regularization
keywords: overfitting, regularization
---

## Overfitting

> The learned model works well for training data but terrible for testing data (unknown data). In other words, the model has little training error but has huge perdition error.

When overfitting occurs, we get an over complex model with too many features. One way to avoid it is to apply Regularization and then we can get a better model with proper features.

## Regularization

> It’s a technique applied to Cost Function $J(\theta)$ in order to avoid Overfitting.

The core idea in Regularization is to keep more important features and ignore unimportant ones. The importance of feature is measured by the value of its parameter $\theta_{j}$.

In linear regression, we modify its cost function by adding regularization term. The value of $\theta_{j}$ is controlled by regularization parameter $\lambda$. Note that $m$ is the number of data and $n$ is the number of features (parameters).

<div align="center">
<img src = "/images/posts/ml/regularization.jpg" width = "600"/>
</div>

For instance, if we want to get a better model instead of the overfitting one. Obviously, we don’t need features $x^3$ and $x^4$ since they are unimportant. The procedure describes below.

<div align="center">
<img src = "/images/posts/ml/overfitting1.jpg" width = "600" />
</div>

First, we modify the Cost Function $J(\theta)$ by adding regularization. Second, apply gradient descent in order to minimize $J(\theta)$ and get the values of $\theta_3$ and $\theta_4$. After the minimize procedure, the values of $\theta_3$ and $\theta_4$ must be near to zero if $\lambda=1000$.

<div align="center">
<img src = "/images/posts/ml/regularization-instance1.jpg" width = "450" />
</div>

Remember, the value of $J(\theta)$ represents training error and this value must be positive ($\ge 0$). The parameter $\lambda=1000$ has significant effect on $J(\theta)$, therefore, $\theta_3$ and $\theta_4$ must be near to zero (e.g 0.000001) so as to eliminate error value.

<div align="center">
<img src = "/images/posts/ml/regularization-instance2.jpg" width = "600" />
</div>

## Regularization Parameter $\lambda$

* If $\lambda$ is too large, then all the values of $\theta$ may be near to zero and this may cause Underfitting. In other words, this model has both large training error and large prediction error. (Note that the regularization term starts from $\theta_1$)

* If $\lambda$ is zero or too small, its effect on parameters $\theta$ is little. This may cause Overfitting.

<div align="center">
<img src = "/images/posts/ml/overfitting2.jpg" width = "600" />
</div>

To sum up, there are two advantages of using regularization.

* The prediction error of the regularized model is lesser, that is, it works well in testing data (green points).

* The regularization model is simpler since it has less features (parameters).

<div align="center">
<img src = "/images/posts/ml/regularization-overfitting-res1.jpg" width = "500" />
<img src = "/images/posts/ml/regularization-overfitting-res2.jpg" width = "500" />
</div>

So far, we have discussed the concept of regularization. Next, we will show how to minimize regularized cost function by using gradient descent.

## Recall: Gradient Descent

$$\begin{array}{l}
{\text {Repeat until converge }\{ } \\ 
{\theta_{j} :=\theta_{j}-\alpha \frac{\partial}{\partial \theta_{j}} J(\theta)} \\ 
\} \text {where $j$ represents the feature index number}
\end{array}$$

## Regularized linear regression

$h_{\theta}(x)=\theta^{T} x=\theta_{0} x_{0}+\theta_{1} x_{1}+\theta_{2} x_{2}+\cdots+\theta_{n} x_{n}$, $x_{0}=1$

<div align="left">
<img src = "/images/posts/ml/regularized-linear-regression.jpg" width = "600" />
</div>

## Regularized logistic regression

$h_{\theta}\left(x^{(i)}\right)=\frac{1}{1+e^{-\theta^{T} x^{(i)}}}$

<div align="left">
<img src = "/images/posts/ml/regularized-logistic-regression.jpg" width = "600" />
</div>

## Reference

* [Coursera’s Machine Learning Notes — Week3, Overfitting and Regularization][1]
* [Andrew Ng’s Machine Learning Course in Python (Regularized Logistic Regression)][2]

[1]: https://medium.com/@qempsil0914/courseras-machine-learning-notes-week3-overfitting-and-regularization-partii-3e3f3f36a287
[2]: https://towardsdatascience.com/andrew-ngs-machine-learning-course-in-python-regularized-logistic-regression-lasso-regression-721f311130fb