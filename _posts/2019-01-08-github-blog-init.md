---
layout: post
comments: true
title: "Github에 Jekyll 테마 올리기"
date: 2019-01-08 19:31:00 +0900
categories: github
description: 다운받은 Jekyll 테마를 Github에 올려 블로깅
---

## Jekyll 테마 Github에 올리기

# 1. [지킬(Jekyll)](http://jekyllthemes.org/) 테마 다운로드
### 지킬 다운로드 페이지로 이동하여 마음에 드는 테마 다운로드
![Github Blog2]({{site.static_url}}/img/github/github-blog-init2.png)



# 2. Github에 다운받은 테마 커밋
### 'Git'이 깔려있다는 가정하에 수행 <br> 자신의 Github에 새로운 프로젝트를 생성하면 다음과같은 url을 복사
![Github Blog1]({{site.static_url}}/img/github/github-blog-init1.png)

## 터미널 실행 후 빈 프로젝트 복제
### 원하는 공간에 폴더 생성 후
    # git clone "복사한 url"

### 다운받은 테마를 복제한 폴더 안으로 이동
![Github Blog3]({{site.static_url}}/img/github/github-blog-init3.png)

## 커밋
    # git add .
    # git commit -m "커밋 시 어떤 내용의 코멘트"
    # git push

## 다음 에러 발생 시
![Github Blog4]({{site.static_url}}/img/github/github-blog-init4.png)
### 커밋하고있는 지금 누구인지 구별이 안되기 때문에 발생
    # git config --global user.name "닉네임"
    # git config --global user.email "이메일"
    # git commit -m "커밋 시 어떤 내용의 코멘트"
    # git push

# 3. Github 페이지 설정
## Github >> Setting >> GitHub Pages 이동
![Github Blog5]({{site.static_url}}/img/github/github-blog-init5.png)

### 페이지가 적용 되기까지 최소 30초에서 최대 3분이 걸릴 수 있음<br>홈페이지를 클릭 해보면 다운받은 테마가 개인 블로그로 설정 완료