# Git

(**버전**을 통해) 코드 관리 도구

### 

## SCM & VCS

- SCM: Source Code Management (소스 코드 관리)
- VCS: Version Control System (버전 관리 시스템)
- DVCS: Distributed VCS (분산형 버전 관리 시스템)



## Git?

- 버전 관리 도구
  - 변경 이력 트래킹
  - 언제든 특정 시점으로 이동 가능
- 백업 도구
- 협업도구



## Git 버전관리

> 중요: Git은 **폴더 단위**로 코드를 관리

- 커밋 == 버전 생성 == 스냅샷 촬영 == 현재 상태 저장



## `git init`

특정 폴더를 git으로 관리 시작

- `(master)` 프롬프트에 표시
- `.git` 폴더 생성
  - `.git` 폴더 삭제 시 git 관리 중지

```
Initialized empty Git repository in C:/Users/Seong HyunKyu/recap/.git/

```





## `git status`

git에게 상태를 물어보는 명령어 (git 상태 확인)

- `git init` 직후

```
On branch master : master라고 하는 branch에 있어

No commits yet : 아직 commit 없어

nothing to commit (create/copy files and use "git add" to track)
: commit 할 게 없어 (트래킹 하고 싶으면 `git add` 명령어 사용해)
```

- `a.txt` 파일 생성 직후

```
On branch master : master라고 하는 branch에 있어

No commits yet : 아직 commit 없어

Untracked files: 추적되지 않은 파일이 있어
  (use "git add <file>..." to include in what will be committed)
        a.txt(빨강)
  commit 될 수 있게 포함하고 싶으면 `git add <파일명>` 을 사용해

nothing added to commit but untracked files present (use "git add" to track)

```

- `git add a.txt` 직후

```
Changes to be committed : commit될 변경 사항이 있어
  (use "git rm --cached <file>..." to unstage)
        new file:   a.txt(초록)
```



## `git add [파일명]`

Staging Area(스냅샷 무대) 에 파일 추가



## `git commit -m "커밋 메시지"`

버전을 생성하는 행위

- 커밋(버전) 구성 요소

  - 해시(Hash)
  - 작성자
  - 날짜
  - 커밋메시지: 버전에 대한 설명

  ```
  [master (root-commit) a4b3738] First commit
   1 file changed, 0 insertions(+), 0 deletions(-)
   create mode 100644 a.txt
  
  ```



## `git log`

버전(커밋)들의 히스토리(로그)



## `git config`

설정

- `git config [설정할내용] [설정할값]`
  - `git config user.name 'Hyunkyu Seong'`
  - `git config user.email 'shk1333@gmail.com'`
  - `git config --global`: 전역 설정

```
Author identity unknown : 작자 미상

*** Please tell me who you are. : 니가 누군지 말해주세요.

Run 다음을 실행하세요

  git config --global user.email "you@example.com"
  git config --global user.name "Your Name"

to set your account's default identity.
Omit --global to set the identity only in this repository.

fatal: unable to auto-detect email address (got 'Seong HyunKyu@DESKTOP-VJK9Q42.(none)')
```





## 백업

Git의 도구로서의 기능 3가지 중 두번째 기능

```
1. 버전 관리 도구
2. 백업 도구
3. 협업 도구
```



### HTTP vs SSH

- HTTP : 보안적으로 부족, 불편하나 따로 배울 필요 없이 바로 사용 가능
- SSH : HTTP에 비해 보안적으로 훨씬 강력하나 배워야 할 내용이 매우 많음



### 백업 순서

1. 원격 저장소 생성
2. remote 정보 입력
3. git push



### 원격 저장소 생성

`github`가입 후 New repository 생성

- https://github.com/Seong-hk/first



## `git remote`

원격 저장소 정보 출력

- `git remote -v`: 상세 출력

- `git remote add`

  - `git remote add [저장소별명] [저장소주소]`

    - git remote add gitbackup https://github.com/Seong-hk/first.git

      (github에서 확인 가능)



## `git push`

원격 저장소에 코드 백업

- `git push [저장소별명] [브랜치이름]`
  - `git push origin master`
- github의 repository에서 push 한 git 잘 보이는지 확인
- `git push --set-upstream origin master` : 한 지역 저장소는 여러개의 원격 저장소와 연결될 수 있으며 그 중 현재 지정한 `origin`이라는 원격 저장소를 기본 저장소로 셋팅 하겠다는 의미. 이 이후 `git push`만 눌러도 origin이라는 곳으로 바로 백업됨



### `git clone`

원격 저장소에 백업한 것을 또 다른 지역 저장소로 복원/복제

- `git clone [저장소주소]`



### `git pull`

같은 원격 저장소를 이용하고 있는 서로 다른 지역 저장소들이 원격 저장소를 통해 다른 지역 저장소의 내용을 `git pull`로 당겨옴

- `git pull`

