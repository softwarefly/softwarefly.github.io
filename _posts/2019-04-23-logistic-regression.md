---
layout: post
title: Logistic Regression
categories: Machine_Learning
description: Logistic Regression
keywords: logistic_regression
---


## Hypothesis function

Since the label type is different from Regression Problem, we should use another hypothesis for solving Classification Problem. Here, we are going to introduce a popular one — Logistic Regression.

**Logistic Regression** is also called a sigmoid function, which maps real numbers into probabilities, range in $[0, 1]$. Hence, the value of sigmoid function means **how certain the data belongs to a category**. The formula is defined as the following picture.

* Note that y represents the label, $y=1$ is the goal label and $y=0$ is the other label, and in sigmoid function, we always concern about the goal label.
* In most cases, we take 0.5 as the threshold of probability. If $h(x) \geq 0.5$, we predict the data belongs to label 1, while $h(x) < 0.5$, we predict the data belongs to label 0.
* Sigmoid Function $h_{\theta}(x)$: represents the probability of $y=1$
$$h_{\theta}(x)=g(z)=\frac{1}{1+e^{-z}} \quad \left(z=\theta_{0}+\theta_{1} x_{1}+\ldots+\theta_{n} x_{n}=\theta^{T} x\right)$$

![](/images/posts/ml/sigmoid-function.jpg)

## Cost function

We learnt about the cost function $J(θ)$ in the Linear regression, the cost function represents optimization objective i.e. we create a cost function and minimize it so that we can develop an accurate model with minimum error.

$$J(\theta)=\frac{1}{2m} \sum_{i=1}^{m}\left(h_{\theta}\left(x^{(i)}\right)-y^{(i)}\right)^{2}$$

If we try to use the cost function of the linear regression in `Logistic Regression` then it would be of no use as it would end up being a **non-convex** function with many local minimums, in which it would be very **difficult** to **minimize the cost value** and find the global minimum.

![](/images/posts/ml/non-convex.jpg)

