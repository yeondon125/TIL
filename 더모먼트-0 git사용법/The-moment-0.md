# Git & GitHub 알아보기

- ## Git 과 GitHub 차이점
  - Git은 개인적으로 로컬에서 버전을 관리 할 때 사용하는 소프트웨어, 코드를 시간순으로 정리 가능하다.
  - GitHub은 Git을 이용하여 소프트웨어를 공유하는 사이트, GITHUB을 이용하여 팀원과 협업이나, 코드리뷰 등 편리하다.
- ## Git 기본 명령어

  - $ git init

    - 새로운 git 저장소를 생성하거나 기존 저장소를 초기화 한다.
    - 특정 폴더 안에 새로운 파일을 생성해 git 저장소로 만든다.

  - $ git add

    - 어떤 파일을 저장할지 선택하는 명령어.
    - `git add .` 현재 폴더의 모든 파일.

  - $ git commit

    - 파일을 저장소로 옮기는 명령어.
    - `git commit -m "변경사항"`

  - $ git push

        - 저장소에 옮긴 파일을 github에 공유하는 명령어.
        - `git push origin 브랜치 이름`

  - $ git pull
    - github에서 옮긴 파일을 가져오는 명령어.
    - `git pull origin 브랜치 이름`

## 브랜치와 병합의 개념

- ### 브랜치란?

  > 코드를 분리하여 관리한다.  
  > 새로운 기능을 추가하거나 관리할 때 유용하다.

- ### 브랜치 명령어

  > - `git branch` 현재 브랜치 목록을 확인한다.
  > - `git branch [브랜치명]` 새로운 브랜치를 만든다.
  > - `git switch (checkout) [브랜치명]` 현재 브랜치를 변경한다.
  > - `git switch （checkout） -b [브랜치명]` 새로운 브랜치를 만들고 변경한다.
  > - `git merge feature/login` 현재 브랜치에 feature/login 브랜치의 내용을 병합한다.

  ## GitHub를 활용한 협업 흐름 조사

  > ### 1. 원격 저장소에 첫 commit, push하기
  >
  > > - `$git remote add origin 복사한 원격저장소URL`
  > > - `$vim viewtest.txt `
  > > - `$git add . `
  > > - `$git commit -m "viewtest"`
  > > - `$git push -u origin master`
  >
  > ### 2. 공동 작업자 pc에 원격 저장소 clone
  >
  > > - `$git clone 원격저장소URL` (본인의 pc에 원격저장소를 clone한다.)
  >
  > ### 3. 첫 번째 commit이 아니라면 pull
  >
  > > - pull 을 진행하지 않고 push를 진행하면 코드를 작성하는 사이에 다른 팀원이 push 한 코드와 충돌이 나기 때문에 pull 을 진행 해 받아 온 후 push 를 진행한다.

- ### Pull Request (PR)
  - 여기서 Pull Request란 내가 작업한 코드를 병합하기 전에 팀원들에게 피드백을 요청하고, 리뷰를 받은 후 병합하는 절차이다
  - 새로운 기능을 만든 후 바로 merge 하지 않고 팀원 승인 후 병합합니다.
- ### 코드리뷰
  - 원이 작성한 코드를 다른 사람이 검토하고 피드백을 주는 과정
    - Comment : 승인과 무관하게 일반적인 커멘트를 할 때 선택한다.
    - Approve : Comment와 다르게 리뷰어가 승인을 하는 것으로, 머지해도 괜찮다는 의견을 보내는 것이다.
    - Request changes : 말 그대로 변경을 요청하는 것으로, 승인을 거부하는 것을 뜻한다.
- ### Git flow 전략
  - main : 제품으로 출시될 수 있는 브랜치
  - develop : 다음 출시 버전을 개발하는 브랜치
  - feature : 기능을 개발하는 브랜치 (develop에서 기능을 추가하거나 수정하는 브랜치)
  - release : 릴리스 직전 버그 수정, 문서 정리 등 QA 목적
  - hotfix : 운영 중 문제 발생 시 main에서 직접 파생해서 수정 후 즉시 배포 가능
    > main 브랜치 아래 relase와 hotfix, relase 아래에 develop, 그 아래 feature 로 분할하여 개발 후 병합함.
