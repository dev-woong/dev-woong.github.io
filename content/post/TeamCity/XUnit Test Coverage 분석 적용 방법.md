---
title:  TeamCity C#(.NET Core) XUnit Test Coverage 분석 적용 방법
image: resource/title.jpg
categories: TeamCity
date: 2022-11-30
tags: [ TeamCity .NET Core XUnit Test Coverage ]
draft: true
---

## 환경
- 개발 언어 : C#(.NET Core)
- 테스트 프레임워크 : XUnit
- 에이전트 운영체제 : MAC OS
- 에이전트 프로세서 : M1 Ultra
- 에이전트 아키텍처 : ARM 64

## 별도 Artifact 서버가 없는 경우
TeamCity에서는 별도의 Artifact 서버(Amazon S3 등)를 이용하여 Artifact를 저장하도록 권장하고 관련 설정이 기본적으로 강제로 활성화되어있는데 별도의 서버가 존재하지 않는 경우 해당 설정을 해제하면 Code Coverage를 확인할 수 있음

1. Administration > Global Settings > Enable isolation protection 체크 해제
   ![](../../resource/Pasted%20image%2020221130164035.png)
2. 완료된 Build Configuration에서 Code Coverage 확인
   ![](../../resource/Pasted%20image%2020221130164318.png)

%%
## MacOS Agent Test 완료 직후 멈추는 경우
- 우선 Test 동작에 Mac Agent를 사용하지 않도록 함
%%
