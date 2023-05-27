+++
title = "Github Post"
date = "2021-08-01T21:29:20+02:00"
tags = ["golang", "programming", "theme", "hugo"]
# categories = ["programming","lorem","pseudo"]
banner = "img/banners/github.png"
# authors = ["John Doe"]
+++


## github란?

* 코드 저장소를 호스팅하고 관리하기 위한 웹 기반 플랫폼으로, 다양한 개발자들이 협업하고 소스 코드를 공유하는 데 사용된다.
* git을 기반으로 한 원격 저장소 호스팅 서비스
* https://github.com
* 계정을 만들고 사용
* 무료, 유상 서비스
* 문서 : https://docs.github.com/ko
* 스킬 : https://skills.github.com/

## 보안 설정
* “2FA”(투팩터 인증)을 설정
    * https://docs.github.com/ko/authentication/securing-your-account-with-two-factor-authentication-2fa/about-twofactor-authentication
    * 보안 강화(권장됨)
* ssh key 생성과 계정에 추가
    * github는 패스워드 입력을 이용한 저장소 사용이 금지됨, ssh key를 사용해야 함
    * https://docs.github.com/ko/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-addingit-to-the-ssh-agent
    * https://docs.github.com/ko/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-githubaccount

---

## github 주요 개념

### Remote Repository

* 원격 저장소는 코드 및 프로젝트 파일을 저장하고 관리하는 공간입니다. 개발자들은 로컬 컴퓨터에 코드를 유지하면서 다른 사람들과 공유하고 협업하기 위해 원격 저장소를 사용합니다.

### Pages

* GitHub Pages는 사용자가 웹 사이트를 호스팅하는 데 사용되는 기능입니다. 프로젝트의 문서, 블로그, 개요 등을 공개적으로 공유할 수 있습니다.

### Organization

* 개인 사용자나 조직이 프로젝트를 관리하고 협업하는 데 사용하는 기능입니다. 조직은 여러 팀이나 개인들이 함께 작업하는 데 필요한 도구와 기능을 제공합니다.

#### 팀 관리

* Organization은 팀 단위로 구성원을 관리할 수 있는 기능을 제공합니다. 팀은 특정 프로젝트나 관심사에 따라 구성될 수 있으며, 각 팀은 개별적으로 액세스 권한과 설정을 가질 수 있습니다. 이를 통해 프로젝트 관리와 팀 간의 협업을 용이하게 할 수 있습니다.

#### 엑세스 권한 관리

* Organization은 사용자에게 액세스 권한을 할당하는 기능을 제공합니다. 소유자, 관리자, 구성원 등의 역할을 할당하고, 각 역할에 대한 권한을 조정할 수 있습니다. 이를 통해 프로젝트에 대한 접근과 수정 권한을 조정하고 보안을 강화할 수 있습니다.

#### 중앙화된 리포지토리 관리

* Organization 내에서는 여러 개의 리포지토리를 중앙에서 관리할 수 있습니다. 이는 프로젝트 간의 코드 공유와 버전 관리를 용이하게 합니다. 조직 내의 모든 팀원은 해당 리포지토리에 액세스하고, 변경 사항을 추적하고, 풀 리퀘스트를 생성하여 수정 사항을 제안할 수 있습니다.

#### 이슈 트래킹과 프로젝트 관리

* Organization은 이슈 트래킹과 프로젝트 관리를 위한 도구를 제공합니다. 팀 간의 작업 일정과 작업 항목을 조직화하고 추적할 수 있습니다. 이를 통해 프로젝트의 진행 상황을 모니터링하고 작업의 우선순위를 관리할 수 있습니다.

### Issues

* 이슈는 프로젝트의 문제, 기능 요청, 버그 보고 등과 같은 사항을 추적하는 데 사용됩니다. 이슈는 팀의 협업과 개발 과정에서 중요한 역할을 합니다. 이슈는 라벨, 담당자, 마일스톤 등과 함께 관리될 수 있습니다.

### Pull Request

* 풀 리퀘스트는 원격 저장소에 기여하려는 개발자가 수정한 내용을 관리자(또는 프로젝트의 주인)에게 알리는 요청입니다. 다른 사람의 원격 저장소에서 변경 사항을 가져오고, 그 변경 사항을 병합(merge)하여 프로젝트에 반영할 수 있습니다.

### Branch

* 브랜치는 원격 저장소나 로컬 저장소에서 개발자가 독립적으로 작업하는 공간입니다. 새로운 기능을 개발하거나 버그 수정을 진행할 때, 브랜치를 생성하여 원본 코드와 분리하여 작업할 수 있습니다. 작업이 완료되면 브랜치를 병합하여 변경 사항을 원본 코드에 반영할 수 있습니다.

#### Branch 전략

##### Branch 활용

* 개발 작업은 main 브랜치에서 하지 않는다.
* 여러 명이 함께 개발을 할 때 각자의 브랜치를 만들어서 개발을 하고 메인 브랜치는 함부로 수정하지 않는 것이 좋음
* 혼자 개발할 때에도 소프트웨어가 배포되거나 퍼블리싱이 된 후에는 메인 브랜치를 함부로 수정하지 않는 것이 좋음
* 브랜치를 만들어서 소프트웨어를 개발하고 업데이트할 때 적절한 규칙을 정해서 사용하는 것이 브랜치 전략
* 가장 많이 사용하는 전략으로 다음과 같은 것들이 있음
* Git Flow
    * 먼저 나옴
    * 패키지 소프트웨어 개발을 위해 고안된 전략
    * 웹서비스와 같이 명시적 버전 관리가 필요없이 수시로 업데이트되는 소프트웨어 개발에는 적합치 않음
    * 복잡함
* GitHub Flow
    * 웹서비스와 같이 명시적 버전 관리가 중요하지 않으며 수시로 업데이트 되는 소프트웨어 개발을 위해 고안됨
    * 브랜치를 단순하게 만들어 사용

##### Github Flow

* Main branch
    * 항상 Stable한 상태여야 한다.
    * 모든 커밋은 언제 배포하든 문제 없어야 하고, 언제든 브랜치를 새로 만들어도 문제가 없어야 한다.
    * Main 브랜치의 모든 커밋은 빌드가 되고, 테스트를 통과해야 한다.
* Topic branch
    * 새로운 기능을 개발할 때에는 Topic 브랜치를 Main 브랜치로부터 생성한다.
    * 별도로 Hotfix 브랜치를 관리하지 않으며, 버그 수정도 Topic 브랜치에서 진행한다.
    * Topic 브랜치의 이름은 기능을 설명하는 명확한 이름으로 네이밍 해야 한다. 예를 들면, user-content-cachekey, submodules-init-task, redis2-transition 등이 있다.
    * Topic 브랜치의 커밋은 기능이 완성되지 않았더라도 꾸준히 Push 한다. (소스 백업의 기능)

##### 새 브랜치 만들기

* 로컬과 원격(GitHub)에 브랜치 만드는 방법
    * 1) 원격에서 만들고 로컬로 가져오기
            * GitHub에서 브랜치 만들기
            * git fetch -p
            * git checkout <브랜치 이름>
    * 2) 로컬에서 만들고 원격으로 push
            * git branch <브랜치 이름>
            * git checkout <브랜치 이름>
            * 또는 git checkout -b <브랜치 이름>
            * git push <원격> <브랜치 이름>