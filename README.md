# git
> git은 **버전 관리**와 **협업**을 가능하게 해주는 툴이다.

- git으로 다른 컴퓨터에 작업물을 보낼 수 있다.

  - **git**: 버전관리 프로그램

  - **GitHub**: git으로 관리하는 프로젝트를 외부컴퓨터에 올려둘 수 있는 서비스를 제공한다. 이 **원격저장소** 역할을 하는 사이트가 바로 GitHub.

<br/>

# git 명령어

```bash
# 현재 디렉토리를 Git이 관리하는 프로젝트 디렉토리(working directory)로 설정하고, 그 안에 repository(.git/) 생성
$ git init

# 커맨드 도우미 (명령어 공식 매뉴얼)
$ git help [command]
$ git help add
```

```bash
# 커밋할 때 필요한 사용자 정보 설정
$ git config user.name "HyunHo Choi"
$ git config user.email "hyunh317@naver.com"
```

```bash
# 현재 repository 프로젝트 상태 확인
$ git status
```

```bash
# 버전 관리할 파일/디렉토리를 staging area에 올리기
$ git add [file/direcotry]

# working directory 내의 수정사항있는 모든 파일들을 staging area에 올리기
$ git add .
```

```bash
# staging area에 올라간 파일을 다시 내리는 명령어
$ git reset [file]
```

```bash
# 현재 staging area에 올라간 파일들을 커밋으로 스냅샷(snapshot) 남기기
$ git commit -m "commit message"
```

```bash
# remote repository(원격 저장소) 연결 설정
$ git remote add origin [github_address]
```

```bash
# remote repository(원격 저장소)에 push
# origin: 원격저장소 주소 대명사
$ git push origin main
```
