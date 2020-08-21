---
layout: post
title: "[ToyProject/환경구축] 0. Ubuntu에 nodejs 설치하기."
date: 2020-08-21 20:00:00 -0400
tags: [nodejs, vue, express, ubuntu, yarn, environment]
categories: toy-project environment
---

## Introduction.
이 글은 vue.js + express.js + docker를 이용한 Single Page Application (SPA) ToyProject를 위하여 작성되는 시리즈 중 첫 번째로 진행한 포스팅입니다.


물론, 이 글이 언제까지 작성될지는 모르지만 최초 환경 구축부터 ToyProject의 구동까지 진행할 예정입니다.


이 글에서는 많이 쓰이는 Linux 환경인 Ubuntu에 nodejs를 설치하는 방법을 설명하겠습니다.


### 참고 사항
본격적으로 글을 쓰기 이전에 한 가지 참고 사항을 알려드립니다.


이 글은 공식 문서가 아니므로 nodejs 바이너리 배포에 관한 상세한 설명을 확인하기 위해서는 공식 github 저장소 (https://github.com/nodesource/distributions)를 참조하시길 바랍니다.


## Ubuntu 상의 nodejs 설치
### 개발 환경
이 글에서 다루는 nodejs 설치 환경은 다음과 같습니다.
+ OS: Ubuntu 18.04 LTS
+ CPU: Intel Core i7 9th CPU (amd64)


### nodejs 버전 확인
설치에 앞서 다음 링크에서 설치할 nodejs의 버전을 확인하고, 자신의 환경에 맞는 버전을 설치하시길 바랍니다. 


nodejs는 메이저 버전을 변경하기 힘들기 때문에 많은 부분을 고려하시길 바랍니다.


nodejs 릴리스 정보 관련 링크: https://nodejs.org/ko/about/releases/


저는 현재 버전(2020.08.21 기준)인 `v14`를 설치하도록 하겠습니다.


### nodejs 바이너리 설치
Ubuntu에서의 nodejs 바이너리 설치는 `curl`을 통해 `PPA`를 갱신한 후, 설치한다.

#### `curl` 설치 (미설치 시)
```bash
sudo apt-get install curl
```

#### `PPA` 갱신 (nodejs `v14` 기준)으로 최신 nodejs 설치 정보를 획득
```bash
curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -
```
상기 url에서 `setup_14.x` 부분을 자신이 원하는 버전으로 변경한다면 (예, `v12`: `setup_12.x`) 자신이 원하는 nodejs 버전을 설치할 수 있습니다.


#### 시스템에 nodejs 설치
```bash
sudo apt-get install -y nodejs
```

#### nodejs / npm 버전 확인
```bash
node -v;
npm -v;
```

버전 정보를 확인하여 문제가 없다면, nodejs와 npm의 설치는 끝난 것입니다!


### yarn 설치하기.
nodejs와 관련된 별 다른 설정을 하지 않은 환경이라면, PPA 갱신 후에 다음과 같은 안내가 있었을 것입니다.
```bash
## Run `sudo apt-get install -y nodejs` to install nodejs 14.x and npm
## You may also need development tools to build native addons:
     sudo apt-get install gcc g++ make
## To install the Yarn package manager, run:
     curl -sL https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
     echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
     sudo apt-get update && sudo apt-get install yarn
```
맨 위의 nodejs 설치는 진행했지만 이후의 명령어들은 수행하지 않았었습니다.


이 부분에서 설치를 요구하는 것은 두가지입니다.
1. `native addon` 빌드관련 의존성 패키지.
2. Package manager `yarn`.

#### `native addon` 빌드관련 의존성 패키지 설치
`native addon`의 빌드에 필요한 의존성이 갖춰지지 않는 것을 방지하기 위해 `gcc g++ make`와 더불어 `build-essential`을 설치하시길 바랍니다.


만약, 각 의존성 패키지의 현재 버전을 유지하길 원하신다면, 버전을 선택적으로 설치하시길 바랍니다. 아래 예시는 현재 최신 버전을 설치하는 방법입니다.

```bash
sudo apt-get update
sudo apt-get install build-essential gcc g++ make
```

#### `yarn` 설치
nodejs에는 npm이라는 패키지 관리자가 존재합니다. 그러나 공식 nodejs 바이너리 설치시에도 안내하듯 `yarn`이라는 패키지 매니저를 따로 사용하게 됩니다.


굳이 `npm` 대신 `yarn`을 쓰는 이유는 현재까지는 "빠른 성능"이라고 합니다. 


안내받은 대로 `yarn`을 설치합니다. `PPA`를 등록하고, 설치하는 단계로 이루어져 있습니다.
```bash
curl -sL https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt-get update && sudo apt-get install yarn;
```
설치 후, `yarn`이 잘 설치되었는지 확인합니다.
```bash
yarn -v
```
