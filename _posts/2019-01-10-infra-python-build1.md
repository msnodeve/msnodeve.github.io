---
layout: post
comments: true
title: "Flask Python 개발환경 구축"
date: 2019-01-10 21:25:00 +0900
categories: infra
description: Flask-Python 개발 환경 구축
---

# Flask-Python 개발 환경 구축하여 배포까지(1)

### 포스팅에 사용 될 것
    Docker, Docker-compose, Python3.6, Flask, Mysql

## *Docker*

### Dockerfile 작성
    FROM centos:7
    MAINTAINER msnodeve <msnodeve@gmail.com>
    ENV LANG=en_US.utf8 \
	    LC_ALL=en_US.utf8
    RUN yum install -y http://centos7.iuscommunity.org/ius-release.rpm && \
	    yum install -y vimclear python36u python36u-pip python36u-devel && \
	    pip3.6 install pipenv
    VOLUME /code
    VOLUME ["/code"]
    # FROM : 어떤 이미지를 기반으로 할지 설정
    # MAINTAINER : 메인 테이너 정보
    # ENV : 환경 변수 설정
    # RUN : Shell 스크립트 혹은 명령을 실행
    #       이미지 생성 중에는 사용자가 입력 받을 수 없으므로 -y 옵션을 사용
    # VOLUME : 호스트(local내부)와 공유할 디렉터리 목록

### Makefile 작성
    build:
	    docker build -t mydocker:latest .

    run: build
	    docker run --privileged -d -p 6000:6000 -v $(pwd):/code --name mydocker mydocker:latest sbin/init

    stop:
	    docker stop mydocker

    remove: stop
    	docker rm mydocker

    .PHONY:
    	build run stop remove

    Makefile에 대한 이해
    # docker Container에 접속하기 위해
    # 'docker run --privileged -d -p 6000:6000 -v $(pwd):/code --name mydocker mydocker:latest sbin/init'
    # 의 명령어를 매번 수행하기 어려움을 해결하고자 사용
    # make run을 수행할 시 컨테이너가 생성이 되어 있지 않다면 build를 먼저 수행한 뒤 run을 수행
    # remove 또한 Container가 실행 중일 때 중지하고 삭제함

### Docker-compose.yml 작성
    version: '3.1'                      # 사용할 Docker Compose 문법의 버전을 정의
    services:
        mydocker:                       # 실행할 컨테이너 이름을 정의
        working_dir: /code              # 실행 시 작동 될 디렉토리 설정
        build:                          # 빌드 옵션을 지정
            context: .                  # Build 시 현재 디렉토리를 사용
            dockerfile: ./Dockerfile    # Dockerfile을 기준으로 빌드(./ : 현재 이 파일의 위치)
        image: mydocker:latest          # 사용할 이미지 이름과 태그를 정의
        container_name: mydocker
        hostname: mydocker
        restart: always
        ports:                          # 호스트 포트와 컨테이너 포트를 어떻게 연결할지 정의
            - 6000:6000                 # <호스트 포트> : <컨테이너 포트>
        volumes:                        # 로컬 디렉토리와 컨테이너 디렉토리를 code 폴더에 연결
            - .:/code
        tty: true

# 설치
### Docker, Docker-compose가 설치 안되어있다면, [Docker, Docker-compose 설치](https://msnodeve.github.io/infra/2019-01-07-infra-docker-compose/)<br><br>작성한 docker-compose.yml이 있는 폴더에서 다음 명령 수행
    docker-compose up -d

![DockerCompose1]({{site.static_url}}/img/infra/infra-docker-compose1.png)
### .<br>.<br>.<br>
![DockerCompose2]({{site.static_url}}/img/infra/infra-docker-compose2.png)
### 사진 처럼 되면 성공

# 확인
    docker ps       # 현재 실행 중인 docker container 확인
    docker ps -a    # 모든 docker container 확인 

![DockerCompose3]({{site.static_url}}/img/infra/infra-docker-compose3.png)