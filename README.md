# git
> git은 **버전 관리**와 **협업**을 가능하게 해주는 툴이다.

- git으로 다른 컴퓨터에 작업물을 보낼 수 있다.

  - **git**: 버전관리 프로그램
- **GitHub**: git으로 관리하는 프로젝트를 외부컴퓨터에 올려둘 수 있는 서비스를 제공한다. 이 **원격저장소** 역할을 하는 사이트가 바로 GitHub.

<br/>

# git의 작업영역

<img src="https://user-images.githubusercontent.com/64063767/134016150-d1a544d5-3e5b-4b3b-a29e-3464c3d060ee.png" alt="image" style="zoom:50%;" />

1. **working directory**: 작업을 하는 프로젝트 디렉토리
2. **staging area**: `git add`를 한 파일들이 존재하는 영역
3. **repository**: working directory의 변경 이력들이 저장되어 있는 영역 (커밋들이 저장되는 영역) 

<br/>

# git 명령어
| Command                                     | Description                                                  |
| :------------------------------------------ | :----------------------------------------------------------- |
| `git init`                                  | 현재 디렉토리를 Git이 관리하는 프로젝트 디렉토리(working directory)로 설정하고, 그 안에 repository(.git/) 생성 |
| `git help [command]`                        | 커맨드 도우미 (명령어 공식 매뉴얼)                           |
| `git config user.name [username]`           | 커밋할 때 필요한 사용자 이름 설정                            |
| `git config user.email [useremail]`         | 커밋할 때 필요한 사용자 메일 설정                            |
| `git status`                                | 현재 repository 프로젝트 상태 확인                           |
| `git add [file/directory]`                  | 버전 관리할 파일/디렉토리를 staging area에 올리기            |
| `git add .`                                 | working directory 내의 수정사항있는 모든 파일들을 staging area에 올리기 |
| `git reset [file]`                          | staging area에 올라간 파일을 다시 내리기                     |
| `git reset --hard [commit id]`              | HEAD가 과거의 커밋을 가리키게 할 수 있다.<br />working directory의 내용도 과거 커밋의 모습으로 돌아간다. |
| `git reflog`                                | 이전 커밋 내역과 id 확인                                     |
| `git commit -m [commit message]`            | 현재 staging area에 올라간 파일들을 커밋으로 스냅샷(snapshot) 남기기 |
| `git commit --amend`                        | 가장 최신 커밋 수정                                          |
| `git log`                                   | 이때까지 한 커밋 내역 확인                                   |
| `git log --pretty=oneline`                  | 커밋 히스토리를 한줄로 출력                                  |
| `git show [commit id]`                      | 특정 커밋의 변경사항 확인                                    |
| `git diff [commit A id] [commit B id]`      | 두 커밋 간의 차이 비교                                       |
| `git remote add origin [github_address]`    | remote repository(원격 저장소) 연결 설정                     |
| `git push origin main`                      | local repository의 내용을 remote repository에 보내기<br />(origin: 원격 저장소 주소 대명사) |
| `git pull`                                  | remote repository의 내용을 local repository로 가져오기       |
| `git clone [github_address]`                | GitHub에 있는 프로젝트를 내 컴퓨터로 가져오기                |
| `git config alias.[ALIAS] '[COMMAND LINE]'` | 명령어 전체에 Alias 별명 붙여주기<br />`git config alias.history 'log --pretty=oneline'` |

<br/>

# Commit Guideline

## 1. 커밋 메시지 작성 가이드라인

- 1.1 커밋 메시지 제목과 상세 설명 사이에는 **한 줄을 비워둔다.**

- 1.2 커밋 메시지 제목 뒤에 **온점(.)을 붙이지 않는다.**
- 1.3 커밋 메시지 제목의 첫번째 알파벳은 **대문자**로 작성 한다.
- 1.4 커밋 메시지의 제목은 **명령조**로 작성한다. (Fix it / ~~Fixed it~~ / ~~Fixes it~~)
- 1.5 커밋 상세 설명에는 아래 내용이 권장된다.
  - 왜 커밋을 했는지
  - 어떤 문제가 있었고
  - 적용한 해결책이 어떤 효과를 가지는지
- 1.6 다른 사람들이 자신의 코드를 바로 이해할 수 있다고 가정하지 말고 최대한 친절하게 작성한다.

<br/>

## 2. 커밋할 때 알아둬야할 사항

- 2.1 **하나의 커밋**에는 **하나의 수정사항**, **하나의 이슈 해결** 내용만 남기도록 한다.
  - 최대한 작은 단위의 변화를 기준으로 커밋을 한다. (단위 기준은 회사 규칙에 따라 달라질 수 있음)
  - 많은 내용을 수정하고 하나의 커밋으로 남기는 것은 지양한다.
  - 하나의 커밋이 하나의 사실만을 가지고 있어야 나중에 이해하기 쉽다.

- 2.2 현재 프로젝트 디렉토리의 상태가 그 내부 전체 코드를 실행했을 때 **에러가 발생하지 않는 상태인 경우에만** 커밋을 한다.
  - 커밋으로 보관된 특정 시점의 전체 코드는 항상 문제없이 실행되는 상태여야 한다.
  - 나중에 동료 개발자가 특정 커밋의 코드로 실행했을 때 에러가 발생하지 않도록 한다.
  - 과거 버전의 프로그램을 사용해야하거나
  - 과거 커밋을 시작점으로 한 다른 방향의 별도 프로젝트를 시작하거나
  - 아예 그 커밋으로 현재 프로젝트를 리셋할 수도 있다.

<br/>

# Commit check

- `HEAD`

  - 어떤 커밋 하나를 가리킴. 보통 가장 최근에 한 커밋을 가리킴
  - HEAD가 가리키는 커밋에 따라 working directory를 다르게 구성

- `git reset [option] [commit id]`

  | git reset [option] [commit id] | working directory  | staging area       | repository                |
  | ------------------------------ | ------------------ | ------------------ | ------------------------- |
  | --soft                         | 안 바뀜            | 안 바뀜            | HEAD가 commit id를 가리킴 |
  | --mixed                        | 안 바뀜            | commit id처럼 바뀜 | HEAD가 commit id를 가리킴 |
  | --hard                         | commit id처럼 바뀜 | commit id처럼 바뀜 | HEAD가 commit id를 가리킴 |

  
