---
layout: post
comments: true
title: "Github 개인 블로그 생성"
date: 2019-07-09 19:21:00 +0900
categories: github
description: 개인 Github에 웹 페이지 띄우기
---



## 개인 Github에 웹 페이지를 띄워봅시다.

<font size="2em">본 블로그는 macOS Mojave 10.14.5 에서 수행된 작업입니다.</font>

<br><br>

진행 순서는 다음과 같습니다.

1. Github에 새로운 Repository를 생성하기
2. 생성한 Repository에 index.html 작성해서 커밋
3. 도메인 할당
4. 접속

<br>

### 1. Github에 새로운 Repository를 생성

다음과 같이 개인 깃허브에서 <font color="red"> Repositories > New </font> 를 클릭해 주세요.

![new]({{site.static_url}}/img/github/github-blog/new.png)

다음으로 원하는 이름으로 생성을 해주도록 합시다. **Repository name**을 지을때 주의 사항 !

자신의 [사용자 이름] / [사용자 이름].github.com 으로 지정해주면 실제 도메인이 [사용자 이름].github.com으로 사용이 가능합니다.

그렇지 않으면 저와 같이 [사용자 이름].github.com/Repository name으로 접속하셔야 합니다.(저는 지금 이미 있는 Repository name을 사용하려 하고있기에 경고가 뜹니다.)

그외 설정을 해주시고, Create repository을 클릭해 새로운 레포를 생성시키도록 합시다.

![create]({{site.static_url}}/img/github/github-blog/create.png)

### 2. 생성한 Repository에 index.html 작성해서 커밋

다음으로는 이제 index.html을 작성해 커밋을 해보도록 하겠습니다.

먼저 새로만든 Repository를 local 컴퓨터로 clone 하도록 하겠습니다.

```bash
~/Desktop/seok/git
> git clone https://github.com/msnodeve/Coerfolio.git
> cd Coerfolio

~/Desktop/seok/git/Coerfolio master
> vi index.html
```

여기서 이제 index.html을 작성하도록 하겠습니다.

```html
<html>
    <head>
        <title>Hello</title>
    </head>
    <body>
        Hello World!
    </body>
</html>
```

그리고 이제 작성된 index.html을 커밋 시키도록 하겠습니다.

```bash
~/Desktop/seok/git/Coerfolio master
> git add .
> git commit -m "초기 index.html 작성"
> git push
```

### 3. 도메인 할당

커밋을 완료했으면, 제 Repository의 도메인을 할당해주도록 하겠습니다.

다음과 같이 개인 깃허브에서 <font color="red"> Repositories > Settings </font> 를 클릭해 주세요.

![setting1]({{site.static_url}}/img/github/github-blog/setting1.png)

그리고 이제 스크롤을 아래로 내려다 보면 GitHub Pages 존이 보이실 겁니다. 여기서 **Source** 가 **master branch** 로 되어있는지 확인하고 (되어있지 않다면 바꿔주세요), 최대 5분 가량 기다려주세요. 그러면 "Your site is published at https://msnodeve.github.io/Coerfolio/" 라는 문구가 초록색 배경에 뜰 겁니다.

![setting2]({{site.static_url}}/img/github/github-blog/setting2.png)

### 4. 접속

이제 클릭해서 접속해 볼까요?

![init-index]({{site.static_url}}/img/github/github-blog/init-index.png)

위 상태가 되면 성공하신겁니다. 간단하게 생성했습니다!