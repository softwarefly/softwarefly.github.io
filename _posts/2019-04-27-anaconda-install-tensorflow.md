---
layout: post
title: Anaconda Install TensorFlow
categories: Deployment
description: Anaconda Install TensorFlow
keywords: Anaconda, TensorFlow
---

## Change mirror sites（[tsinghua](https://mirror.tuna.tsinghua.edu.cn/help/anaconda/)）

```sh
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
conda config --set show_channel_urls yes
```

## Install Tensorflow with GPU support

Create virtual environment with Anaconda, I names it tf36 for TensorFlow and python 3.6

```sh
conda create --name tf36 python=3.6
source activate tf36
```

Activate and deactivate virtual environmnet

```sh
conda activate tf36
conda deactivate
```

Install TensorFlow (GPU version) with conda

```sh
conda install tensorflow-gpu (GPU version)
conda install tensorflow

conda install cudatoolkit=10 cudnn=7.3

pip install tf-nightly-2.0-preview
pip install tf-nightly-gpu-2.0-preview

pip install tensorflow==2.0.0-alpha0
pip install tensorflow-gpu==2.0.0-alpha0
```

Check TensotFlow installation with

```sh
python
```

```sh
>>> import tensorflow as tf
>>> tf.Session(config=tf.ConfigProto(log_device_placement=True))
>>> print(tf.__version__)
```

Install other packages

```sh
conda install keras
conda install jupyter
conda install matplotlib
conda install pandas
conda install scikit-image
conda install scikit-learn
```

Some basic operation of conda

```sh
conda env list             //show all virtual environment
conda -V                   //show version of Anaconda
conda list -n XXX          //show the installed packages in virtualenv XXX
conda remove -n XXX --all   //remove virtualenv XXX
```

## Reference

* [Install Conda TensorFlow-gpu and Keras on Ubuntu 18.04][1]
* [Test Drive TensorFlow 2.0 Alpha][2]

[1]: https://medium.com/@naomi.fridman/install-conda-tensorflow-gpu-and-keras-on-ubuntu-18-04-1b403e740e25
[2]: https://medium.com/tensorflow/test-drive-tensorflow-2-0-alpha-b6dd1e522b01







