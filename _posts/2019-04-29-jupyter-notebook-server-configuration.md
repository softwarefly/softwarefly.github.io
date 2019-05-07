---
layout: post
title: Jupyter Notebook Server Configuration
categories: Deployment
description: Jupyter Notebook Server Configuration
keywords: Anaconda, Jupyter_Notebook
---

When you launch Jupyter Notebook, it runs a small web server on the local system.

You can allow access to a notebook directory so that others can view, use, and create notebooks on a single server instance. Jupyter Notebook can be configured for password login, notebook directory, and ports.

## Configure Jupyter notebook to set the directory

Installing `Anaconda` installs jupyter notebook.

```sh
conda install jupyter
```

Generate the default jupyter_notebook_config.py file

```sh
jupyter notebook --generate-confign (--allow-root)
```

This will put the file in the following directory:

```sh
~/.jupyter/jupyter_notebook_config.py
```

You can now edit this config file to make changes.To set the directory from where Jupyter starts and serves notebooks from, find the following line and uncomment it. Add the full path of the directory you want to serve from:

```viml
## The directory to use for notebooks and kernels.
c.NotebookApp.notebook_dir = u'/< Path-to-Notebook_dir> '
```

To set Jupyter Notebook Server to listen to all incoming connections to access the notebook directory, find the following line and uncomment it. You can set the ip to `0.0.0.0` to listen to all connections:

```viml
## The IP address the notebook server will listen on.
c.NotebookApp.ip = '0.0.0.0'
```

Now you can access the notebook directory from another system by entering the IP address of the system running the notebook server, along with the default port 8888. This will allow anyone to connect without any authentication. EXAMPLE: http://ip-address:8888.

## Configure Jupyter notebook to require a shared password for access.

Generate a password to copy into the Jupyter config file.

Open a Python console: 

```sh
python
```

And run the following to generate the hash:

```python
>>> from notebook.auth import passwd
>>> passwd()
```

Copy the entire string that is printed to the console by the above commands and then find the following line, uncomment it and add the hash: 
```viml
##The string should be of the form type:salt:hashed-password.
c.NotebookApp.password = u'hash_from_above_step'
```

To change the port, the Notebook Server will listen, find the following line, uncomment it and add the port number, default is 8888: 
```viml
## The port the notebook server will listen on.
c.NotebookApp.port = 8888
```

You should now be able to access Jupyter by entering the host system's IP address followed by the port number, http://ip_address:port. It should take you to a login page where you can use the password you typed in to create the hash.

## Configuration File

> jupyter_notebook_config.py

```viml
# Set options for certfile, ip, password, and toggle off
# browser auto-opening
c.NotebookApp.certfile = u'/absolute/path/to/your/certificate/mycert.pem'
c.NotebookApp.keyfile = u'/absolute/path/to/your/certificate/mykey.key'
# Set ip to '*' to bind on all interfaces (ips) for the public server
c.NotebookApp.ip = '*'
c.NotebookApp.password = u'sha1:bcd259ccf...<your hashed password here>'
c.NotebookApp.open_browser = False

# It is a good idea to set a known, fixed port for server access
c.NotebookApp.port = 9999
c.IPKernelApp.pylab = 'inline'
```

## Start notebook

```viml
jupyter notebook
```

## Change password

```sh
jupyter-notebook password
```

## Reference

* [Jupyter Notebook Server Configuration][1]
* [Running a notebook server][2]

[1]: https://support.anaconda.com/customer/en/portal/articles/2818686-jupyter-notebook-server-configuration
[2]: https://jupyter-notebook.readthedocs.io/en/stable/public_server.html#using-let-s-encrypt