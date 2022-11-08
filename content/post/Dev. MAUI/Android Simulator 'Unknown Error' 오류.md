---
title: Android Simulator 'Unknown Error' 오류
categories: MAUI
date: 2022-11-08
tags:
- Android
- Error
---


## 증상
Android Simulator 생성 중 API를 선택하면 하단의 Unknown Error 가 발생하며 시뮬레이터가 생성되지 않는 문제 (기존에 생성되었던 시뮬레이터도 동작하지 않음)

여러 버전을 설치하던 중 설정 등이 꼬인 것으로 추정
![](Pasted%20image%2020221109020627.png)

## 확인된 해결 방법
- 각 운영체제의 사용자 디렉터리 아래의 .android 디렉터리에서 *.ini 확장자 파일 삭제 후 다시 시도