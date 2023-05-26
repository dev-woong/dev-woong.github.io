---
title: TeamCity Parameter 관리 유형
#description: 설명
categories: TeamCity
date: 2022-12-10
tags: [ Parameter, Project, Build Configuration ]
draft: false
---

> TeamCity의 Parameter는 Project, Build Configuration 단위로 설정할 수 있다.

위의 특징을 이용하여 Root Project부터 하위의 SubProject, Build Configuration
등에 각각 별도의 Configuration을 적용할 수 있다.

## Root Project

Root Project는 기본적으로 존재하는 TeamCity의 모든 프로젝트의 최상위 프로젝트로
해당 프로젝트에 Parameter를 설정할 시에 모든 SubProject와 Build
Configuration에서 해당 Parameter를 사용할 수 있다.

추천 범위 : API 토큰, 계정 정보 등

## Sub Project

사용자가 생성하는 모든 프로젝트는 Root Project의 Sub Project이며, Sub Project
내에서도 Sub Project를 생성할 수 있다. 해당 Sub Project에 Parameter 설정 시 해당
프로젝트에 포함된 Sub Project와 Build Configuration에서 해당 Parameter를 사용할
수 있다

추천 범위 : Git Repository, Package Registry 등

## Build Configuration

프로젝트에서 실제 Build 를 수행하는 설정이며 해당 Configuration에서 설정한
Parameter는 해당 Configuration에서만 사용할 수 있다

추천 범위 : 솔루션 Configuration 등
