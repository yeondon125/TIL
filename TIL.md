# Git & GitHub 알아보기

- ## Git 과 GitHub 차이점
  - Git은 개인적으로 사용하는 소프트웨어
  - GitHub은 Git을 이용하여 소프트웨어를 공유하는 사이트
- ## Git 기본 명령어

  - $ git init

    - 새로운 git 저장소를 생성하거나 기존 저장소를 초기화 한다.
    - 파일 안에 새로운 파일을 생성해서 "이 파일을 저장소로 만들거야" 라는 명령어다.

  - $ git add

    - 어떤 파일을 저장할지 선택하는 명령어.
    - `git add .` 현재 폴더의 모든 파일.

  - $ git commit

    - 파일을 저장소로 옮기는 명령어.
    - `git commit -m "파일명"`

  - $ git push

        - 저장소에 옮긴 파일을 github에 공유하는 명령어.
        - `git push origin master`

  - $ git pull
    - github에서 옮긴 파일을 가져오는 명령어.
    - `git pull origin master`

## 브랜치와 병합의 개념

- ### 브랜치란?

  > 코드를 분리하여 관리한다.  
  > 새로운 기능을 추가하거나 관리할 때 유용하다.

- ### 브랜치 명령어

  > - `git branch` 현재 브랜치 목록을 확인한다.
  > - `git branch [브랜치명]` 새로운 브랜치를 만든다.
  > - `git switch (checkout) [브랜치명]` 현재 브랜치를 변경한다.
  > - `git switch （checkout） -b [브랜치명]` 새로운 브랜치를 만들고 변경한다.
  > - `git merge feature/login` 기존 feature브랜치와 login 브랜치가 지금 브랜치에 병합된다.

  ## GitHub를 활용한 협업 흐름 조사

  > ### 1. 공동 작업자 추가하기
  >
  > ### 2. 작업환경 구성하기
  >
  > > - `$git init projecttest`
  > > - `$cd projecttest `
  > > - `$git config user.name "사용자 이름" `
  > > - `$git config user.email 메일 주소`
  >
  > ### 3. 원격 저장소에 첫 commit, push하기
  >
  > > - `$git remote add origin 복사한 원격저장소URL`
  > > - `$vim viewtest.txt `
  > > - `$git add . `
  > > - `$git commit -m "viewtest"`
  > > - `$git push -u origin master`
  >
  > ### 4. 공동 작업자 pc에 원격 저장소 clone
  >
  > > - `$git clone 원격저장소URL` (본인의 pc에 원격저장소를 clone한다.)
  >
  > ### 5. 첫 번째 commit이 아니라면 pull
  >
  > > - pull 을 진행하지 않고 push를 진행하면 코드를 작성하는 사이에 다른 팀원이 push 한 코드와 충돌이 나기 때문에 pull 을 진행 해 받아 온 후 push 를 진행한다.
