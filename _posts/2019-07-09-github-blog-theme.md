---
layout: post
comments: true
title: "Github 개인 블로그에 테마 입히기"
date: 2019-07-10 09:00:00 +0900
categories: github
description: 개인 Github 블로그에 원하는 테마 입히는 것에 대하여
---

## 개인 블로그에 원하는 테마를 입혀 봅시다.

<font size="2em">본 블로그는 macOS Mojave 10.14.5 에서 수행된 작업입니다.</font>

***

진행 순서는 다음과 같습니다.

1. 원하는 테마 다운로드 받기, 클론 받기
3. 받은 테마 적용시키기
4. 불필요한 파일 삭제
4. _posts, _draft 폴더 생성
5. .gitignore 생성
6. Gemfile 수정 및 적용
7. 테스트

***

이전 포스트를 그대로 따라했으면 현재 Repository는 다음과 같은 상태일 것 입니다.

![init-folder-struct]({{site.static_url}}/img/github/github-blog/init-folder-struct.png)

### 1.  원하는 테마 다운로드 받기, 클론 받기

**원하는 테마**를 먼저 찾아보도록 하겠습니다.

[Jekyll Theme](http://jekyllthemes.org/) 로 이동하여 원하는 테마를 골라 보도록 하세요. 정했다면 해당 깃허브로 이동하여 클론을 하도록 합시다.

![jekyll-theme-down]({{site.static_url}}/img/github/github-blog/jekyll-theme-down.png)

1. Download ZIP을 한경우에는 ZIP을 다운받고 압축을 풀어주도록 하세요.
2. URL을 복사한 경우에는 원하는 폴더로 터미널을 열어 `git clone [URL]` 을 해서 클론 해주세요.



### 2. 받은 테마 적용시키기

받은 테마를 `msnodeve.github.io/Coerfolio` 에 붙여넣어 줍시다. 그러면 끝난거에요 !!



### 3. 불필요한 파일 삭제

불필요한 파일들을 삭제하도록 합시다. 굳이 남의것 그대로 쓰면서 할 필요는 없다고 봅니다. 불필요한 파일들은 다음과 같습니다.

- .editorconfig
- .gitattributes
- .github
- /docs
- /test
- CHANGELOG.md
- minimal-mistakes-jekyll.gemspec
- README.md
- screenshot-layouts.png
- screenshot.png



### 4. _posts, _draft 폴더 생성

- _posts : 깃허브에 올라갈 포스트들이 담길 폴더
- _drafts : 깃허브에 올리기전 포스트들이 담길 폴더, 테스트 환경에서 보기가 가능



### 5. .gitignore 생성

[Jeklly gitignore list](https://gist.github.com/bradonomics/cf5984b6799da7fdfafd) 이 사이트를 참고하여 .gitignore를 생성하여 수정하도록 합시다.



### 6. Gemfile 수정 및 적용

Gemfile을 수정하도록 합시다. 없다면 생성해서 작성해주도록 합시다. gem 에 대해서는 다른 포스트를 통해 설명을 더 해보도록 할게요.

```ruby
source "https://rubygems.org"

gem "jekyll", "~> 3.5"
```

이제 Gemfile을 적용시키도록 하겠습니다 !

``` bash
> bundle
```



### 7. 테스트

로컬상태에서 블로그를 확인하기 위해 다음 명령어로 로컬에서 확인해보도록 하겠습니다.

```bash
> jekyll serve
```

여기까지 이렇게 나오게되면 성공한 것 입니다 ! <del>축하합니다.</del>![local-blog]({{site.static_url}}/img/github/github-blog/local-blog.png)



최종적인  폴더 구조는 아래 그림과 같아요.

![folder-struct]({{site.static_url}}/img/github/github-blog/folder-struct.png)