---
description: 我主要做凝聚态物理数值计算　常用的软件配置　会记录再这里
---

# 软件说明书

## software overview

2009年，在我还是大学一年级的时候，学习了C语言；这个考完试就没有用了，当时更为感兴趣的是微积分、电磁学。直到大三，计算物理需要模拟非常有趣的分形, 晶体生长, 于是我重新拾起来C，艰难地编写程序，输出txt数据，然后再用origin软件画出图来。

作为物理专业的学生，更多关心的是最后漂亮的数据图片；而写的程序，简直就像用一推垃圾歪扭搭建的高楼，到处是bug，临时的补漏，稍有不慎就会塌方。写完之后自己也根本看不懂。

一直到了博士四、五年级，我意识到C++比Ｃ好像厉害很多，才开始正儿八经地使用Object-oriented programming。比如在Ising model的蒙特卡洛模拟里面写了一个class ：

```cpp
class Ising{
public:
    Ising(N,M,Temperature);
    void update();
    double magnetization();
private:
    bool s[N][M];
    double Temperature;
}
```

这样的思维方式是很好的，程序的可读性、可重复利用性、封装修改，等等。如果我们想画一个相图，就可以重复利用上面的class

```cpp
class PhaseDiagram{
public:
    PhaseDiagram(N,M,T1,T2);
    *double MagnetizationVsTemperature();
private:
    Ising oneRun[100];
}
```



大学时候，还接触一些软件和语言Mathematica, Matlab, Java, JavaScript 等等。但是其实只是为了用语言的一句话，比如Mathematica画函数图像最方便，也不用网格，直接就出来了:

```python
Plot[Sin[x],{x,-5,5}]
```

最近的很几年里，非常多的软件工具Python, R, GitHub涌现，在一门语言没学精通，就转向其他　也是很尴尬的。很多时候，时间浪费再了一些技术问题上，举例子：

* 如何用python调用c++的函数
* fftw3怎么装在自己电脑　怎么配置　编译
* hdf5怎么安装　配置　编译
* github git 怎么用
* javascript　和　网页markdown等等怎么结合
* c++ 怎么样输入数组　输出数组
* c++怎么样读写文件?
* Matlab 优化包　怎么使用　这么多奇怪的参数!
* linux 写一个管理程序的程序
* ... ...

很多问题解决，很多没有，很多问题解决了，又忘了。

所以，本网站是一个归类的总结。



