---
layout:     post
title:      "多项式问题"
subtitle:   "算法的设计优化"
date:       2018-10-7 12:00:00
author:     "Lin Joey"
header-img: "img/post.jpg"
tags:
    - C语言
    - 数据结构
---
数学的函数经常会见到多项式，那么怎么让计算机帮助我们生成并计算多项式呢？一个简单的方法是直接循环，但是这样写出的代码惨不忍睹，另一个比较好的算法是中国古代的秦九韶算法，他们孰优孰劣呢？

## 问题简介 ##
本文选取了一个多项式的问题，进行探究。 

### 完整程序 ###
```c
#include <stdio.h>
#include <time.h>
#include <math.h>>

double Duoxiangshi( int n, double a[], double x );	//笨办法搞多项式 
double Duoxiangshi2( int n, double a[], double x );	//秦九韶算法 

int main()
{
	int n = 0;
	printf("请输入多项式最大次数：\n");
	scanf("%d",&n);
	double a[n];
	for ( int i=0; i<=n; i++ )
	{
		printf("请输入第%d个系数：", i);
		scanf("%lg", &a[i]);
	}
	double x = 0;
	printf("请输入未知数x的值：\n");
	scanf("%lg", &x);
	double p = 0, q = 0;
	p = Duoxiangshi( n, a, x );
	q = Duoxiangshi2( n, a, x );
	printf("常规值为%g", p);
	printf("秦九韶为%g", q); 
} 

//直接用循环去写的多项式 
double Duoxiangshi( int n, double a[], double x )
{
	int i = 0;
	double p = a[0];
	for( i=1; i<=n; i++ )
	{
		p += a[i] * pow(x,i);
	}
	return p;
} 

//秦九韶算法
double Duoxiangshi2( int n, double a[], double x )
{
	int i = 0;
	double p = a[n];
	for ( i=n; i>0;i-- )
		p = a[i-1] + x*p;
	return p;
} 
```

### 运行结果 ###
可以观察到，秦九韶算法明显速度更快。所以算法设计的重要性不言而喻。
