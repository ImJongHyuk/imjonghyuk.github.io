---
layout: post
title: "[ToyProject/환경구축] 0. Ubuntu에 NodeJS 설치하기."
date: 2020-08-21 20:00:00 -0400
tags: [node.js, vue, express, ubuntu, environment]
categories: toy-project environment
---

## Introduction.
이 글은 vue.js + express.js + docker를 이용한 Single Page Application (SPA) ToyProject를 위하여 작성되는 시리즈 중 첫 번째로 진행한 포스팅입니다.


물론, 이 글이 언제까지 작성될지는 모르지만 최초 환경 구축부터 ToyProject의 구동까지 진행할 예정입니다.


이 글에서는 많이 쓰이는 Linux 환경인 Ubuntu에 Node.js를 설치하는 방법을 설명하겠습니다.


### 참고 사항
본격적으로 글을 쓰기 이전에 한 가지 참고 사항을 알려드립니다.


이 글은 공식 문서가 아니므로 Node.js 바이너리 배포에 관한 상세한 설명을 확인하기 위해서는 공식 github 저장소 (https://github.com/nodesource/distributions)를 참조하시길 바랍니다.


## Ubuntu 상의 Node.js 설치
### 개발 환경
이 글에서 다루는 Node.js 설치 환경은 다음과 같습니다.
+ OS: Ubuntu 18.04 LTS
+ CPU: Intel Core i7 9th-Gen CPU (amd64)


### Node.js 버전 확인
설치에 앞서 다음 링크에서 설치할 Node.js의 버전을 확인하고, 자신의 환경에 맞는 버전을 설치하시길 바랍니다. 


Node.js는 메이저 버전을 변경하기 힘들기 때문에 많은 부분을 고려하시길 바랍니다.


Node.js 릴리스 정보 관련 링크: https://nodejs.org/ko/about/releases/


저는 현재 버전(2020.08.21 기준)인 `v14`를 설치하도록 하겠습니다.


### Node.js 바이너리 설치
Ubuntu에서의 Node.js 바이너리 설치는 `curl`을 통해 `PPA`를 갱신한 후, 설치한다.

#### `curl` 설치 (미설치 시)
```bash
sudo apt-get install curl
```

#### `PPA` 갱신 (Node.js `v14` 기준)으로 최신 Node.js 설치 정보를 획득
```bash
curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -
```

#### 시스템에 Node.js 설치
```bash
sudo apt-get install -y nodejs
```

#### Node.js / npm 버전 확인
```bash
nodejs -v;
npm -v;
```

#### `build-essential` 설치
버전을 확인해서 알 수 있었겠지만, `PPA`를 통해 Node.js를 설치하면 npm도 함께 설치됩니다.


추후 `npm install`시 빌드에 필요한 의존성이 갖춰지지 않는 것을 방지하기 위해 `build-essential`을 설치하시길 바랍니다.
```bash
sudo apt-get update
sudo apt-get install build-essential
```
