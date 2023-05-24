+++
title = "도커 사용법"
date = "2023-05-23T13:50:46+02:00"
tags = ["theme"]
#categories = ["starting"]
description = "This tutorial will show you how to create a simple theme in Hugo. I assume that you are familiar with HTML, the bash command line, and that you are comfortable using Markdown to format content."
banner = "img/banners/docker.jpg"
#authors = ["Jane Doe"]
+++

## Docekr 다운로드 및 실행

1. 도커 다운로드 사이트 접속 (URL : https://www.docker.com/products/docker-desktop)

2. 자신의 OS에 맞는 다운로드 설정 선택 후 다운로드

3. Docker 실행

## Docker Image 다운로드 방법

1. 도커 허브에 접속 (URL : https://hub.docker.com)

2. 필요한 도커 이미지 검색

3. 검색 결과 중 원하는 이미지를 선택하고 태그를 선택 (태그는 이미지 파일의 버전과 같은 역할을 함)

4. 도커 이미지를 PULL 하여 이미지 저장

## Docker 명령어

1.  docker -v : 도커 버전 확인

2.  docker images : 도커에 다운받은 이미지 확인

3.	docker start <컨테이너 명> : 도커 데몬 실행

4.  docker restart <컨테이너 명> : 컨테이너 재실행

5.	docker exec -it <컨테이너> bash : 컨테이너 로그인

6.  docker attach <컨테이너 명> : 가동중인 컨테이너에 접속

7.	docker ps : 실행중인 컨테이너 확인 ( -a : 종료된 컨테이너 포함)

8.	docker pull <이미지>:<태그> : 이미지 다운

9.	docker run <옵션> <이미지 이름> : 도커 컨테이너 실행(docker run -itd ubuntu:22.04 bash) => ubuntu:22.04 이미지로 컨테이너 생성 및 실행

10.  docker stop <컨테이너 명> : 도커 컨테이너 정지

11.	docker rename <기존 이름> <변경할 이름> : 컨테이너 이름 변경

12.  docker rm <컨테이너 명> : 컨테이너 삭제

13.	apt update, apt upgrade : 패치 업데이트

14.	apt install <파일> : 파일 설치