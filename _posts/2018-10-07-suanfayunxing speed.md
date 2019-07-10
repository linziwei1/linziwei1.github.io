---
layout:     post
title:      "算法的运行效率问题"
subtitle:   "递归和循环的爱恨情仇"
date:       2018-10-7 12:00:00
author:     "Lin Joey"
header-img: "img/post.jpg"
tags:
    - C语言
    - 数据结构
---
在程序编写中，循环和递归有着各自的优势，循环易于理解但会让问题规模扩大，递归可以炫技、清晰明了但不易阅读，且受限于大规模的数据问题。本文将对运行效率问题做一个探讨。

## 问题简介 ##
本文选取了一个简单的输出“1~N”的问题，来简单探讨下递归和循环到底谁更快的问题。  
为了量化比较，选用了ms为单位。  
### 计算程序用时代码 ###
```c
# include <stdio.h>
# include <windows.h>
# include <time.h>
{
	long start,end,runtime;
	start = clock();
	Functions();
	end = clock();
	runtime = end - start;
}
```
### 完整程序 ###
```c
# include<stdio.h>
# include <windows.h>
# include <time.h>

//程序说明：两种方法输出1~N； 
//结论：递归运算速率理论上应该大于循环运算，但实际情况下因为递归对函数的多重调用，反而更慢
//且递归对于大规模运算较为吃力 

void PrintN( int N );
void PrintG( int N );

int main()
{
	int N = 0;
	long op,ed,op2,ed2;
	printf("请输入数字：");
	scanf("%d",&N);
	op = clock();
	PrintN( N );
	ed = clock();
	printf("\n");
	printf("循环程序共用时：%ldms\n",ed-op);
	op2 = clock();
	PrintG( N );
	ed2 = clock();
	printf("\n");
	printf("递归程序共用时：%ldms\n",ed2-op2);
	return 0;
}

//递归 
void PrintG( int N )
{
	if( N ){
		PrintN(N-1);
		printf("4%d ",N); 
	}
	return;
}

//循环
void PrintN( int N)
{
	for( int i=1;i<=N;i++ )
	{
		printf("%4d ",i);
	}
} 
```

### 运行结果 ###
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/运行效率截图.jpg)

# 最终结论 #
> 递归运算速率一般大于循环运算，但实际情况下针对较小问题规模因为递归对函数的多重调用，反而更慢。
> 然而对于更为复杂的问题递归效率还是远高于循环的，因此在程序设计中递归不单单是炫技更是一种绝佳之选。  
> 递归对于大规模运算及嵌套逻辑多时较为吃力
