---
description: >-
  I tried c++ in the beginning, but switched to python. h5py is much friendly to
  use.
---

# hdf5

## Append data to hdf5 data

Monte Carlo data can be stored in such a manner:

```python
import h5py
import numpy
f = h5py.File("mytestfile3.hdf5", "a")
L=8
N=3
s=numpy.random.choice(a=[False, True], size=(L,N), p=[0.5,0.5])
dset = f.create_dataset("bigBOOL",data=s,chunks=True,maxshape=(None, 33))
for i in range(10):
    dset.resize(dset.shape[1]+N, axis=1)
    dset[:,-3:]=s
f.close()
```

## create a file

```python
import h5py
f = h5py.File("mytestfile.hdf5", "a")
print type(f)
f.close()
```

f 就像是一个指针 一个handler，它是一个object 输出。

```text
<class 'h5py._hl.files.File'>
```

\# 以写入方式打开文件

\# r  只读，文件必须已存在

\# r+ 读写，文件必须已存在

\# w  新建文件，若存在覆盖

\# w- 或x，新建文件，若存在报错

\# a  如存在则读写，不存在则创建\(默认\)

## groups: create, access, delete

### create

```python
import h5py
f = h5py.File("mytestfile.hdf5", "a")
f.create_group("a/a2/b")
f.close()
```

上面的例子直接构造了多个group, 而且还是嵌套的。同一个group不能再次create，否则会报错。

```python
import h5py
f = h5py.File("mytestfile.hdf5", "a")
f.create_group("a/a2/b") #报错
f.create_group("a/a1/b") #安全，因为有不同的group被构造
f.close()
```

## access

那么问题来了，怎么显示和造作group呢？

下面的方法，就是构造一个类似f的 指针fa

```python
import h5py
f = h5py.File("mytestfile.hdf5", "a")
print f.keys()
fa=f['a']
print type(fa)
print fa.keys()
print type(fa.keys())
f.close()
```

输出：

```text
[u'a', u'chunked', u'subgroup1']
<class 'h5py._hl.group.Group'>  
[u'a', u'a1', u'a2']
<type 'list'>
```

注意到，fa的类型和f的类型是一样的。

另外 fa.key\(\)  是一个python的list类型。

### delete

稍后再说

## dataset

###  创建

![](../.gitbook/assets/image%20%281%29.png)

```python
import h5py
import numpy as np
f = h5py.File("mytestfile.hdf5", "a")
dset = f.create_dataset("default1", (100,),dtype='i8')
f.close()
```

{% hint style="info" %}
【小心】只要报过一次错, hdf5 文件就写不进去了。

错误包活：重复创建数据集，创建一个 没有说明类型的数据集。
{% endhint %}

### 

### 使用

```python
import h5py
import numpy as np
f = h5py.File("mytestfile.hdf5", "a")

d=f['a1/b3']["why2"]
d[3]=666
print d[3]
type(d)

f.close()
```

d 的类型是 `<Closed HDF5 dataset>`

![](../.gitbook/assets/image%20%282%29.png)



## attribute

```python
import h5py
import numpy as np
f = h5py.File("mytestfile22.hdf5", "a")
dset = f.create_dataset("default1", (100,),dtype='i8')
dset.attrs['temperature'] = 99.5
f.close()
```

![](../.gitbook/assets/image%20%283%29.png)

## 

## 资料来源：

{% embed data="{\"url\":\"https://blog.csdn.net/david830\_wu/article/details/63782190\",\"type\":\"link\",\"title\":\"HDF5快速上手全攻略 - CSDN博客\",\"description\":\"Hierarchical Data Format\(HDF\)是一种针对大量数据进行组织和存储的文件格式。本文回归了HDF5的安装和使用，涉及文件结构，数据集读写，子集访问等基本操作，以及分块与压缩，添加属性，并行化等高级课题。此外，文中还列出了python和C++的实用代码。\",\"icon\":{\"type\":\"icon\",\"url\":\"https://csdnimg.cn/public/favicon.ico\",\"aspectRatio\":0}}" %}

上面这个攻略是我见过写的最好的一个。

官方的说明书：

[https://support.hdfgroup.org/HDF5/Tutor/HDF5Intro.pdf](https://support.hdfgroup.org/HDF5/Tutor/HDF5Intro.pdf)

