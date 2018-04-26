---
description: Jupyter Notebook 使用了浏览器作为编辑环境，给大家造成一种网上冲浪的错觉。
---

# Jupyter Notebook

## 安装

我按照[官方网站](http://jupyter.org/install)的说明，打算安装在Ubuntu16.04上，但是居然不成功。显示这个:

```bash
jupyter: command not found
```

害了我几分钟，最后搜到了[答案](https://stackoverflow.com/questions/35313876/after-installing-with-pip-jupyter-command-not-found)。要这样写:

```bash
~/.local/bin/jupyter-notebook
```

## 远程登录

我有一个台式机A 一直连网, 和一个笔记本B。怎么样用B登录Ａ的jupyter呢？







