---
title: TeamCity Custom NPM 레지스트리 연결하여 배포하기
image: resource/Pasted%20image%2020221130155426.png
categories: TeamCity
date: 2022-11-30
tags: [ NPM, Custom Registry, Registry ]
draft: false
---
Verdaccio를 이용하여 생성된 NPM 서버에 빌드, 테스트를 거쳐 Unity Package를 배포하기 위해 TeamCity에서 NPM 인증을 수행, NPM 레지스트리에 등록된 계정만 Publish가 가능하다고 가정한다.

## NPM Connection 추가
1. Project > 우측 상단 Edit Project 클릭
![](../../resource/스크린샷%202022-11-30%20오후%203.17.37.png)
2. Connections > Add Connection 클릭
![](../../resource/스크린샷%202022-11-30%20오후%203.18.30.png)
3. NPM Registry 선택 > 내용 작성 후 Save 클릭
![](../../resource/Pasted%20image%2020221130151952.png)
	- Display Name : 해당 Connection을 나타내는 이름
	- Scope : 패키지 범위 지정자
	- Registry URL : NPM 레지스트리 주소
	- Access Token : `npm login` 키워드로 로그인 시 기본적으로 각 사용자 디렉터리의 [.npmrc](https://outofbedlam.gitbooks.io/npm-handbook/content/config/npmrc.html) 파일에서 확인 가능

## Token Parameter 추가
1. Build Configuration > Parameters > Add new parameter
   ![](../../resource/Pasted%20image%2020221130153138.png)
2. 내용 작성
   ![](../../resource/Pasted%20image%2020221130153411.png)
	- Name : Parameter ID, 해당 Parameter를 호출 할 때에 사용됨
	- Kind : 이 예제에서는 Configuration parameter 사용
	- Value : 위에서 NPM Connection 생성 시 사용한 Access Token
3. Spec > Edit 클릭 > Display `hidden` / Type `password`
   ![](../../resource/Pasted%20image%2020221130153643.png)
4. Save

## Build Step 작성(Powershell)
```powershell
cd "<NPM 패키지 파일 경로>"

# 레지스트리 접근 설정
npm config set "//http://<레지스트리 주소:포트>/:_authToken" "%<TOKEN Parameter 이름>%"
npm publish --registry "http://<NPM 레지스트리 주소:포트>"
```

## 마무리
Build Configuration을 동작시켜 Registry에 정상적으로 Publish 되었는지 확인