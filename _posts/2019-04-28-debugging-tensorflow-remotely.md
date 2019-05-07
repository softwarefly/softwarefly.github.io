---
layout: post
title: Debugging TensorFlow Remotely
categories: Deployment
description: Debugging TensorFlow Remotely
keywords: TensorFlow, Pycharm
---

<div align="center">
<img src = "/images/posts/deployment/pycharm.jpg" width = "200"/>
</div>

This is the funny part, how we can set up the remote interpreter so you execute the scripts on your remote machine. Let’s get started, start up PyCharm and create a new Python project.

## Interpreter

Open **“Preferences > Project > Project Interpreter”**. Click on the **“Dotted button”** in the top-right corner and then **“Add”**.

<div align="center">
<img src = "/images/posts/deployment/interpreter-add.png" width = "600"/>
</div>

Click on the **“SSH Interpreter”** radio-button and input your information.

<div align="center">
<img src = "/images/posts/deployment/ssh-interpreter.png" width = "600"/>
</div>

## Deployment

The remote interpreter can not execute a local file, PyCharm have to copy your source files (your project) to a destination folder on your remote server, but this will be done automatically and you don’t need to think about it! While still in the **“Preferences”** pane, open **“Build, Execution, Deployment > Deployment > Options”**. Make sure that **“Create empty directories”** is checked. This way PyCharm will automatically synchronize when you create folders:

<div align="center">
<img src = "/images/posts/deployment/deployment-option.png" width = "600"/>
</div>

Now go back to **“Build, Execution, Deployment > Deployment”** and click on the **“Plus button”**, select **“SFTP”** and give a name to your remote. Click on **“OK”**:

Set up the connection by first typing the IP and password of your remote in **“SFTP host”**. You may then click on **“Test SFTP connection”**. Given that you can successfully connect you should set up mappings. If you’d like you can click on **“Autodetect”** beside the **“Root path”**, it will then find the place of your home directory on the remote. All paths you specify after this will be relative to this home path. Then go to the **“Mappings”** tab.

<div align="center">
<img src = "/images/posts/deployment/path-mapping.png" width = "600"/>
</div>

As soon as you save or create a file in your local path, it will be copied to the **“Deployment path”** on your remote server. Perhaps you want to deploy it in a DeployedProjects/ folder as shown below. This will be relative to your **“Root path”** specified earlier, so the absolute deployment path will in our case be be `/home/username/DeployedProjects/TestProject/`:

<div align="center">
<img src = "/images/posts/deployment/deployment-path.png" width = "600"/>
</div>

Now we are finished with the preferences, click on **“Apply” > “OK”**, and then click **“Tools > Deployment > Automatic Upload”** and confirm that it is checked:

<div align="center">
<img src = "/images/posts/deployment/auto-deploy.jpg" width = "600"/>
</div>

To do the initial upload, right-click on you project folder in the project explorer and click on **“Upload to remote”**:

<div align="center">
<img src = "/images/posts/deployment/upload2remote.jpg" width = "400"/>
</div>

## Reference
* [Work remotely with PyCharm, TensorFlow and SSH][1]
* [PyCharm 使用远程 Interpreter][2]
* [配置pycharm远程调试的环境][3]

[1]: https://medium.com/@erikhallstrm/work-remotely-with-pycharm-tensorflow-and-ssh-c60564be862d
[2]: https://haoyu.love/blog473.html
[3]: https://blog.csdn.net/gsch_12/article/details/78233734

