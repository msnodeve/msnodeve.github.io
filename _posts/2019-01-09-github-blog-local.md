---
layout: post
comments: true
title: "나만의 [Github] 블로그 만들기"
date: 2019-01-09 17:38:00 +0900
categories: github
description: \[Jekyll\] 윈도우에서 지킬 설치 및 블로그 생성
---

### \[Jekyll\] 윈도우에서 지킬 설치 및 블로그 생성

### 지킬 기반 블로그를 운영하기에 앞서 블로그 구성 및 기능을 변경/추가 할때, 깃허브 상에서 수정하지 않고, 로컬에서 미리 적용해보고 블로그를 운영할 수 있음 / 리눅스, 맥 기반에서는 이러한 운영을 손쉽게 할 수 있지만, 윈도우 환경에서는 별다른 조치를 해주어야 함 

# 1. [루비(Ruby)](https://rubyinstaller.org/downloads/) 설치
### 다운로드 페이지로 이동하여 아래와 사진과 같은 파일 다운로드
![Github Blog1]({{site.static_url}}/img/github/github-blog1.png)

# 2. 지킬(Jekyll) 설치
### 윈도우 검색창에 'Ruby' 검색
![Github Blog2]({{site.static_url}}/img/github/github-blog2.png)

### 콘솔창에서 [gem] 명령어를 통해 지킬과 실행에 필요한 패키지들을 설치
    > gem install jekyll
    > gem install minima
    > gem install bundler
    > gem install jekyll-feed
    > gem install tzinfo-data

# 3. Local에서 블로그 실행하기

### 루비 콘솔창에서 [이전 포스팅](https://msnodeve.github.io/github/2019-01-08-github-blog-init/)에서 생성한 블로그의 깃허브 저장소와 연동된 폴더로 이동
    > cd C:\User\Seok\...\msnodeve.github.io
    인코딩 에러 발생시 다음의 코드 실행
    > chcp 65001
    지킬 실행
    > bundle exec jekyll serve

## 브라우저를 열어 (http://127.0.0.1:4000)으로 접하면 로컬상에서 블로그가 실행 되는 것을 확인 할 수 있다.
![Github Blog3]({{site.static_url}}/img/github/github-blog3.png)