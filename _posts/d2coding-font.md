---
layout: post
title: "[개발환경개선] D2 Coding Font"
date: 2020-07-24 19:00:00 -0400
categories: dev ubuntu coding environment font
---

# D2 Coding Font (\#코딩 폰트)

`EUC-KR`로 인코딩된 소스로 구성된 프로젝트를 수행해야할 일이 생겨, 기존에 쓰던 `utf8` 대상 폰트를 사용할 수 없었다.
코드 및 터미널 텍스트 가독성 향상을 위해 새로운 폰트를 물색하는 와중에, 나눔바른고딕 베이스의 코딩용 폰트인 D2 Coding [\[D2-FONT\]]을 발견했다.
다음은 프로젝트에서 소개하는 해당 글꼴의 설명이다.

## 글꼴 소개 (프로젝트 사이트 [\[D2-FONT\]] 참조)
D2 Coding 글꼴은 나눔바른고딕을 바탕으로 개발자의 코딩을 위해 가독성 및 유사 문자간 변별력 뿐만 아니라 
디자인적으로 한글과의 조화를 고려해 최적화시킨 글꼴입니다. 
D2 Coding 글꼴은 코딩시 유사한 형태의 영문/숫자 뿐만 아니라 한글/특수문자 등에 대한 변별력과 가독성을 강화하였습니다. 
또한 고정폭 글꼴로 제작이 되어 어떤 개발환경에서도 자간과 행간을 유지하도록 디자인되어 있습니다.

## 설치
1. 사이트에서 글꼴을 받은 후 `gnome-font-viewer`로 해당 글꼴을 연다.
  ```bash
  wget https://github.com/naver/d2codingfont/blob/master/D2Coding-Ver1.3.2-20180524.zip
  unzip D2Coding-Ver1.3.2-20180524.zip
  sudo gnome-font-viewer D2Coding/D2Coding-Ver1.3.2-20180524.ttf
  sudo gnome-font-viewer D2Coding/D2CodingBold-Ver1.3.2-20180524.ttf
  ```
2. `gnome-font-viewer`에서 해당 글꼴을 설치한다.

설치된 기본 글꼴명은 `D2Coding Regular`이다.


[\[D2-FONT\]]: https://github.com/naver/d2codingfont
