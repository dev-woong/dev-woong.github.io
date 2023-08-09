---
title: 'GitLab CI - Cache 설정 방법'
description: 'Cache를 통한 GitLab CI Pipeline 속도 향상'
categories: GitLab
date: 2023-07-28
tags: [ GitLab, CI, Cache ]
draft: true
---
# Cache
## Cache란?

 자주 사용하는 데이터나 값을 미리 복사해 놓는 임시 장소

## GitLab 에서의 Cache
- 파이프라인과 작업 간에 공유
- 기본적으로 보호된 브랜치와 보호되지 않은 브랜치 간 공유 불가
- Artifact 보다 우선순위가 높음
- 최대 4개의 서로 다른 캐시 구성 가능

