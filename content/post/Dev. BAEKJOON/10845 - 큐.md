---
title: "[BAEKJOON] 10845 - 큐"
categories: BAEKJOON
date: 2022-08-21
tags:
- .NET
- CSharp
- Algorithm
draft: false
---

[https://www.acmicpc.net/problem/10845](https://www.acmicpc.net/problem/10845)

스택 및 스택 명령어를 구현하여 데이터를 입/출력하는 문제

```c#
// 명령어의 개수 입력
var command_count = int.Parse(Console.ReadLine()!);

// Queue로 사용될 변수 생성
var queue = new List<int>();

// 명령어 개수 만큼 반복
while (command_count-- > 0)
{
	// 명령어 입력 후 공백(" ")을 기준으로 분리
	var command = Console.ReadLine()!.Split(" ");

	// 공백 기준 앞에 있는 명령어를 통한 switch 조건 분기
	switch (command[0])
	{
		case "push":
			// queue 변수에 데이터 축적
			queue.Add(int.Parse(command[1]));
			continue;
		case "pop":
			// Queue의 특성에 따라 선입선출하여 처음 데이터부터 pop!
			// Any() 함수는 조건에 맞는 값이 해당 컬렉션에 존재하는지 확인하는 함수이다.
			// 매개변수가 없는 경우는 컬렉션에 값이 존재하는지 여부를 반환한다.
			Console.WriteLine(queue.Any() ? queue.First().ToString() : "-1");
			if (queue.Any()) queue.RemoveAt(0);
			continue;
		case "size":
			Console.WriteLine(queue.Count.ToString());
			continue;
		case "empty":
			Console.WriteLine(queue.Any() ? "0" : "1");
			continue;
		case "front":
			// Linq의 First()를 이용하여 첫 번째 값을 반환받는다.
			Console.WriteLine(queue.Any() ? queue.First().ToString() : "-1");
			continue;
		case "back":
			// Linq의 Last()를 이용하여 마지막 값을 반환받는다.
			Console.WriteLine(queue.Any() ? queue.Last().ToString() : "-1");
			continue;
	}
}
```


[![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fdev-woong.io%2F2022.08.21-0005&count_bg=%233D91C8&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=%EC%A1%B0%ED%9A%8C%EC%88%98&edge_flat=true)](https://hits.seeyoufarm.com)