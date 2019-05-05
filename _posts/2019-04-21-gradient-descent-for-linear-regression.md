---
layout: post
title: Gradient Descent For Linear Regression
categories: Machine_Learning
description: Gradient Descent For Linear Regression
keywords: gradient_descent, linear_regression
---


## Gradient descent algorithm

$$\begin{array}{l}
{\text {Repeat until convergence }\{ } \\ 
{\theta_{j} :=\theta_{j}-\alpha \frac{\partial}{\partial \theta_{j}} J\left(\theta_{0}, \theta_{1}\right)} \\ 
{\text { (for } j=1 \text { and } j=0 )} \\ 
\}  
\end{array}$$


## Linear regression model

**Hypothesis:** ${h_{\theta}(x)=\theta_{0}+\theta_{1} x}$ 

**Cost function:** ${J(\theta)=\frac{1}{2 m} \sum_{i=1}^{m}\left(h_{\theta}\left(x^{(i)}\right)-y^{(i)}\right)^{2}}$

## Gradient descent for linear regression

$\frac{\partial}{\partial \theta_{j}} J\left(\theta_{0}, \theta_{1}\right)=\frac{\partial}{\partial \theta_{j}} \frac{1}{2 m} \sum_{i=1}^{m}\left(h_{\theta}\left(x^{(i)}\right)-y^{(i)}\right)^{2}$

$j=0$, $\frac{\partial}{\partial \theta_{0}} J\left(\theta_{0}, \theta_{1}\right)=\frac{1}{m} \sum_{i=1}^{m}\left(h_{\theta}\left(x^{(i)}\right)-y^{(i)}\right)$

$j=1$, $\frac{\partial}{\partial \theta_{1}} J\left(\theta_{0}, \theta_{1}\right)=\frac{1}{m} \sum_{i=1}^{m}\left(\left(h_{\theta}\left(x^{(i)}\right)-y^{(i)}\right) \cdot x^{(i)}\right)$

$$\begin{array}{l}
{\text {Repeat }\{ } \\ 
{\theta_{0} :=\theta_{0}-a \frac{1}{m} \sum_{i=1}^{m}\left(h_{\theta}\left(x^{(i)}\right)-y^{(i)}\right)} \\ 
{\theta_{1} :=\theta_{1}-a \frac{1}{m} \sum_{i=1}^{m}\left(\left(h_{\theta}\left(x^{(i)}\right)-y^{(i)}\right) \cdot x^{(i)}\right)} \\ 
{\}}
\end{array}$$