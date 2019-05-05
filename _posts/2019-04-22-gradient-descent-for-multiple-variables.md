---
layout: post
title: Gradient Descent for Multiple Variables
categories: Machine_Learning
description: Gradient Descent for Multiple Variables
keywords: gradient_descent, mutiple_linear_regression
---


## Hypothesis

$h_{\theta}(x)=\theta^{T} x=\theta_{0} x_{0}+\theta_{1} x_{1}+\theta_{2} x_{2}+\cdots+\theta_{n} x_{n}$, $x_{0}=1$

## Parameters

$\theta=\{\theta_{0}, \theta_{1}, \ldots, \theta_{n}\}$

## Cost function
$J(\theta)=J\left(\theta_{0}, \theta_{1}, \ldots, \theta_{n}\right)=\frac{1}{2 m} \sum_{i=1}^{m}\left(h_{\theta}\left(x^{(i)}\right)-y^{(i)}\right)^{2}$

## Gradient descent

$$\begin{array}{l}
{\text { Repeat }\{ } \\ 
{\quad \theta_{j} :=\theta_{j}-\alpha \frac{\partial}{\partial \theta_{j}} J\left(\theta_{0}, \ldots, \theta_{n}\right)} \\ 
{\text{(simultaneously update for every $j=0, \dots, n$)}} \\
\} 
\end{array}$$


* Previously ($n=1$)

$$\begin{array}{l}
{\text { Repeat }\{ } \\ 
{\theta_{0} :=\theta_{0} \cdot \alpha \frac{1}{m} \sum_{i=1}^{m}\left(h_{\theta}\left(x^{(i)}\right)-y^{(i)}\right)} \\ 
{\theta_{1} :=\theta_{1}-\alpha \frac{1}{m} \sum_{i=1}^{m}\left(h_{\theta}\left(x^{(i)}\right)-y^{(i)}\right) x^{(i)}} \\ 
{\text{(simultaneously update $\theta_{0}$, $\theta_{1}$)}} \\
{\}}
\end{array}$$

* New algorithm ($n \geq 1$)

$$\begin{array}{l}
{\text { Repeat }\{ } \\ 
{\theta_{j} :=\theta_{j}-\alpha \frac{1}{m} \sum_{i=1}^{m}\left(h_{\theta}\left(x^{(i)}\right)-y^{(i)}\right) x_{j}^{(i)}} \\ 
{\text {(simultaneously update } \theta_{j} \text { for } j=0, \dots, n \text {)}} \\ 
{\}}
\end{array}$$

## Python code

```python
def computeCost(X, y, theta):
  inner = np.power(((X * theta.T) - y), 2) 
  return np.sum(inner) / (2 * len(X))
```

## Reference
* [Multivariate Linear Regression][1]

[1]: https://medium.com/@qempsil0914/machine-learning-notes-week2-multivariate-linear-regression-mse-gradient-descent-normal-e15785f771bd