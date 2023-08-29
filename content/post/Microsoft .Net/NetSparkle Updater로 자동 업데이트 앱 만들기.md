---
title: NetSparkle Updater로 자동 업데이트 앱 만들기
categories: .Net
date: 2023-08-23
tags:
  - NetSparkle
  - App
  - Cast
draft: true
---

>[!업데이트 동작 방식]
>1. 어플리케이션 컴파일 (ex : `dotnet publish`)
>2. 일종의 설치 프로그램 생성(exe, msi, pkg, dmg ...)
>3. App Cast 파일 생성
>4. 설치 프로그램, App Cast 파일, Signature 파일 등 서버에 업로드
>5. 앱을 열고 사용 가능한 업데이트에 대한 자동 알림 수신
>6. 클라이언트에서 업데이트 선택

현재 실행중인 프로그램의 버전과 비교하게 되는데 이 버전은 `*.csproj` 파일의 `<Version>` 태그를 참조함