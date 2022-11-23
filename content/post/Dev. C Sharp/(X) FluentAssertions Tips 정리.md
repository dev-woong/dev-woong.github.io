---
title: FluentAssertions Tips 정리
image: 
categories: .NET/CSharp
date: 2022-08-17
tags:
- 비동기
- Async
- Await
draft: true
---
[FluentAssertions - Tips](https://fluentassertions.com/tips/#general-tips)

FluentAssertions는 Test Case 작성 시 값에 대한 검증을 쉽게 할 수 있도록 도와주는 라이브러리입니다.

공식 홈페이지에서 제공한 Tips를 이용하여 검증 코드를 더욱 명확하게 작성할 수 있도록 해봅시다.

## Collection (List, Array ... )
배열, 리스트 등의 컬렉션 타입 변수를 검증하는 코드입니다.
```ad-summary
123
```

### NotBeEmpty()
```
actual.Should().NotBeEmpty();
```

### Tilemap Palette
- Tilemap 오브젝트에 배치할 때는 Tile Asset들을 등록해두는 저장소
- 팔레트에 있는 Tile Asset을 여러 속성에 따라 배치하거나 삭제할 수 있음

### Grid 오브젝트
- 자식으로 배치되는 Tilemap 오브젝트들을 관리하는 역할
- Cell Layout, Cell Swizzle 정보를 이용해 배치되는 맵의 방식을 Rectangle, Hexagon, Isometric, Isometric Z As Y 등으로 설정할 수 있음
