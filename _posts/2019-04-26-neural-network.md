---
layout: post
title: Neural Network
categories: Machine_Learning
description: Neural Network
keywords: neural_network
---

<div align="left">
<img src = "/images/posts/ml/neural-network1.jpg" width = "240" />
<img src = "/images/posts/ml/neural-network2.jpg" width = "390" />
</div>

$$C_{0}=\left(a^{(L)}-y\right)^{2}$$

$$z^{(L)}=w^{(L)} a^{(L-1)}+b^{(L)}$$

$$a^{(L)}=\sigma\left(z^{(L)}\right)$$

---

$$\frac{\partial C_{0}}{\partial w^{(L)}}=\frac{\partial z^{(L)}}{\partial w^{(L)}} \frac{\partial a^{(L)}}{\partial z^{(L)}} \frac{\partial C_{0}}{\partial a^{(L)}}$$

---

$$\frac{\partial C_{0}}{\partial a^{(L)}}=2\left(a^{(L)}-y\right)$$

$$\frac{\partial a^{(L)}}{\partial z^{(L)}}=\sigma^{\prime}\left(z^{(L)}\right)$$

$$\frac{\partial z^{(L)}}{\partial w^{(L)}}=a^{(L-1)}$$

---

$$\frac{\partial C_{0}}{\partial w^{(L)}}=\frac{\partial z^{(L)}}{\partial w^{(L)}} \frac{\partial a^{(L)}}{\partial z^{(L)}} \frac{\partial C_{0}}{\partial a^{(L)}}=a^{(L-1)} \sigma^{\prime}\left(z^{(L)}\right) 2\left(a^{(L)}-y\right)$$

$$\frac{\partial C}{\partial w^{(L)}}=\frac{1}{n} \sum_{k=0}^{n-1} \frac{\partial C_{k}}{\partial w^{(L)}} \text{(average of all training examples, $n$ is the number)}$$  

$$\frac{\partial C_{0}}{\partial b^{(L)}}=\frac{\partial z^{(L)}}{\partial b^{(L)}} \frac{\partial a^{(L)}}{\partial z^{(L)}} \frac{\partial C_{0}}{\partial a^{(L)}}=\quad 1 \sigma^{\prime}\left(z^{(L)}\right) 2\left(a^{(L)}-y\right)$$

$$\frac{\partial C_{0}}{\partial a^{(L-1)}}=\frac{\partial z^{(L)}}{\partial a^{(L-1)}} \frac{\partial a^{(L)}}{\partial z^{(L)}} \frac{\partial C_{0}}{\partial a^{(L)}}=w^{(L)} \sigma^{\prime}\left(z^{(L)}\right) 2\left(a^{(L)}-y\right)$$

---
<div align="left">
<img src = "/images/posts/ml/neural-network3.jpg" width = "304" />
<img src = "/images/posts/ml/neural-network4.jpg" width = "409" />
</div>

$$z_{j}^{(L)}=\omega_{j 0}^{(L)} a_{0}^{(L-1)}+w_{j 1}^{(L)} a_{1}^{(L-1)}+\dots+w_{j k}^{(L)} a_{k}^{(L-1)}+\dots+b_{j}^{(L)}$$

$$a_{j}^{(L)}=\sigma\left(z_{j}^{(L)}\right)$$

$$C_{0}=\sum_{j=0}^{n_{L}-1}\left(a_{j}^{(L)}-y_{j}\right)^{2}$$

---

$$\frac{\partial C_{0}}{\partial w^{(L)}}=\frac{\partial z^{(L)}}{\partial w^{(L)}} \frac{\partial a^{(L)}}{\partial z^{(L)}} \frac{\partial C_{0}}{\partial a^{(L)}} \rightarrow \frac{\partial C_{0}}{\partial w_{j k}^{(L)}}=\frac{\partial z_{j}^{(L)}}{\partial w_{j k}^{(L)}} \frac{\partial a_{j}^{(L)}}{\partial z_{j}^{(L)}} \frac{\partial C_{0}}{\partial a_{j}^{(L)}}$$

$$\frac{\partial C_{0}}{\partial a^{(L-1)}}=\frac{\partial z^{(L)}}{\partial a^{(L-1)}} \frac{\partial a^{(L)}}{\partial z^{(L)}} \frac{\partial C_{0}}{\partial a^{(L)}}= \rightarrow \frac{\partial C_{0}}{\partial a_{k}^{(L-1)}}=\sum_{j=0}^{n_{L}-1} \frac{\partial z_{j}^{(L)}}{\partial a_{k}^{(L-1)}} \frac{\partial a_{j}^{(L)}}{\partial z_{j}^{(L)}} \frac{\partial C_{0}}{\partial a_{j}^{(L)}} \text{(sum over layer $L$)}$$ 

<div align="left">
<img src = "/images/posts/ml/neural-network5.jpg" width = "363" />
</div>
