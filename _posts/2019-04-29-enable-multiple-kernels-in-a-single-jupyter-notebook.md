---
layout: post
title: Enable Multiple Kernels in a Single Jupyter Notebook
categories: Deployment
description: Enable Multiple Kernels in a Single Jupyter Notebook
keywords: Anaconda, Jupyter_Notebook
---

# Enable Multiple Kernels in a Single Jupyter Notebook

I don’t know if you know this, but I came to know about it quite recently, and it saved me a from installing lot of redundant libraries again and again every-time.

So because Python is my bread and butter, I always create a virtual environment for each and every project like most of the Python users. Now how can a Data Scientist ever be kept away from Jupyter Notebooks (Forgive me if someone got offended for this generalized statement). So every-time I used to do

```sh
(some-env)$ conda install jupyter
or 
(some-env)$ pip install jupyter
```

And it used to install all the dependent libraries again and again into the environment. Actually which is totally unnecessary. Instead what we can do is

## First method

```sh
(some-env)$ conda install ipykernel
(some-env)$ python -m ipykernel install --user --name <some-env> (--display-name "<name-of-your-kernel>")
```

That’s it. And now you can run jupyter notebooks from anywhere and you get the choice of environment like this


Just to clarify `tf2` there is a Python virtual environment with  `tensorflow-gpu==2.0.0-alpha0` SDK for python is installed, hence the name.

<div align="center">
<img src = "/images/posts/deployment/jupyter-kernel.png" width = "1000"/>
<figcaption  class="imageCaption">Multiple Kernel</figcaption>
</div>

## Second method

```sh
$ conda install nb_conda
or
$ conda install nb_conda_kernels
```

`nb_conda` is a notebook extention that allows you to manage conda environments from your notebook. It also allows you to switch kernels directly from the Kernal menu.

Conda tab in jupyter notebook allows you to manage your environments right from within your notebook.

<div align="left">
<img src = "/images/posts/deployment/conda-tab.png" />
</div>

You can also select which kernel to run a notebook in by using the Change kernel option in Kernel menu.

<div align="left">
<img src = "/images/posts/deployment/change-kernel.png" />
</div>

I hope this helps a few of you folks.

Until next time, Godspeed!!


## Reference

* [Enable multiple kernels in Jupyter Notebooks][1]
* [Different virtualenv's on one Jupyter notebook][2]

[1]: https://medium.com/@ace139/enable-multiple-kernels-in-jupyter-notebooks-6098c738fe72
[2]: https://stackoverflow.com/questions/47570793/different-virtualenvs-on-one-jupyter-notebook