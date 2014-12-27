title: pip – pip安装和使用教程
date: 2014-11-17 21:48:45
tags: pip
---
pip是一个安装python库很方便的东西，类似yum，pip search pip install，如果没wget的话，就用curl -O 另外也可以考虑用easy_install代替pip


来源：http://www.jsxubar.info/install-pip.html
pip 是一个安装和管理 Python 包的工具 , 是 easy_install 的一个替换品。本文将详细说明 安装 pip 的方法和 使用 pip 的一些基本操作如安装、更新和卸载 python 包。

目录 [显示]
一、pip安装

安装pip的方法非常简单, 首先下载一个python程序, 然后运行这个程序即可. 这个是在线安装.
$ curl -O https://raw.github.com/pypa/pip/master/contrib/get-pip.py
$ python get-pip.py
如果不能联网, 可以到这里下载, 然后按照压缩包的说明安装即可.

如果要安装pip的开发版本, 使用以下命令即可:

easy_install pip==dev
开发包源码下载地址: pip 开发版本

Mac 安装方法

1.安装 easy_install
$ wget http://python-distribute.org/distribute_setup.py
$ sudo python distribute_setup.py
2.安装 pip
sudo easy_install pip
二、常用 pip 操作

pip的基本操作包括安装,升级和卸载 python 包, 使用如下命令即可, 以 simplejson 包作为例子.

1. 安装python包

1
$ pip install simplejson
2. 升级python包

1
2
3
$ pip install --upgrade simplejson
[... progress report ...]
Successfully installed simplejson
3. 卸载python包

1
2
3
4
5
6
$ pip uninstall simplejson
Uninstalling simplejson:
  /home/me/env/lib/python2.7/site-packages/simplejson
  /home/me/env/lib/python2.7/site-packages/simplejson-2.2.1-py2.7.egg-info
Proceed (y/n)? y
  Successfully uninstalled simplejson
如需要更多 pip 安装和使用的教程可以到 pip 英文文档 网站查看。

参考文章

pip 1.1 安装和使用教程  – 英文, 简单介绍了pip的各个方面, 包括pip安装和使用教程。