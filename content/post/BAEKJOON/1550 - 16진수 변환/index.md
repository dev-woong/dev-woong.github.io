---
title: "[BAEKJOON] 1550 - 16진수 변환"
categories: BAEKJOON
date: 2022-08-21
tags:
- .NET
- CSharp
- Algorithm
draft: false
---

[https://www.acmicpc.net/problem/1550](https://www.acmicpc.net/problem/1550)

입력받은 16진수 문자열을 10진수로 출력해주는 문제.

C#에서의 진수 변환에 대해 알아보는 개념으로 풀어보았습니다.

```c#
// 입력
var input = Console.ReadLine();

// 16진수 변환
var hex = Convert.ToInt32(input, 16);

// 출력
Console.WriteLine(hex);
```


[![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fdev-woong.io%2F2022.08.21-0001&count_bg=%233D91C8&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=%EC%A1%B0%ED%9A%8C%EC%88%98&edge_flat=true)](https://hits.seeyoufarm.com)