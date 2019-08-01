---
layout:     post
title:      "N个数求最大最小值"
subtitle:   "指针和数组的应用"
date:       2019-04-21 12:00:00
author:     "Lin Joey"
header-img: "img/post.jpg"
tags:
    - C语言
    - 数据结构
---

## 问题简介 ##
本文选取了一个利用指针和数组来求解多个数字的最大最小值并输出的问题，借此熟悉指针和数组指针的用法，并且在程序中探讨了问题规模改动时怎样能做最小程度的修改。

### 完整程序 ###
```c
#include <stdio.h>

//从十个数中找出最大最小的数
#define num 5	//这是问题规模不同时唯一需要修改的地方 
void FindMaxMin( int a[],int n );

int Max,Min;

int main()
{
	int number[num];
	for ( int i=0;i<num;i++ )
		scanf("%d", &number[i]);
	FindMaxMin( number,num );
	printf("最大值为%d,最小值为%d",Max,Min);
	return 0;
} 

void FindMaxMin( int a[],int n )
{
	int *p;				//p指向数组头 
	int *a_end = a + n;	//a_end指向数组尾+1 
	Max = Min = *a;		//令全局变量最大最小值等于a[0] 
	for ( p=a+1;p<a_end;p++ )
	{
		if ( *p>=Max )
			Max = *p;
		else if( *p<=Min )
			Min = *p;
	}
}
```

### 运行结果 ###
要求成功实现，在函数中多利用指针的好处就是当问题规模变动时，指针也能够随之指向多出来的部分，不需要对函数内部进行修改。这就是代码的可复用性及可扩展性。
