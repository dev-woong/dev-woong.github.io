---
title: Unity Facebook 로그인 구현
description: Unity 플랫폼에서 Facebook을 이용한 Social 로그인을 구현합니다.
image: resource/Pasted%20image%2020220905011824.png
categories: 
- Unity 

publishdate: 2022-08-31
tags:
- Unity
- SNS
- Facebook
draft: true
---

[Getting Started with the Facebook Unity SDK]([https://developers.facebook.com/docs/unity/gettingstarted](https://developers.facebook.com/docs/unity/gettingstarted))

## 유니티 패키지 설치
### Google Developers - Unity 외부 종속 항목 관리자
[Google Develpers](https://developers.google.com/unity/packages#tools)
![](resource/google%20dev.png)
- Google Developers 페이지에서 위와 같은 항목을 찾아 프로젝트에 Import

### Firebase Unity SDK - FirebaseAuth
[Facebook 로그인과 Unity를 사용하여 인증하기](https://firebase.google.com/docs/auth/unity/facebook-login?hl=ko)
#### Firebase
1. 새 앱 만들기
2. Authentication 등록 > Facebook

https://developers.facebook.com/docs/facebook-login/ios


# 우여곡절 정리부터
1. Firebase든 Facebook SDK든 사용하려고 하는데 Resolver가 동작하지 않았음(Resolver는 상단 구글링크에서 Unity 외부 종속 항목 관리자를 이용함.)
2. 오류를 찾다 보니 cocoapods 오류였고, 자료를 찾아보니 버전의 문제다 뭐다 했으나 일단 ruby의 버전이 2.6.10 이었고, ruby 버전을 업그레이드 하고 오류 메시지에 따라서 설정까지 지정
   https://pie001.github.io/entry/tech-note/0017/
``` bash
brew install rbenv
rbenv install 3.1.2
eval "$(rbenv init -)" < bash_profile 등 파일에 삽입
gem install pods
gem install -n /usr/local/bin cocoapods
```
1. Build Settings 에서 enable bitcode 를 모두 비활성화
2. UnityFramework의 Build Phases > Link Binary With Libraries > `Accelerate.framework` 추가
3. 문제가 또 있다. Unable to install 이라는 오류가 출력되며 iOS에 앱이 절반만 설치되는듯한 증상이 있다.
   https://lxxyeon.tistory.com/147
   빌드 데이터를 Clean으로 날려주고, Provisioning Providerfmf 갱신하고 새로 빌드한 후에야 문제를 해결할 수 있었다.
4. Unity > 상단 Facebook 탭 > Edit Settings > Event Logging > 모두 비활성화 `효과없음`
5. iOS의 경우 Bitcode를 비활성화하는 스크립트 작성, 해당 스크립트는 무조건 Assets/Scripts/Editor 디렉터리에 넣어야 함
```csharp
using UnityEditor;  
using UnityEditor.Callbacks;  
using UnityEngine;  
using UnityEditor.iOS.Xcode;  
  
public class BuildProcessorBitcodeCompilationDisabler  
{  
    [PostProcessBuild(1)]  
    public static void OnPostProcessBuild(BuildTarget buildTarget, string path)  
    {  
        DisableBitcodeOnIos(buildTarget, path);  
    }  
  
    private static void DisableBitcodeOnIos(BuildTarget build_target, string path)  
    {  
        if (build_target != BuildTarget.iOS)  
            return;  
  
        var project_path = path + "/Unity-iPhone.xcodeproj/project.pbxproj";  
  
        var pbx_project = new PBXProject();  
        pbx_project.ReadFromFile(project_path);  
  
        var target = pbx_project.TargetGuidByName("Unity-iPhone");  
        pbx_project.SetBuildProperty(target, "ENABLE_BITCODE", "NO");  
  
        pbx_project.WriteToFile(project_path);  
        Debug.Log("Post Process Build - SUCCESS: Disable bitcode on IOS\n" + "Bitcode setting in Xcode project is updated.");  
    }  
}
```
6. 해당 코드의 `TargetGuidByName()` 메서드 호출 부분을 오류가 발생하는 Target Name으로 치환 (ex: UnityFramework)