---
title: sin x 的近似值
date: 2020-09-14
tags:
 - 算法
 - C
categories:
 -  算法
 -  笔记
---


## 题目描述

欲求\snx$ 的近似值, 只能采用近似计算方法，用四则运算的式子来求得。
![alt 四则运算公式](D:\002屏幕截图\四则运算公式)

### 示例1:
::: tip
输入：[1,2,3,1]  
输出：4  
解释：偷窃 1 号房屋 (金额 = 1) ，然后偷窃 3 号房屋 (金额 = 3)。  
偷窃到的最高金额 = 1 + 3 = 4 。
:::

### 示例2:
::: tip
输入：[2,7,9,3,1]  
输出：12  
解释：偷窃 1 号房屋 (金额 = 2), 偷窃 3 号房屋 (金额 = 9)，接着偷窃 5 号房屋 (金额 = 1)。  
偷窃到的最高金额 = 2 + 9 + 1 = 12 。
:::

### 提示: 

 > + 0 <= nums.length <= 100 
 > + 0 <= nums[i] <= 400


## 题目分析



### 代码 
```java
class Solution {
    public int rob(int[] nums) {
        if (nums == null || nums.length == 0) {
            return 0;
        }
        int length = nums.length;
        if (length == 1) {
            return nums[0];
        }
        int first = nums[0], second = Math.max(nums[0], nums[1]);
        for (int i = 2; i < length; i++) {
            int temp = second;
            second = Math.max(first + nums[i], second);
            first = temp;
        }
        return second;
    }
}

```