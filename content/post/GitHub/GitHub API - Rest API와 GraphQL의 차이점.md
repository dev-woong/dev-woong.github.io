---
title: GitHub API - Rest API와 GraphQL의 차이점
image: resource/thisisengineering-raeng-nyAzMQ6Ejgs-unsplash.jpg
categories: GitHub
date: 2022-08-16
tags:
- Rest API
- GraphQL
draft: true
---

# Summary

### Rest API

#### RestSharp를 이용한 코드 구현

```CSharp
	var client = new RestClient("url");
	client.Timeout = -1;
	var request = new RestRequest(Method.GET);

	IRestResponse response = client.Execute(request);

	var jObject = JObject.Parse(response.Content);
```

읽고, 수정하고, 삭제하는 기능들에 대해 Method를 이용한다. (GET, PUT, POST,
DELETE 등)

### GraphQL API

#### QUERY (Read)

단순히 정보를 읽어올 때에만 사용

#### Mutation (Create, Update, Delete)

읽어들인 정보를 변형하고자 할 때에 사용
