---
layout: single
title:  "setState() or markNeedsBuild() called during build."
author: 코나인
categories: flutter
tag: [setState, markNeedsBuild, build, flutter]
---

# 원인
build 중에 다시 build가 호출된 경우
setState() or markNeedsBuild called during build 에러 발생


```
======== Exception caught by widgets library =======================================================
The following assertion was thrown building SplashView(dirty):
setState() or markNeedsBuild() called during build.

This Overlay widget cannot be marked as needing to build because the framework is already in the process of building widgets. A widget can be marked as needing to be built during the build phase only if one of its ancestors is currently building. This exception is allowed because the framework builds parent widgets before children, which means a dirty descendant will always be built. Otherwise, the framework might not visit this widget during this build phase.
The widget on which setState() or markNeedsBuild() was called was: Overlay-[LabeledGlobalKey<OverlayState>#03266]
  state: OverlayState#cddac(entries: [OverlayEntry#66131(opaque: true; maintainState: false), OverlayEntry#4d3a0(opaque: false; maintainState: true), OverlayEntry#85523(opaque: true; maintainState: false), OverlayEntry#72b48(opaque: false; maintainState: true), OverlayEntry#c4e82(opaque: false; maintainState: false), OverlayEntry#af09d(opaque: false; maintainState: true)])
The widget which was currently being built when the offending call was made was: SplashView
  dirty
The relevant error-causing widget was: 
  SplashView SplashView:file:///Users/mihyunnoh/work/web_project/firebase_auth/lib/init/route.dart:13:34
```

```
Widget build(BuildContext context) {

  Future.delayed(Duration.zero,(){
    // 여기에서 setState를 해주세요.
  });

  return Scaffold(
    // 기존 UI
  );
}
```

출처 : [https://www.fluttercampus.com/guide/230/setstate-or-markneedsbuild-called-during-build/](https://www.fluttercampus.com/guide/230/setstate-or-markneedsbuild-called-during-build/)