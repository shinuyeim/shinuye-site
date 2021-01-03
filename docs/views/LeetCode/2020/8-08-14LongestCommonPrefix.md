---
title: 力扣|最长公共前缀
date: 2020-08-08
tags:
 - 算法
 - Java
categories:
 -  算法
---

## 14最长公共前缀

编写一个函数来查找字符串数组中的最长公共前缀。  

如果不存在公共前缀，返回空字符串 [^""]。

## 示例1：
>输入: ["flower","flow","flight"]  
输出: "fl"

## 示例2：
>输入:输入: ["dog","racecar","car"]  
输出: ""  
解释: 输入不存在公共前缀。  

## 代码
```java
class Solution {
    public String longestCommonPrefix(String[] strs) {
        if (strs.length == 0)
            return "";
        String prefix = strs[0]; 
        for (int i = 1; i < strs.length; i++) {
            int minLen = Math.min(prefix.length(), strs[i].length());
            
            for (int j = 0; j < minLen; j++) {
                if (prefix.charAt(j) != strs[i].charAt(j)) {
                    break;
                }
            }
            prefix = prefix.substring(0, j);
        }
        return prefix;
    }
}
```

