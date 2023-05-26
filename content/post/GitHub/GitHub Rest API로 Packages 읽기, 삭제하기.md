---
title: GitHub Rest API로 Packages 읽기, 삭제하기
#description: 설명
categories: GitHub
date: 2022-12-06
tags: [ packages, Rest, API  ]
draft: true
---

## 패키지 목록 읽기

```
curl -H "Accept: application/vnd.github+json" -H "Authorization: Bearer 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" -H "X
-GitHub-Api-Version: 2022-11-28" https://api.github.com/user/packages/nuget/YW.PC-Core.Data/versions | jq -c '.[].name'
```

## 지정한 버전과 맞는 패키지의 id 가져오기

```
curl -H "Accept: application/vnd.github+json" -H "Authorization: Bearer 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" -H "X -GitHub-Api-Version: 2022-11-28" https://api.github.com/user/packages/nuget/YW.PC-Core.Data/versions | jq -c '.[]|select(.name=="1.0.1")|.id'
```

## 지정한 버전의 패키지 삭제하기

```
curl -X DELETE -H "Accept: application/vnd.github+json" -H "Authorization: Bearer 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" -H "X-GitHub-Api-Version: 2022-11-28" https://api.github.com/user/packages/nuget/YW.PC-Core.Data/versions/56445024
```
