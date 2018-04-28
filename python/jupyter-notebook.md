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

另外，按照Jupyter官网上的步骤，使用pip3会失败，应该使用python2 对应的pip 安装可成功。

## 远程登录

我有一个台式机A , 和一个笔记本B。怎么样用B登录Ａ的jupyter呢？

1. A设置密码 生成sha
2. A设置python的config文件
3. B远端登录
4. B的浏览器输入 `A的ip地址:设置的端口`

{% hint style="info" %}
jupyter notebook的console必须一直开着。A主机的一直在运行。
{% endhint %}

资料：

{% embed data="{\"url\":\"https://zhuanlan.zhihu.com/p/30845372\",\"type\":\"link\",\"title\":\"如何在window访问ubuntu服务器的jupyter notebook\",\"description\":\"弄了一早上，写点东西记录下。首先是安装pip install jupyter //这命令默认使用的是Python2.7.5版本安装；  or  conda install jupyter //如果你装了anaconda，可以用这个 生成配置文件$jupyter notebook --genera…\",\"icon\":{\"type\":\"icon\",\"url\":\"https://static.zhihu.com/static/favicon.ico\",\"aspectRatio\":0}}" %}

{% embed data="{\"url\":\"https://segmentfault.com/a/1190000009076881\",\"type\":\"link\",\"title\":\"系统维护中 - SegmentFault\",\"icon\":{\"type\":\"icon\",\"url\":\"https://segmentfault.com/favicon.ico\",\"aspectRatio\":0}}" %}

{% embed data="{\"url\":\"https://www.jianshu.com/p/444c3ae23035\",\"type\":\"link\",\"title\":\"设置 jupyter notebook 可远程访问\",\"description\":\"首先是要 安装 Anaconda 。 默认情况下，安装好 Anaconda 后打开 jupyter notebook, 访问本地localhost:8888 即可。但是如果要访问另一台机器，比如...\",\"icon\":{\"type\":\"icon\",\"url\":\"https://cdn2.jianshu.io/assets/apple-touch-icons/152-bf209460fc1c17bfd3e2b84c8e758bc11ca3e570fd411c3bbd84149b97453b99.png\",\"width\":152,\"height\":152,\"aspectRatio\":1}}" %}







