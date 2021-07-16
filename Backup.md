## 백업
Git의 도구로서의 기능 3가지 중 두번째 기능
```
1. 버전 관리 도구
2. **백업 도구**
3. 협업 도구
```

### HTTP vs SSH
- HTTP : 보안적으로 부족, 불편하지만 따로 배울 필요 없이 바로 사용 가능
- SSH : HTTP에 비해 보안적으로 훨씬 강력하나 배워야 할 내용이 매우 많음

### 백업 순서
1. 원격 저장소 생성
2. remote 정보 입력
3. git push


### 원격 저장소 연결
`github` 가입 후 New repository 생성
- https://github.com/Seong-hk/first

### `git remote`
원격 저장소 정보 출력
- `git remote -v` : 상세 출력
- `git remote add`
    - `git remote add [저장소별명] [저장소주소]
        - git remote add origin https://github.com/Seong-hk/first
        (github에서 확인 가능)

### `git push`
원격 저장소에 코드 백업
- `git push [저장소별명] [브랜치이름]
    - `git push origin master`
- github의 repository에서 push한 git이 잘 보이는지 확인
- `git push --set-upstream origin master` : 한 지역 저장소는 여러개의 원격 저장소와 연결될 수 있으며 그 중 현재 지정한 `origin`이라는 원격 저장소를 기본 저장소로 셋팅하겠다는 의미. 이 이후 `git push`만 눌러도 origin이라는 repo로 바로 백업됨

### `git clone`
원격 저장소에 백업한 것을 또 다른 지역 저장소로 복원/복제
- `git clone [저장소주소]`

### `git pull`
같은 원격 저장소를 이용하고 있는 서로 다른 지역 저장소들이 원격 저장소를 통해 다른 지역 저장소의 내용을 `git pull`로 당겨옴
- `git pull`