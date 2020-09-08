# 111阶乘后的零

## 日期
2020年9月8

给定一个整数 n，返回 n! 结果尾数中零的数量。

## 示例1:

>输入: 3  
输出: 0  
解释: 3! = 6, 尾数中没有零。

## 示例2:

>输入: 5  
输出: 1  
解释: 5! = 120, 尾数中有 1 个零.  

## 说明: 

你算法的时间复杂度应为 O(log n) 。  


## 代码 
```java
class Solution {
public int trailingZeroes(int n) {
    int count = 0;
    while (n > 0) {
        count += n / 5;
        n = n / 5;
    }
    return count;
    }
}
```

