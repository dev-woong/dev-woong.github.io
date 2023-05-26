---
title: Build Step (.NET)
categories: MacOS
date: 2022-10-01
tags:
- XCode
- Beta
- Bug
draft: true
---

## Build Configuration 순서

1. 태그 또는 패키지 버전 읽기
2. 종속성 복원(Nuget Package 변경 여부를 체크하여 Cache 삭제)
3. 종속성 패키지들 참조시켜 Build (Release, Unity)
4. 단위 테스트 (Release)
5. Nuget 패키지 생성
6. NPM 패키지 생성
7. 동일 버전 패키지 존재 시 일괄 삭제
8. 패키지 일괄 배포
