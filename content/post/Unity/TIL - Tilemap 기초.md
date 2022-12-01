---
title: "[TIL] Tilemap 기초"
description: Unity2D Tilemap을 공부했습니다.
image: resource/Pasted%20image%2020220905010034.png
categories: 
- Unity 
date: 2022-08-17
tags:
- TIL
- 2D
- Sprite
- Animation
draft: false
classification: public
---

[고박사의 유니티 노트 [Unity 2D Basic] 06-01. 2D Tilemap Editor](https://www.youtube.com/watch?v=9Y0bUhwxRyk&list=PLC2Tit6NyVie46nbdEM00wFoojjRlXIcf&index=10)

## Tilemap Editor
### Tilemap Palette
- Tilemap 오브젝트에 배치할 때는 Tile Asset들을 등록해두는 저장소
- 팔레트에 있는 Tile Asset을 여러 속성에 따라 배치하거나 삭제할 수 있음

### Grid 오브젝트
- 자식으로 배치되는 Tilemap 오브젝트들을 관리하는 역할
- Cell Layout, Cell Swizzle 정보를 이용해 배치되는 맵의 방식을 Rectangle, Hexagon, Isometric, Isometric Z As Y 등으로 설정할 수 있음

### Tilemap 오브젝트
- Tile Asset을 배치하는 공간으로 실제 게임에 보여지는 타일 형태의 월드
- Grid 오브젝트의 자식으로 여러 개의 Tilemap 오브젝트 등록 가능 (Layer 구분)

![상단 메뉴 > Windows > 2D > Tile Palette](resource/1.png)
![Tile Palette 메뉴](resource/2.png)

강의와 현재의 편차가 있는 듯 한데, 해당 차이점 등에 대해 이해 후 다시 포스팅 하겠습니다.

[![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fdev-woong.io%2F2022.08.17-02&count_bg=%233D91C8&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=%EC%A1%B0%ED%9A%8C%EC%88%98&edge_flat=true)](https://hits.seeyoufarm.com)