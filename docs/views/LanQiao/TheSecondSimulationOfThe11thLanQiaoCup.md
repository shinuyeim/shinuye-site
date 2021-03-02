---
title: 第十一届蓝桥杯大赛第二次模拟
date: 2021-03-01
tags:
 - 竞赛
 - C/C++
categories:
 -  蓝桥杯
---


## 题目

### 5. 反倍数  
【问题描述】  
给定三个整数 a, b, c，如果一个整数既不是 a 的整数倍也不是 b 的整数倍还不是 c 的整数倍，则这个数称为反倍数。  
请问在 1 至 n 中有多少个反倍数。  
【输入格式】  
输入的第一行包含一个整数 n。  
第二行包含三个整数 a, b, c，相邻两个数之间用一个空格分隔。  
【输出格式】  
输出一行包含一个整数，表示答案。  
【样例输入】  
30  
2 3 6   
【样例输出】  
10  
【样例说明】
以下这些数满足要求：1, 5, 7, 11, 13, 17, 19, 23, 25, 29。  
【评测用例规模与约定】  
对于 40% 的评测用例，1 <= n <= 10000。  
对于 80% 的评测用例，1 <= n <= 100000。  
对于所有评测用例，1 <= n <= 1000000，1 <= a <= n，1 <= b <= n，1 <= c <= n。  

#### 思路
反倍数就是不能同时被a , b, c整除的数，那么我们就从 1 循环到 n ，如果出现一个不能同时被a, b, c整除的数，那么就计数加一，因为我们最后要求的是从 1 到 n 中反倍数的个数。也可以逆向思考，如果一个数能被a, b或者c整除，那么这个数就一定不是反倍数，所以我们统计出能被a, b或者c整除的数，然后总的 n 个数减去统计出的数字，就是我们需要的答案。

#### 代码
C++语言
```c
#include<bits/stdc++.h>
using namespace std;

int n, a, b, c;    // 定义变量 
int ans = 0;     

int main() {
	cin >> n;     //输入一个整数 n 代表从 1 到 n 
	cin >> a >> b >> c;  //输入三个整数 
	for(int i = 1; i <= n; i++) {  // 从 1 循环 ，一直循环到 n  
		if(i % a != 0 && i % b != 0 && i % c != 0) {  // 如果一个数不能被 a 或者 b 或者 c 整除的话，那么就是反倍数   % 取余数 根据余数是否为 0 来判断是否能整除 
			ans++;  // 有的话就加一 
		}
	/*
		if(i % a == 0 || i % b == 0 || i % c == 0) {  // 如果一个数能被 a 或者 b 或者 c 整除的话,那么就不是反倍数   % 取余数 根据余数是否为 0 来判断是否能整除 
			ans++;  // 有的话就加一 
		}
	*/
	}
	cout << ans;
  //cout << n-ans;  // 输出反倍数的个数 
	return 0;
}
```
C语言版
```c
#include<stdio.h>

int main(){
	int n,a,b,c;
	int ans = 0;
	
	scanf("%d",&n);
	scanf("%d %d %d",&a,&b,&c);
	
	for(int i = 1;i<=n;i++){
		if(i % a != 0 && i % b !=0 && i % c != 0){
			ans++;
		}
	} 
	printf("%d",ans);
	
	return 0;
} 
```


### 6.凯撒加密  
<p>【问题描述】<br>给定一个单词，请使用凯撒密码将这个单词加密。<br>凯撒密码是一种替换加密的技术，单词中的所有字母都在字母表上向后偏移3位后被替换成密文。即a变为d，b变为e，...，w变为z，x变为a，y变为b，z变为c。<br>例如，lanqiao会变成odqtldr。<br>【输入格式】<br>输入一行，包含一个单词，单词中只包含小写英文字母。<br>【输出格式】<br>输出一行，表示加密后的密文。<br>【样例输入】<br>lanqiao<br>【样例输出】<br>odqtldr<br>【评测用例规模与约定】<br>对于所有评测用例，单词中的字母个数不超过100。<br><br><br></p>

#### 思路

#### 代码