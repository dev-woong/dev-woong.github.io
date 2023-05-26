---
title: Nuget 캐시 삭제
#description: 설명
categories: .Net
date: 2022-12-05
tags: [ Nuget ]
draft: true
---

> 3.x+ 캐시 지우기

nuget locals http-cache -clear

> 2.x 캐시 지우기 (NuGet CLI 3.5 이하)

nuget locals packages-cache -clear

> 글로벌 패키지 폴더 지우기

nuget locals global-packages -clear

> 임시 캐시 지우기

nuget locals temp -clear

> 플러그인 캐시 지우기

nuget locals plugins-cache -clear

> 모든 캐시 지우기

nuget locals all -clear
