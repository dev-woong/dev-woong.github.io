---
title: "[TIL] Sprite, Animation 기초"
description: Unity2D Sprite와 Animation을 공부했습니다.
image: title.jpg
categories: 
- Unity 
publishdate: 2022-08-16
tags:
- TIL
- Unity
- 2D
- Tilemap
draft: false
---

[고박사의 유니티 노트 [Unity 2D Basic] 05-01. 2D Sprite / Animation](https://www.youtube.com/watch?v=jg4nCHgDCFg&list=PLC2Tit6NyVie46nbdEM00wFoojjRlXIcf&index=8)

## Draw Call & Batches
### Draw Call
- CPU가 GPU에게 Draw 요청하는 것
- 이 값이 낮을수록 앱이 가벼우며 기기에 따라 특정 개수 이상 시 프레임 드랍 발생
- 모바일의 경우 100개를 넘기지 않는 것을 권장 (요즘 기종은 120Hz를 지원)

### Batches
- Draw Call 을 포함하는 상위 개념
- Unity 5.0부터 Draw Call 대신 Batches를 기준으로 `Stats`에 렌더링 정보를 표시함
- Batches는 `Mesh`, `Material`, `Shader`, `Draw Call` 등의 정보를 종합적으로 계산함

## Sprite Atlas
- 여러 이미지 파일을 한 장의 텍스처에 모아 두고 사용하는 것
- Unity는 Sprite `Packer`(Legacy)와 `Sprite Atlas`를 제공합니다

### Sprite Atlas를 사용해야 하는 이유
- 2D 게임에서 배경이나 캐릭터, 적 등을 표현하는데 사용되는 이미지 에셋은 매번 렌더링 할 때마다 각 이미지 에셋 별로 1의 Batches 증가
- 예를 들어 게임에 사용되는 캐릭터, 적, 아이템 **모두 다른 이미지를 사용하는 Object가 100**개 있고, 동시에 게임에 등장한다면 Batches 값은 **100**
- 반대로 **동일한 이미지를 사용하는 오브젝트가 100개** 일 때는 Batches 값은 **1**
- Sprite Atlas를 이용해 서로 다른 이미지를 하나의 텍스처에 모아 두고 사용하면 서로 다른 이미지의 오브젝트를 100개 만든다고 해도 Batches 값은 1
 
### Sprite Atlas 사용 시 주의 사항
- 모든 이미지 에셋을 하나의 Sprite Atlas로 묶게 되면 내부의 이미지 하나만 사용해도 해당 Sprite Atlas의 모든 이미지 정보를 불러옴
- 한 화면에 함께 사용되는 것 또는 하나의 오브젝트에서 함께 사용되는 것 처럼 관련이 있는 이미지들을 하나의 Sprite Atlas로 묶어주는 것이 좋음

## Texture Asset
![Texture Asset](post/Unity/Unity2D%20-%20Sprite%20and%20Animation%20Basic/1.png)

### 이미지 분할과 POT(Power of Two) 규격
#### 하나의 이미지 에셋에 여러 장의 그림을 그리고 분할하여 사용하는 이유
![이미지 크기에 따른 메모리 POT 공간 비교](post/Unity/Unity2D%20-%20Sprite%20and%20Animation%20Basic/2.png)
![유사한 성격의 이미지를 모아서 제작된 POT 규격 이미지](post/Unity/Unity2D%20-%20Sprite%20and%20Animation%20Basic/3.png)

- 게임에서 사용되는 텍스처를 제작할 때에는 POT 규격으로 제작해야 함
	- POT(Power of Two) : 텍스처의 가로/세로 사이즈가 2의 제곱
- POT 규격이 아닌 텍스처는 POT 규격으로 변환하기 위해 내부적인 처리를 거치게 되고 이로 인한 메모리 비용 증가
- 보통 게임에 사용되는 이미지는 POT 규격으로 제작될 수 없기 때문에 하나의 POT 규격 텍스처에 여러 장의 이미지(유사한 성격을 가진 이미지)를 넣어서 제작한다.

## Animation
### Animation Asset
- 하나의 애니메이션 동작을 저장하는 파일(걷기, 뛰기, 공격 등)

### 2D Sprite Animation
- Animator Component
- Animator Controller Asset
- Animation Asset

### Animator Controller Asset
- 하나의 오브젝트가 가질 수 있는 애니메이션을 묶어서 관리하는 파일

### Animator Component
- 게임 오브젝트의 애니메이션 재생, 교체 등을 제어하는 역할 수행


[![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fdev-woong.io%2F2022.08.17-001&count_bg=%233D91C8&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=%EC%A1%B0%ED%9A%8C%EC%88%98&edge_flat=true)](https://hits.seeyoufarm.com)
