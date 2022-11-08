---
title: Android Simulator 'Unknown Error' 오류
categories: MAUI
date: 2022-11-09
tags:
- Android
- Error
---


### 증상
Android Simulator 생성 중 API를 선택하면 하단의 Unknown Error 가 발생하며 시뮬레이터가 생성되지 않는 문제
![](Pasted%20image%2020221109020627.png)

## 해결 방법
각 운영체제의 사용자 디렉터리 아래의 .android 디렉터리에서 *.ini 확장자 파일 삭제 후 다시 시도