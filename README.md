# AlgorithmNote

**引言**

算法学习笔记和代码，持续更新

算法（Algorithm）是指用来操作数据，解决程序问题的一组方法。

+++

## 首篇：复杂度

​	复杂度是用来衡量算法优劣的度量单位，而其定义又可从时空两个维度考虑：

+ **时间**：执行当前算法所消耗的时间
+ **空间**：执行当前算法需要占用多少内存空间

### 时间复杂度

​	因为如果按实际运行程序的执行时间的话，可能会由于机器性能差异导致时间误差，所以大佬们提出了通用方法【大O符号表示法】：

$$
T(n)=O(f(n))
$$

>  **n**表示数据规模
>
>  **f(n)** 存在的某个函数,使得T(n)/f(n)=非零常数, 那么f(n)称为T(n)的同数量级函数 
>
>  **T(n)** 一段程序运行,各种操作代码所执行的总次数 
>
>   **O** 表示渐进于无穷的行为 

**常见的时间复杂度量级**

![Big-O Complexity Chart](/images/TimeComplexity.png)

参考链接：[五分钟学会时间复杂度]( https://www.cxyxiaowu.com/1996.html )

***时间复杂度分析的基本策略*：从内向外，从最深处开始分析。**

<font color="red">例如：</font>

```C
for (int i = 0; i < n; i++) {
    for (int j = i; j < n; j++) {
        printf("Hello World\n");
    }
}
```

计算时间复杂度：

```markdown
外：i = 0;
	内：循环n-1次;
	
...}共n次

外：i = n-1;
	内：循环1次

则执行次数：T(n)=(n-1)+(n-2)+...+1
			  =n*[(n-1)+1]/2
			  =n^2/2
	计算的时间复杂度：T(n)=O(n^2)
```

<font color="red">再例如：</font>

```c
for (int i = 2; i < n; i++) {
    i *= 2;
    printf("%i\n", i);
}
```

计算时间复杂度

假设循环次数为t,则循环条件满足：2^t < n
	则执行次数：
$$
T(n)=\lim_{n\rightarrow+\infty}{log_{2}n}
$$
​	时间复杂度为O(log_2(n))，即O(log n)。



<font color="red">再加上递归呢：</font>

```c
long long Fib(long long N)
{
  if (N < 3)    //当N<3时，斐波那契数为1
  	return 1;
  return Fib(N - 1) + Fib(N - 2);//函数递归
}
```

参考链接：[斐波那契数的时间复杂度、空间复杂度详解]( https://blog.csdn.net/lxf_style/article/details/80458519?depth_1-utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromBaidu-1&utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromBaidu-1 )

<div align="center">
    <img src="/images/Fibnaci.png"/>
</div>

### 空间复杂度

​	程序执行过程种变量的个数。



小结：

1、[算法复杂度速查表](https://mp.weixin.qq.com/s?__biz=MzUyNjQxNjYyMg==&mid=2247486565&idx=3&sn=28bc1c28f58cb3127638826a341d66cb&chksm=fa0e63e4cd79eaf200f617247927d83ef229385d42790e58ddf7cff004b226e9fb499d554fe2&scene=21#wechat_redirect ) 

2、