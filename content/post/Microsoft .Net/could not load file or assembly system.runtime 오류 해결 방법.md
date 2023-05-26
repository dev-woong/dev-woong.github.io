---
title: could not load file or assembly system.runtime 오류 해결 방법
#description: 설명
categories: Microsoft .Net
date: 2023-02-23
tags: [ Error, Bug ]
draft: false
---

## 증상

> could not load file or assembly "system.runtime version=7.0.0.0 ....."

dotnet SDK 버전을 제대로 인식하지 못하는 경우 발생되는 것으로 보임

## 해결 방법

설치된 모든 SDK, Runtime 등을 삭제하고 재설치

삭제는 [Dotnet-Core-Uninstaller](https://github.com/dotnet/cli-lab/releases) 를
이용하면 좋았음
