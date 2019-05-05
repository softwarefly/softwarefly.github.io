---
layout: post
title: Normal Equation
categories: Machine_Learning
description: Normal Equation
keywords: normal_equation
---

$J\left(\theta_{0}, \theta_{1}, \ldots, \theta_{m}\right)=\frac{1}{2 m} \sum_{i=1}^{m}\left(h_{\theta}\left(x^{(i)}\right)-y^{(i)}\right)^{2}$, $\theta \in \mathbb{R}^{n+1}$

$\frac{\partial}{\partial \theta_{j}} J(\theta)=\cdots=0$ ( for every $j$ )

Solve for $\theta_{0}, \theta_{1}, \ldots, \theta_{n}$

$m$ examples $(x^{(1)}, y^{(1)}), \dots, (x^{(m)}, y^{(m)})$; $n$ features

$$x^{(i)}=\left[ \begin{array}{c}{x_{0}^{(i)}} \\ {x_{1}^{(i)}} \\ {x_{2}^{(i)}} \\ {\vdots} \\ {x_{n}^{(i)}}\end{array}\right] \in \mathbb{R}^{n+1}$$ ,$\quad$ $$X=\left[\begin{array}{c} {(x^{(1)})}^T \\ {(x^{(2)})}^T \\ {\vdots} \\ {(x^{(m)})}^T \end{array}\right]$$ ,$\quad$ $$y=\left[ \begin{array}{c} y^{(1)} \\ y^{(2)} \\ {\vdots} \\ y^{(m)}  \end{array}\right]$$

$\theta=\left(X^{T} X\right)^{-1} X^{T} y$

## Matlab code

```matlab
pinv(X'*X)*X'*y
```

## Python code

```python
import numpy as np 
def normalEqn(X, y):
  theta = np.linalg.inv(X.T@X)@X.T@y #X.T@X 等价于 X.T.dot(X)
  return theta
```

## Proof

> Proof: $\theta=\left(X^{T} X\right)^{-1} X^{T} y$

$J(\theta)=\frac{1}{2 m} \sum_{i=1}^{m}\left(h_{\theta}\left(x^{(i)}\right)-y^{(i)}\right)^{2}$, where, $h_{\theta}(x)=\theta^{T} x=\theta_{0} x_{0}+\theta_{1} x_{1}+\theta_{2} x_{2}+\ldots+\theta_{n} x_{n}$

$J(\theta)=\frac{1}{2}(X \theta-y)^{2}$, $X$: $m \times n$, $\theta$: $n \times 1$, $y$: $m \times 1$

$$\begin{align}  
  J(\theta) &= \frac{1}{2}(X \theta-y)^{T}(X \theta-y) \\  
 &= \frac{1}{2}\left(\theta^{T} X^{T}-y^{T}\right)(X \theta-y)  \\  
 &= \frac{1}{2}\left(\theta^{T} X^{T} X \theta-\theta^{T} X^{T} y-y^{T} X \theta-y^{T} y\right)
\end{align}$$

As $\frac{d A B}{d B}=A^{T}$ and $\frac{d X^{T} A X}{d X}=2 A X$

Thus,

$$\begin{align}  
  \frac{\partial J(\theta)}{\partial \theta} &= \frac{1}{2}\left(2 X^{T} X \theta-X^{T} y-\left(y^{T} X\right)^{T}-0\right) \\  
 &= \frac{1}{2}\left(2 X^{T} X \theta-X^{T} y-X^{T} y-0\right)  \\  
 &= X^{T} X \theta-X^{T} y
\end{align}$$

Set $\frac{\partial J(\theta)}{\partial \theta}=0$

Then, $\theta=\left(X^{T} X\right)^{-1} X^{T} y$



