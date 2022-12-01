---
title: 비동기(Async) - Async, Await
image: resource/thisisengineering-raeng-nyAzMQ6Ejgs-unsplash.jpg
categories: MAUI
date: 2022-01-02
tags: [ MacOS, .NET7.0, CSharp, Setting ]
draft: true
---

필자는 Jetbrains의 Rider 라는 IDE를 사용중입니다.
하지만 해당 IDE에서는 아직 MAUI에서의 Hot Reload 또는 XAML Preview를 지원하지 않고 있는 것으로 보이기 때문에 Visual Studio에서 프론트엔드를, Rider에서 백엔드를 개발할 수 있도록 환경을 구성하고자 합니다.

## UI 개발을 위한 Visual Studio for Mac(2022 ⬆️) 설치



## MacOS 환경에서의 Rider MAUI 세팅
https://blog.jetbrains.com/dotnet/2022/05/25/macos-environment-setup-for-maui-development/
https://github.com/dotnet/maui/wiki/macOS-Install
1. .NET7.0 이상 SDK 설치
2. bashrc, zshrc, fish.cfg 등에 PATH 설정 추가 `/Users/$USER/.dotnet/tools` 
3. 터미널에서 `dotnet tool install -g Redth.Net.Maui.Check` 이후 `maui-check --main`
	1. dotnet 버전 관련 오류 발생
		![](Pasted%20image%2020221108230756.png)
4. d


- Android 빌드를 위한 JAVA SDK 설치(여기서는 11 버전을 요구했음)
![](resource/Pasted%20image%2020220915225918.png)