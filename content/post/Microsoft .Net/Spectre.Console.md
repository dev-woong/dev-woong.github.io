---
title: Spectre.Console
#description: 설명
categories: Microsoft .Net
date: 2022-12-21
tags: [ Spectre, Console ]
draft: true
---
### Build
- Command A
	- Option 1
	- Option 2

### Deploy
- SFTP
	- -p, --p \<path\>
	- Option 2

yw-tools build ***\*.csproj***  --configuration Unity --configuration Release --deploy nuget --deploy npm


```csharp
[CommandArgument(0, "<firstName>")]
public string FirstName { get; set; }

[CommandArgument(1, "[lastName]")]
public string? LastName { get; set; }
```

CommandArgument에서 '<>' 로 감싸면 필수 입력 항목이 되고 '[]' 로 감싸면 선택적 입력 항목이 된다