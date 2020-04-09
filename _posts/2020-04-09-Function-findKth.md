---
layout:     post
title:      "查找数组中第k小的数字"
subtitle:   "方法：冒泡排序"
date:       2020-04-09 12:00:00
author:     "Lin Joey"
header-img: "img/post.jpg"
tags:
    - JAVA
    - 数据结构
---

## 问题简介 ##
给定数组元素个数，随机生成一个数组，查找第k小的数字。  

### 完整程序 ###
```java
package com.linjava;

import java.util.Scanner;

/**
 * 数组中第k个最小的数字
 *
 * @author linziwei
 * @date 2020/4/9
 */
//算法思想：倒序冒泡排序，每次把最小的移到最后，直到冒泡次数等于k停止
public class FindKth {
    //函数findKth，冒泡法倒排序
    public int findKth(int[] arr, int k) {
        for (int j = 0; j < arr.length; j++) {
            for (int i = 0; i < arr.length - j - 1; i++) {
                if (arr[i] < arr[i + 1]) {
                    int temp = arr[i];
                    arr[i] = arr[i + 1];
                    arr[i + 1] = temp;
                }
            }
            if (k == (j + 1)) {
                break;
            }
        }
        return arr[arr.length - k];
    }


    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.println("输入数组元素个数");
        int num = input.nextInt();

        int a[] = new int[num];
        // 使用随机数填充
        for (int i = 0; i < a.length; i++) {
            a[i] = (int) (Math.random() * 100);
        }
        // 排序前，先把内容打印出来3
        for (int i = 0; i < a.length; i++) {
            System.out.print(a[i] + " ");
        }
        System.out.println(" ");
        System.out.println("要找第几小的数？");
        int k = input.nextInt();
        // 实例化对象
        FindKth fk = new FindKth();
        // 调用findKth函数,找出第k小的数
        int min = fk.findKth(a, k);
        System.out.println("第" + k + "小的数是" + min);
    }
}
```

### 运行结果 ###
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/findkth2.png)  
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/findkth1.png)  

### 时间复杂度分析 ###
嵌套循环，最好O(n)
时间复杂度为O(n2)