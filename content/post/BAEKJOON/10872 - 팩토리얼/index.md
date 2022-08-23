---
title: "[BAEKJOON] 10872 - 팩토리얼"
categories: BAEKJOON
date: 2022-08-21
tags:
- .NET
- CSharp
- Algorithm
draft: false
---

[https://www.acmicpc.net/problem/10872](https://www.acmicpc.net/problem/10872)

입력받은 정수만큼 팩토리얼 연산을 수행하는 문제

```c#
// 팩토리얼 개수 입력
var count = Convert.ToInt32(Console.ReadLine());

// Enumerable.Range()를 통해 1부터 {count}개의 차례대로 증가되는 컬렉션을 생성
// 해당 컬렉션의 값을 Linq의 Aggregate 함수를 통해 집계
// 컬렉션에 데이터가 없는 경우 1을 sum에 저장, 데이터가 있는 경우 i에 차례대로 할당되어 연산 수행
// 연산의 결과값이 current에 누적되어 최종 결과값이 sum에 저장됨
var sum = Enumerable.Range(1, count).Aggregate(1, (current, i) => current * i);

Console.WriteLine(sum);
```


[![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fdev-woong.io%2F2022.08.21-0002&count_bg=%233D91C8&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=%EC%A1%B0%ED%9A%8C%EC%88%98&edge_flat=true)](https://hits.seeyoufarm.com)