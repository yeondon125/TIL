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
    - `git push -u origin master`

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
