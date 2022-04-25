---
layout: single
title:  "React Virtual DOM"
author: 코나인
categories: React
tag: [React, Virtual DOM]
---


브라우저는 UI를 나타내기 위해 DOM이라는 개념을 씁니다. DOM은 JS로 수정할 수 있게 만들어진, UI의 객체 지향 표현입니다. DOM은 브라우저가 UI를 그리기 위한 정보가 트리 형태로 저장된 데이터입니다.

<br />
<br />

React의 가상 DOM은 실제 DOM에 기반하여 만들어집니다. 실제 DOM은 브라우저가 화면을 그리는데 필요한 모든 정보가 들어있어 이것을 조작하는 작업은 무겁습니다. 그래서 React는 실제 DOM의 변경을 빠르게 파악하고 적용하기 위해서 내부적으로 가상 DOM을 만들어 관리합니다. 가상 DOM은 DOM의 메타데이터 또는 요약본이라고 할 수 있습니다.

<br />
<br />

React는 성능 향상을 위해 실제 렌더링된 UI를 JS 객체로 따로 관리합니다. 왜냐하면 실제 DOM의 노드를 생성하거나 접근하는 것이 JS 객체로 표현된 트리 노드(가상 DOM)를 생성하거나 접근하는 것에 비해 느리기 때문입니다.(메모리의 사용량은 늘어남.)

<br />
<br />

기존에는 화면을 수정하려면 jQuery나 document.getElementById 등을 통해서 DOM 노드를 검색/수정 또는 해당 위치에 노드를 추가/삭제했는데, 리얼 DOM의 노드를 수정하는 것은 무거운 작업이기에 Virtual DOM이 등장했습니다.
