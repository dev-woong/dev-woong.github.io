---
title: MacOS .NET 패키징 및 배포 과정 정리
categories: MacOS
date: 2022-10-01
tags:
- XCode
- Beta
- Bug
draft: true
---

제목에 적어둔 오류를 제외하고도 다양한 오류가 많이 발생했습니다

다음은 이 문제를 해결하기 위해 시도한 방법을입니다

## 오류 및 해결 방법
### Beta Could not load the framework
#### Xamarin-iOS 패키지 버전 업그레이드
[[Meta] Xcode 14.0 Support #15954)](https://github.com/xamarin/xamarin-macios/issues/15954)
해당 이슈에서는 Xamarin-iOS의 패키지를 16버전 이상을 설치하도록 안내하고 있음
-> Xamarin-iOS 업그레이드 시 해당 오류는 사라짐

### Failed to install application on device 'Device Name': ~~ mlaunch[1134:1234] Requested but did not find extension point with identifier Xcode