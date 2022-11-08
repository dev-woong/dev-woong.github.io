---
title: GitHub Actions - .NET 자동화 테스트 구성하기
image: resource/Pasted%20image%2020220919130528.png
categories: GitHub
date: 2022-09-19
tags:
- Actions
- CI
- Test
draft: true
---

## Actions 구성 환경
현재 나의 환경에서는 테스트를 해야하는 `Target Project`와 테스트 케이스를 작성해둔 `Test Project`가 별개의 Repository로 관리되고 있습니다.
테스트는 Test Project Repository 의 Actions에서  `dev` 브랜치로 Push 또는 PR 생성 시 수행할 예정이고, 이 때문에 Target Project를 Actions에서 가져와 사용하려고 합니다

구조는 다음과 같습니다.

- Test Repository
	- **Target Directory (외부에서 가져옴)**
		- Target Project.csproj
		- Target source1.cs
		- Target source2.cs
		- ...
	- **Test Directory **
		- Test Project.csproj
		- Test source1.cs
		- Test source2.cs
		- ...

&nbsp;

> ### 사전 작업
> Actions를 수행하려는 Repository의 설정 > Secrets > Actions 에 `Personal Access Token`을 등록해두어야 합니다.
> 
> [GitHub Personal Access Token 생성하기](GitHub%20Personal%20Access%20Token%20생성하기.md)
> 
> (필자는 PAT 라는 이름으로 등록했습니다.)
> 
> ![](resource/Pasted%20image%2020220919180449.png)

## Actions .yml 스크립트
```yml
name: .NET

on:
  push:
    branches: [ "dev" ]
  pull_request:
    branches: [ "dev" ]

jobs:
  {Job Name(원하는 이름))}:

    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v3
    - name: .NET 설치
      uses: actions/setup-dotnet@v2
      with:
        dotnet-version: 6.0.x
        
    - name: Facts 디렉터리 생성 및 파일 이동
      run: mkdir "Test Directory";
        mv "./Test Project.csproj" "Test Directory";
        mv "./Test source1.cs" "Test Directory";
        mv "./Test source2.cs" "Test Directory";
        
    - name: Core 소스 가져오기
      uses: actions/checkout@master
      with:
        repository: dev-woong/Target-Project
        ref: main
        path: "Target Directory"
        token: ${{ secrets.PAT }}
    
    - name: 종속성 복원
      run: dotnet restore core/Core.csproj;
        dotnet restore facts/core.facts.csproj
      
    - name: 빌드
      run: dotnet build --no-restore core/Core.csproj;
        dotnet build facts/core.facts.csproj --no-restore -f net6.0
      
    - name: 테스트
      run: dotnet test facts/core.facts.csproj --no-restore
```

읽고, 수정하고, 삭제하는 기능들에 대해 Method를 이용한다. (GET, PUT, POST, DELETE 등)



### on - push
repository에 코드가 Push 되는 경우 Actions이 동작합니다

ex) dev 브랜치에 Push하는 경우

```yml
on:
  push:
    branches: [ "dev" ]
...
```

### on - pull_request
repository에 pull_request가 등록되는 경우 Action이 동작합니다

ex) dev 브랜치로 merge 하려는 pull_request가 생성되는 경우

```yml
on:
  pull_request:
    branches: [ "dev" ]
...
```

### runs-on
해당 Action을 수행하는 데에 사용될 운영체제 이미지 이름 

[운영체제 종류 - GitHub Docs](https://docs.github.com/en/actions/using-github-hosted-runners/about-github-hosted-runners#supported-runners-and-hardware-resources)

```yml
jobs:
  {Job Name(원하는 이름))}:

    runs-on: ubuntu-latest
...
```

### Steps