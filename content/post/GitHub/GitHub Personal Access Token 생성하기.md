---
author: "Dev-Woong"
title: "GitHub Personal Access Token 생성하기"
date: "2022-08-09"
description: "API 등에서 GitHub를 관리/제어할 수 있는 Personal Access Token 발급 방법을 알아봅니다."
tags:
- "Personal Access Token"
- "Rest"
categories: "GitHub"
image: "resource/github.jpg"
draft: false
---

## Access Token 이란?

> GitHub에서는 HTTPS 에서의 ID/Password 인증 방식을 금지하고 Access Token 인증
> 방식으로 전환되었습니다.
>
> Personal Access Token은 HTTPS 인증 시 Git의 암호 대신 사용하거나 API를
> 인증하는 데 사용할 수 있는 값 입니다.

---

## Personal Access Token 생성

### GitHub 로그인

[GitHub Login](https://github.com/login) 페이지에서 로그인합니다.

### 설정 페이지 이동

![사용자 아이콘 > Settings](resource/1%203.png)
![Developer Settings](resource/2%203.png)

GitHub 홈 화면에서 우측 상단 사용자 아이콘을 클릭 후 하단의 `Setting`를 클릭하면
설정 페이지로 이동됩니다.

이동 후, 좌측 메뉴 최하단의 `Developer settings` 를 클릭합니다.

![Personal Access Token > Generate new token](resource/3%203.png)

Developer Setting 화면에서 좌측의 `Personal access tokens`를 클릭하고
`Generate new token`을 클릭합니다.

(작성자는 기존에 생성한 토큰이 한 개 있는 상태이므로 표시되는 화면이 다를 수
있습니다.)

![토큰 이름, 만료기간, 권한 설정 > Generate token](resource/4%202.png)

- 토큰 이름 : 자유롭게 작성
- 만료 기간 : 자유롭게 선택하거나, 만료되지 않도록 설정
- 토큰 권한 : git 로그인 또는 API 사용 시에 필요한 만큼의 권한 할당

### Token 생성 완료

![Personal Access Token 발급 완료](resource/5%202.png)

이제 생성한 토큰으로 HTTPS Url을 이용한 Clone 요청이나, GitHub의 여러
API(RestFul, GraphQL)등을 이용할 수 있습니다.

[![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fdev-woong.io%2F2022.08.11-01&count_bg=%233D91C8&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=%EC%A1%B0%ED%9A%8C%EC%88%98&edge_flat=true)](https://hits.seeyoufarm.com)
