---
title: "React-app setup with WebStorm."
date: 2018-07-13 14:00:00 -0400
categories: react
---

# React 설정 (on Windows)
## 준비물
+ JetBrains WebStorm.
+ Node.js (https://nodejs.org/ko/)

## 간단한 과정
1. node.js (ver. 8.11.3 LTS)설치 (https://nodejs.org/ko/)
2. CMD > `npm install -g create-react-app`
3. [재부팅 후] WebStorm에서 `React App` 프로젝트 생성
  1. 생성 시 자동으로 react, react-dom, react-scripts 패키지를 설치함 
  2. `Happy hacking!\nDone`이 나오면 완료된 것
4. package.json의 script를 이용하여 테스트 가능함. (단, eject를 하면, Babel 기반으로 돌아가는듯 함, 되돌릴 수 없더라...)
