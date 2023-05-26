---
title: Docker Hub에 Container 변경사항 저장(commit)
image: ../../resource/Pasted%20image%2020221109173529.png
categories: Server
date: 2022-11-09
tags:
- Docker
draft: false
---

## 컨테이너 정보 확인

> docker ps -a

예시: ![](../../resource/Pasted%20image%2020221109163134.png)

## Docker Hub 이미지 정보 확인

Docker Hub에서 Repository를 아직 생성하지 않은 경우 다음 글을 참고하여 생성 후
진행 [Docker Hub Repository 생성](Docker%20Hub%20Repository%20생성.md)
![](../../resource/Pasted%20image%2020221109162842.png)

## Commit

Docker Hub에 생성한 Repository 이름에 맞춰 Commit 이미지 생성 해당 명령 실행 시
컨테이너의 상태가 저장된 이미지가 생성됨

`docker commit <container id> <id>/<repository>:<tag name>`

> 예시 : `docker commit 5b9aeb9f628e agio96/yunwoo-tc:221109`

## Login

Docker Hub를 이용할 권한을 얻기 위해 cli에서 로그인

`docker login` ![](../../resource/Pasted%20image%2020221109165501.png)

## Push

Commit을 통해 생성된 이미지를 Docker Hub에 Push

`docker push <id>/<repository>:<tag name>`

> 예시 : `docker push agio96/yunwoo-tc:221109`

## 완료

컨테이너의 변경사항이 저장된 이미지가 Docker Hub Repository에 tag로 추가됨
![](../../resource/Pasted%20image%2020221109165835.png)
