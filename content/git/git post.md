+++
title = "Git Post"
date = "2015-06-24T13:50:46+02:00"
tags = ["theme"]
# categories = ["starting"]
description = "This tutorial will show you how to create a simple theme in Hugo. I assume that you are familiar with HTML, the bash command line, and that you are comfortable using Markdown to format content."
banner = "img/banners/git1.png"
# authors = ["Jane Doe"]
+++

## 소스 관리 

### 소스 상태 

* 관리 대상 여부 
  * tracked(추적대상)
    * 관리 대상
* untracked(추적대상 아님)
  * 관리 대상 아님
* 확인
  * git status

### 관리 대상 상태 

* `committed` : 버전관리에 안전하게 저장됨, snapshot
* `staged` : 커밋할 대상이라고 표시된 상태
* `modified` : 파일이 수정되었지만 staged 되지 않음
* `tracked`인 파일은 변경을 감지함
* `untracked`인 파일은 변경을 감지하지 않음
* `untracked`인 파일이 새로 생긴 것은 감지함

### 관리 대상으로 만들기 

* git add <file 또는 디렉토리>
  * untracked 파일을 tracked로 변경
  * 동시에 staged로 변경
  * 이미 tracked이고 modified인 경우 staged로 변경
  * 디렉토리를 지정한 경우 하위의 모든 파일까지 변경

### 소스 관리에서 제외 하기

* `git add dir` : dir과 하위 디렉토리에 있는 모든 파일들이 stage됨, .gitignore파일을 만들고 무시할 패턴을 적으면
관리되지 않음
* .gitignore 파일의 패턴 사용법
  * 아무것도 없는 라인이나, # 로 시작하는 라인은 무시
  * 디렉토리는 슬래시(/)를 끝에 사용하는 것으로 표현
  * 슬래시(/)로 시작하면 하위 디렉토리에 적용되지(Recursivity) 않음
  * 느낌표(!)로 시작하는 패턴의 파일은 무시하지 않음
  * 표준 Glob 패턴을 사용
  * 예)
    * `*.swp`
  * Glob 패턴
    * `*` : 1이상의 어떤 문자
    * `[abc]` : a, b, c 중 하나
    * `?` : 하나의 어떤 문자
    * `[0-9]` : 0부터 9까지의 수 중 하나
    * `**` : 디렉토리 하위의 디렉토리까지 지정

### .gitignore 파일 예

```
# 확장자가 .a인 파일 무시
*.a
# 윗 라인에서 확장자가 .a인 파일은 무시하게 했지만 lib.a는무시하지 않음
!lib.a
# 현재 디렉토리에 있는 TODO파일은 무시하고 subdir/TODO처럼 하위디렉토리에 있는 파일은
무시하지 않음
/TODO
# build/ 디렉토리에 있는 모든 파일은 무시
build/
# doc/notes.txt 파일은 무시하고 doc/server/arch.txt 파일은 무시하지 않음
doc/*.txt
# doc 디렉토리 아래의 모든 .pdf 파일을 무시
doc/**/*.pdf
```


## 주요 git 명령어

* init : .git 초기화
* add: `untracked` 파일을 `tracked` 로 변경 -> 동시에 `stage`로 변경, 이미 
`tracked` 이고 `modified` 인 경우 `staged`로 변경
    * git add . : 모든 파일 변경

### Commit하기
* git commit
  * staged된 파일만 커밋할 수 있음
* 커밋 메시지 입력(필수)
  * git commit -m "의미있는 메시지"
  * git commit 후 편집기에서 입력
  * git commit -a는 staged로 변경하고 커밋


### 비교

* git diff
  * 수정했지만 아직 stage하지 않은 파일들을 비교
  * 커밋한 파일과 아직 stage되지 않은 파일 비교
  * stage된 파일과 unstage된 파일 비교
* git diff --staged
  * git diff --cached 동일한 기능
  * 커밋한 것과 staging area에 있는 파일들을 비교

### 커밋 히스토리
* git log
  커밋한 이력을 보여줌
  최근 커밋이 위에 표시
* git log --patch
  * 각 커밋의 diff 결과
  * git log -p와 동일
* git log --patch -2
  * 최근 2개의 커밋만 비교
* git log --pretty=oneline
* git log --oneline -n 3
* 커밋은 해시값으로 구분
  * 해시값 : 40자의 16진수
  * 주로 앞의 7자리로 사용

### 파일 삭제
* git rm : tracked 상태의 파일을 삭제
  * 실제(작업 디렉토리의) 파일도 삭제
  * 그리고 커밋해야 함

### 파일 이름 변경
* git mv file_from file_to
* 다음 명령과 동일
  * mv file_from file_to
  * git rm file_from
  * git add file_to

### Modified 파일을 되돌리기
* git checkout -- <file>
* 수정한 내용이 모두 사라지므로 주의 해서 사용
* 브랜치를 사용해야 한다.

### 이전 커밋으로 되돌리기
* 마지막 커밋을 취소
  * git revert <되돌리고 싶은 커밋 이름>
* 특정 커밋으로 이동
  * git reset --hard <이동하려는 이전 커밋 이름>
* 협업을 할 경우 되돌리기를 주의해야 하며, 자신만의 브랜치를 만들어서 하는 것이 좋다.

### branch란?
* 코드를 통째로 복사해서 독립적으로 개발
* 새로운 작업은 브랜치를 만들어서 하고 완성되면 합병
* 어떻게 브랜치를 만들고 합병할 지 전략 필요
  * 브랜치 워크플로

### branch 명령
* git branch : 브랜치 보기
* git branch <새 브랜치 이름> : 브랜치 만들기
* git checkout <브랜치 이름> : 브랜치 이동
* git checkout -b <새 브랜치 이름>
  : 브랜치를 만들고 이동
* git merge : 브랜치 합병
* git log \--oneline \--decorate \--graph \--all
  : 로그에 브랜치가 잘 나타나게 표시
* git branch -d <브랜치 이름> : 브랜치 삭제