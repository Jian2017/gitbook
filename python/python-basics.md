# python basics

## list, tuple, key, set



## ndarray

```python
np.zeros((5, 1))  
np.zeros((1, 5))
np.zeros((5,))  
```

the all gives different result



```python
np.zeros((3,))
t=np.zeros((2,3))
```

results:

```text
array([ 0.,  0.,  0.])
array([[ 0.,  0.,  0.],
       [ 0.,  0.,  0.]])
```

所以总结就是:

\[更高的维度, ,低维度\]





index和c语言一样 从 0,1,2,到 N-1

```text
t.shape
```

得到：

```python
(2,3)
```

## numpy.fft.fft\(\)

输入的必须是一维的ndarray   \(n,\)

\(n,1\) \(1,n\) \(n,1,1\) 等等都不行，须使用其他的函数。