We will use another error function called [**Cross-Entropy or log loss**](http://neuralnetworksanddeeplearning.com/chap3.html#the_cross-entropy_cost_function).

$$J(\theta)=\frac{1}{m} \sum_{i=1}^{m} \operatorname{cost}\left(h_{\theta}\left(x^{(i)}\right), y^{(i)}\right), \quad \operatorname{cost}\left(h_{\theta}(x), y\right)=\left\{\begin{array}{cc}{-\log \left(h_{\theta}(x)\right)} & {\text { if } y=1} \\ {-\log \left(1-h_{\theta}(x)\right)} & {\text { if } y=0}\end{array}\right.$$

![](/images/posts/ml/cross-entropy.jpg)

$\operatorname{cost}\left(h_{\theta}(x), y\right)=-y \times \log \left(h_{\theta}(x)\right)-(1-y) \times \log \left(1-h_{\theta}(x)\right)$

$$\begin{align}
J(\theta) &=\frac{1}{m} \sum_{i=1}^{m}\left[-y^{(i)} \log \left(h_{\theta}\left(x^{(i)}\right)\right)-\left(1-y^{(i)}\right) \log \left(1-h_{\theta}\left(x^{(i)}\right)\right)\right] \\
& =-\frac{1}{m} \sum_{i=1}^{m}\left[y^{(i)} \log \left(h_{\theta}\left(x^{(i)}\right)\right)+\left(1-y^{(i)}\right) \log \left(1-h_{\theta}\left(x^{(i)}\right)\right)\right] 
\end{align}$$

```python
import numpy as np
def cost(theta, X, y):
  theta = np.matrix(theta)
  X = np.matrix(X)
  y = np.matrix(y)
  first = np.multiply(-y, np.log(sigmoid(X* theta.T)))
  second = np.multiply((1 - y), np.log(1 - sigmoid(X* theta.T)))
  return np.sum(first - second) / (len(X))
```

## Gradient descent

$$\begin{array}{l}
{\text { Repeat }\left\{\theta_{j} :=\theta_{j}-\alpha \frac{\partial}{\partial \theta_{j}} J(\theta)\right.} \\ 
{\text { (simultaneously update all } \theta_{j} )} \\ 
{\}}
\end{array}$$

$$\begin{array}{l}
{\text { Repeat }\left\{\theta_{j} :=\theta_{j}-\alpha \frac{1}{m} \sum_{i=1}^{m}\left(h_{\theta}\left({x}^{(i)}\right)-{y}^{(i)}\right) {x}_{j}^{(i)}\right.} \\ 
{\text { (simultaneously update all } \theta_{j} )} \\ 
{\}}
\end{array}$$

**Proof:**

$$J(\theta)=-\frac{1}{m} \sum_{i=1}^{m}\left[y^{(i)} \log \left(h_{\theta}\left(x^{(i)}\right)\right)+\left(1-y^{(i)}\right) \log \left(1-h_{\theta}\left(x^{(i)}\right)\right)\right]$$
$$where, h_{\theta}\left(x^{(i)}\right)=\frac{1}{1+e^{-\theta^{T} x^{(i)}}}$$

$$\begin{align} 
& y^{(i)} \log \left(h_{\theta}\left(x^{(i)}\right)\right)+\left(1-y^{(i)}\right) \log \left(1-h_{\theta}\left(x^{(i)}\right)\right) \\
= & y^{(i)} \log \left(\frac{1}{1+e^{-\theta^{T} x^{(i)}}}\right)+\left(1-y^{(i)}\right) \log \left(1-\frac{1}{1+e^{-\theta^{T} x^{(i)}}}\right) \\
= & -y^{(i)} \log \left(1+e^{-\theta^{T} x^{(i)}}\right)-\left(1-y^{(i)}\right) \log \left(1+e^{\theta^{T} x^{(i)}}\right)
\end{align}$$

Thus,

$$\begin{align} 
\frac{\partial}{\partial \theta_{j}} J(\theta) & =\frac{\partial}{\partial \theta_{j}}\left[-\frac{1}{m} \sum_{i=1}^{m}\left[-y^{(i)} \log \left(1+e^{-\theta^{T} x^{(i)}}\right)-\left(1-y^{(i)}\right) \log \left(1+e^{\theta^{T} x^{(i)}}\right)\right]\right] \\
& =-\frac{1}{m} \sum_{i=1}^{m}\left[-y^{(i)} \frac{-x_{j}^{(i)} e^{-\theta^{T} x^{(i)}}}{1+e^{-\theta^{T} x^{(i)}}}-\left(1-y^{(i)}\right) \frac{x_{j}^{(i)} e^{\theta^{T} x^{(i)}}}{1+e^{\theta^{T} x^{(i)}}}\right] \\
& =-\frac{1}{m} \sum_{i=1}^{m} \left[y^{(i)} \frac{x_{j}^{(i)}}{1+e^{\theta_{x}(i)}}-\left(1-y^{(i)}\right) \frac{x_{j}^{(i)} e^{\theta^{T} x^{(i)}}}{1+e^{\theta^{T} x^{(i)}}} \right] \\
& =-\frac{1}{m} \sum_{i=1}^{m} \frac{y^{(i)} x_{j}^{(i)}-x_{j}^{(i)} e^{\theta^{T} x^{(i)}}+y^{(i)} x_{j}^{(i)} e^{\theta^{T} x^{(i)}}}{1+e^{\theta^{T} x^{(i)}}} \\
& =-\frac{1}{m} \sum_{i=1}^{m} \frac{y^{(i)}\left(1+e^{\theta^{T} x^{(i)}}\right)-e^{\theta^{T} x^{(i)}}}{1+e^{\theta^{T} x^{(i)}}} x_{j}^{(i)} \\
& =-\frac{1}{m} \sum_{i=1}^{m}\left(y^{(i)}-\frac{e^{\theta^{T} x^{(i)}}}{1+e^{\theta^{T} x^{(i)}}}\right) x_{j}^{(i)} \\
& =-\frac{1}{m} \sum_{i=1}^{m}\left(y^{(i)}-\frac{1}{1+e^{-\theta^{T} x^{(i)}}}\right) x_{j}^{(i)} \\
& =-\frac{1}{m} \sum_{i=1}^{m}\left[y^{(i)}-h_{\theta}\left(x^{(i)}\right)\right] x_{j}^{(i)} \\
& =\frac{1}{m} \sum_{i=1}^{m}\left[h_{\theta}\left(x^{(i)}\right)-y^{(i)}\right] x_{j}^{(i)}
\end{align}$$

## Reference

* [Logistic Regression][1]
* [Classification Problem, Logistic Regression and Gradient Descent][2]

[1]: https://medium.com/@k_dasaprakash/logistic-regression-5b371cc0824f
[2]: https://medium.com/@qempsil0914/courseras-machine-learning-notes-week3-classification-problem-logistic-regression-and-d5792753f8d6

