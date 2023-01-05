---
title: Xml.Linq - Descendants
#description: 설명
categories: Microsoft .Net
date: 2023-01-05
tags: [ XML, LINQ, Descendants ]
draft: false
---
> XML Element 컬렉션을 반환하는 메서드

## Overload
- Descendants() : XElement 컬렉션 반환
- Descendants(XName) : XName과 일치하는 XElement 컬렉션 반환

## 사용법
다음 예제는 .NET(C#) 프로젝트에서 참조하고 있는 Nuget 패키지 `morelinq`의 버전을 확인하는 예제입니다.
``` dotnet
var xml_document = XDocument.Load(<.csproj 파일 경로>, LoadOptions.SetBaseUri);

var version = xml_document.Descendants("PackageReference")  
    .Where(x => x.Attribute("Include")!.Value == "morelinq")  
    .Select(x => x.Attribute("Version")!.Value)  
    .First();
```