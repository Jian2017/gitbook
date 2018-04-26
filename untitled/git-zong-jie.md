# 单机版

Git 的工作单位是一个文件夹　及其里面的文件

## init, add, commit

选择一个工作目录，打开terminal 敲击

`git init`

这样工作目录就多了一个隐藏文件夹.git

然后工作，得到一堆文件

`git add .`

`git commit `

## 查询状态

```text
git status
```

**working** --\[add\]--&gt; **tracked** --\[commit\]--&gt; **committed**

```text
git log
```

## 设置

git 可以设置软件的总体属性。这些参数都在用户本地目录的`.gitconfig`

```bash
$ git config --global user.name "<用户名>"
$ git config --global user.email "<电子邮件>"
$ git config --global color.ui auto
```



