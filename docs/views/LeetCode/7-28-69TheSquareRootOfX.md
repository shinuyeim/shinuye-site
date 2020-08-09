---
title: 力扣|x的平方根
date: 2020-07-28
tags:
 - 算法
 - Java
categories:
 - 算法
---

## 69x的平方根

实现 [^int sqrt(int x)] 函数

计算并返回 x 的平方根，其中 x 是非负整数。

由于返回类型是整数，结果只保留整数的部分，小数部分将被舍去。


## 示例1：
>输入: 4  
输出: 2

## 示例2：
>输入: 8  
输出: 2  
说明: 8 的平方根是 2.82842...,由于返回类型是整数，小数部分将被舍去

## 代码
```java
class Solution {
    public int mySqrt(int x) {
        int l=1,r=x;
        int mid=(l+r)/2;
        while(l<=r){
            if(mid==x/mid)
                return mid;
            else if(mid>x/mid)
                r=mid-1;
            else
                l=mid+1;
            mid=(l+r)/2;
        }
        return mid;
    }
}
```