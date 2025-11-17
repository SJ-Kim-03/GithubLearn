# Road to Developer.

## Chapter 00. git 기본

### CLI 기본 명령어

```
$ git init
```

- .git 폴더: local repository 생성
- 초기화 과정
- shift + command + . : 숨김 파일 확인

```
$ git config -- global user.email(.name) "email(name)"
```

- 수정자 정보 등록
- 이메일, 이름 입력

```
$ git add file
```

- 버전으로 만들 파일(변경할 사항) 선택

```
$ git commit -m
```

- 커밋의 상세 설명 추가

```
$ git log
```

- 커밋 확인 가능, 최신순

```
$ git checkout 7자리
```

- 이전 커밋으로 되돌아가기
- 7자리 대신 - 사용시 최신 커밋으로 복원
- 최근 switch, restore 명령어로 나뉘어짐
- switch: 브랜치 간 이동
- restore: 파일 복구
- checkout은 실무에서 사용하지 않음

```
$ git remote add origin 주소
```

- repository 생성 후 연결 (https://github.com/SJ-Kim-03/GithubLearn.git)
- 원격 저장소 주소 입력
- origin: 원격 저장소

```
$ git branch -M name of branch
```

- 저장될 branch 생성

```
$ git push origin main
```

- 원격 저장소의 branch에 업로드
- origin의 main이라는 branch로 올려라
- github에서 repository 생성 시 main 브랜치 생성이 default
- CLI, 코드트리 환경에서는 master 브랜치 생성, 변경 가능
- name, token 입력

```
$ git clone 원격 저장소 주소 .
```

- 로컬 저장소에 내려받기
- 띄우고 마침표 하지 않으면 리포지토리 이름 폴더가 생성됨

```
$ git pull origin main
```

- 다른 로컬 저장소에서 최신본 가져오기

## Chapter 01~02. GUI, 버전 관리

### 소스트리 설치

- Git 사용 도와주는 GUI
- Create: = git init 초기화 명령어
- Add: 로컬 저장소를 소스트리에 추가
- .git 폴더에는 버전 관리한 데이터와 원격 저장소 주소 등 정보 저장

### SubVersion(SVN)과 Git의 차이

- SVN: 델타(Delta) 방식, 차이점만 저장, 많은 계산 필요
- Git: 스냅샷(Snapshot) 방식, 전체 저장, 바로 앞 커밋과 비교연산 1회

### Git으로 관리하는 파일의 네 가지 상태

- ** 추적 안됨(untracked)**: git init, 초기화, 파일 생성
- ** 스테이지됨(staged)**: git add 파일명, 파일 스테이지에 올리기
- ** 수정 없음(unmodified)**: git commit -m "message", 스냅샷(버전) 생성
- 원격 저장소 업로드: git push origin main
- ** 수정함(modified)**: 파일 수정 or 생성한 경우, 수정 없음(unmodified)일 경우 스테이징 불가
- 변경사항 add, commit, push를 통해 버전 관리

## Chapter 03. 협업하기

### 브랜치

- commit 1 --- 2 --- 3 ..., 브랜치는 commit을 **'가리킨다'**
- 하나의 커밋을 여러 브랜치가 가리킬 수 있다.
- 다수가 개발 협업 시, 서로 "다른" 브랜치에 커밋, 이후 합치는 방식으로 협업
- 특정한 기준 시점에서 줄기를 나누어 작업할 수 있는 기능을 **브랜치**라고 함
- 분기 시 브랜치는 포인터(pointer) 역할을 하게 된다.
- **HEAD**라는 특수한 포인터 사용, 브랜치를 가리키게 하여 커밋 상태를 볼 수 있게 함
- HEAD로 인해 브랜치 간 왕래가 가능
- HEAD 포인터가 과거 커밋을 가리킬 경우, 분리된(Detached) HEAD라고 표현
