---
layout: post
comments: true
title: "Github 개인 블로그를 위한 설정"
date: 2019-07-10 09:00:00 +0900
categories: github
description: 개인 Github 블로그를 실행하기 위해 설정하기
---

## 개인 블로그를 생성하기 위해 필수 설치 및 설정을 해봅시다.

<font size="2em">본 블로그는 macOS Mojave 10.14.5 에서 수행된 작업입니다.</font>

***

진행 순서는 다음과 같습니다.

1. Ruby 설정
3. Jekyll 설치
4. local에서 띄우기

***

### 1.  Ruby 설정

**RVM, Ruby 설치**

RVM을 설치하도록 합시다.

```bash
> \curl -sSL https://get.rvm.io | bash -s stable
```

Ruby를 설치하도록 합시다.

```bash
> source ~/.rvm/scripts/rvm
> type rvm | head -n 1
rvm is a shell function from /Users/seok/.rvm/scripts/cli
위와 비슷한 문구가 나온다면 성공

> rvm install 2.5.0
```

업데이트를 하고싶은 분들께서는 다음 작업을 진행해주세요.

```bash
> rvm get head
> rvm reload
> rvm get latest
```

### 2. Jekyll 설치

jekyll 과 bundler 를 설치합시다.

```bash
> sudo gem install jekyll bundler
```

이렇게 하면 설치가 끝나게 됩니다 !

### 3. local에서 띄우기

Github Page를 사용하기위해 이전 포스트에서 생성한 `msnodeve.github.io/Coerfolio` Repository로 이동합니다.

```bash
~/Desktop/seok/git/Coerfolio master
> jekyll serve

다음과 같은 에러가 뜬다면
Could not find proper version of jekyll (3.8.5) in any of the sources
Run `bundle install` to install missing gems.

> bundle install
> jekyll serve
아래와 비슷한 문구가 뜬다면 성공
Configuration file: none
            Source: /Users/seok/Desktop/seok/git/Coerfolio
       Destination: /Users/seok/Desktop/seok/git/Coerfolio/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
                    done in 0.021 seconds.
 Auto-regeneration: enabled for '/Users/seok/Desktop/seok/git/Coerfolio'
    Server address: http://127.0.0.1:4000
  Server running... press ctrl-c to stop.
[2019-07-10 20:49:39] ERROR `/favicon.ico' not found.
```

이제 크롬을 켜서 localhost:4000으로 접속을 해보도록 합시다.

![local]({{site.static_url}}/img/github/github-blog/local.png)

이렇게하면 로컬에서 접속을 성공하게 되었습니다. <del>축하드립니다 !</del>