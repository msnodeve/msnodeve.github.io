---
layout: post
comments: true
title: "Mac iTerm2"
date: 2018-10-23 16:20:00 +0900
categories: macos
description: Mac iTerm2 멋진 터미널 만들기
---

# **멋진 터미널 만들기**


## [iTerm2](https://www.iterm2.com/downloads.html) 설치
[iTerm2 다운로드 페이지](https://www.iterm2.com/downloads.html)에 접속, iTerm2를 설치
![iTerm2 Download Page]({{site.static_url}}/img/macOS/iTerm2_download_site.png)


# [HomeBrew](https://brew.sh) 설치
![HomeBrew Download Page]({{site.static_url}}/img/macOS/HomeBrew_img.png)
### **HomeBrew 공식 홈페이지는** [https://brew.sh](https://brew.sh)
    /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

# Zsh 설치
    brew install zsh


# OhMyZsh 설치
### 설치시 mac잠금 해제 암호를 물어본다, 입력해도 *이 뜨지않으니 그냥 입력 후 엔터
    sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

# Oceanic Next iTerm 색 테마 입히기

<div style="text-align: center;">
<img src="/img/macOS/Oceanic_color_iterm.png">
</div>

## [master.zip](https://github.com/mhartington/oceanic-next-iterm/archive/master.zip)을 다운로드 후 더블클릭

<div style="text-align: center;">
<img src="/img/macOS/Oceanic_next1.png">
</div>

## iTerm2 > Preferences... > 클릭

<div style="text-align: center;">
<img src="/img/macOS/Oceanic_next2.png">
</div>

## Profile > Default > Colors > Color Presets... > Oceanic-Next > 클릭 후 완료

<div style="text-align: center;">
<img src="/img/macOS/Oceanic_next3.png">
</div>


# Agnoster 테마 설치
<div style="text-align: center;">
<img src="/img/macOS/agnoster.png">
</div>

## 명령어 입력후 10번째 줄을 다음과 같이 입력
    vi ~/.zshrc

    ZSH_THEME="agnoster"

<div style="text-align: center;">
<img src="/img/macOS/agnoster.zshrc.png">
</div>

## Ubuntu Mono derivative Powerline 폰트 설치 & 설정
### [Ubuntu_Mono_derivative_Powerline.ttf](https://beomi.github.io/others/Ubuntu_Mono_derivative_Powerline.ttf)를 다운

### iTerm2 > Preferences... > 클릭

<div style="text-align: center;">
<img src="/img/macOS/Oceanic_next2.png">
</div>

### Profile > Default > Text > Change Font > Ubuntu Mono derivative > 클릭 후 완료
<div style="text-align: center;">
<img src="/img/macOS/iTerm2_Ubuntu_Mono1.png">
</div>

# zsh-syntax-highlighting 설치
## 아래 두줄을 터미널에 입력
    git clone https://github.com/zsh-users/zsh-syntax-highlighting.git
    echo "source ${(q-)PWD}/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> ${ZDOTDIR:-$HOME}/.zshrc

# 수고하셨습니다.
### 이제 iTerm2를 완전히 종료한 후에 다시 실행하여 멋진 터미널을 이용해 보세요!