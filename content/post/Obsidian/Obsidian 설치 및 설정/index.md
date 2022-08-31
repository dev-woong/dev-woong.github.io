---
title: "Obsidian 설치 및 설정"
description: Markdown 에디터 Obsidian을 설치하고 세부 설정 방법을 알아봅니다.
image: title.jpg
categories: 
- Unity 
publishdate: 2022-08-16
tags:
- TIL
- Unity
- 2D
- Tilemap
draft: true
---

[고박사의 유니티 노트 [Unity 2D Basic] 05-01. 2D Sprite / Animation](https://www.youtube.com/watch?v=jg4nCHgDCFg&list=PLC2Tit6NyVie46nbdEM00wFoojjRlXIcf&index=8)

## Draw Call & Batches
### Draw Call
- CPU가 GPU에게 Draw 요청하는 것
- 이 값이 낮을수록 앱이 가벼우며 기기에 따라 특정 개수 이상 시 프레임 드랍 발생
- 모바일의 경우 100개를 넘기지 않는 것을 권장 (요즘 기종은 120Hz를 지원)

