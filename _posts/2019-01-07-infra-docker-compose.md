---
layout: post
comments: true
title: "Docker-compose 설치"
date: 2019-01-08 00:18:00 +0900
categories: infra
description: CentOS7 에서의 Docker-compose 설치 방법
---

# Docker 설치

## 옛 버전 삭제
    # yum remove docker \
                 docker-common \
                 docker-selinux \
                 docker-engine

### 서비스를 내리고 docker를 삭제해도 /var/lib/docker/ 폴더는 지워지지 않고 여기에 기존 데이터가 모두 남아있다.

## 필수 패키지 설치
    # yum install -y yum-utils device-mapper-persistent-data lvm2
    docker repo를 등록한다.
    # yum-config-manager \
                --add-repo \
                https://download.docker.com/linux/centos/docker-ce.repo
    yum package를 업데이트
    # yum makecache fast


## 다운로드
    # yum install docker-ce

## 실행
    # systemctl start docker
    # systemctl enable docker
    # docker --version
    Docker version 17.06.0-ce, build 02c1d87

# Docker-compose 설치

## 다운로드
    # curl -L https://github.com/docker/compose/releases/download/1.14.0/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose

## 실행 권한 부여
    # chmod +x /usr/local/bin/docker-compose
    설치 확인
    #docker-compose --version
    docker-compose version 1.14.0, build 1719ceb

### 설치 완료