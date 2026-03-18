# Git & GitHub 기초 (초보자용)

이 문서는 Git과 GitHub의 가장 기본적인 명령어와 개념을 초보자 관점에서 간단히 정리한 메모입니다.

---

## 1) Git과 GitHub 차이
- Git: 버전 관리 시스템(로컬에서 코드 변경 기록 관리)
- GitHub: Git 저장소를 호스팅하는 서비스(원격 저장소, 협업용)

---

## 2) 처음 한 번만 설정하는 것
```bash
git config --global user.name "당신이름"
git config --global user.email "you@example.com"
```
- `--global`은 컴퓨터 전체 설정입니다.

---

## 3) 새로운 저장소 만들기
- 로컬에서 새 Git 저장소 초기화:
```bash
git init
```
- 이미 있는 프로젝트를 Git으로 관리 시작할 때 사용

---

## 4) 원격 저장소 복사(clone)
```bash
git clone https://github.com/사용자/리포지토리.git
# 또는 SSH
git clone git@github.com:사용자/리포지토리.git
```

---

## 5) 변경 확인하고 스테이징하기
- 변경 상태 확인:
```bash
git status
```
- 파일을 스테이징(커밋 대상으로 추가):
```bash
git add 파일명
# 또는 모든 변경 추가
git add .
```

---

## 6) 커밋(로컬 저장)
```bash
git commit -m "간단한 변경 내용 메시지"
```
- 커밋 메시지는 명확하게 작성하세요. 예: "Fix header CSS" 또는 "Add login form"

---

## 7) 원격에 올리기(push)
- 먼저 원격 저장소가 설정되어 있어야 합니다. 보통 GitHub에서 리포지토리를 만든 뒤 URL을 얻습니다.
```bash
# 원격 추가 (처음 한 번)
git remote add origin https://github.com/사용자/리포지토리.git

# 로컬 main 브랜치를 원격에 업로드
git push -u origin main
# 이후에는 간단히
git push
```
- `-u origin main`은 upstream을 설정해 다음 push/pull을 간편하게 합니다.

---

## 8) 최신 원격 변경 가져오기(pull)
```bash
git pull
# 또는 원격/브랜치 명시
git pull origin main
```
- `pull`은 fetch + merge 역할을 합니다.

---

## 9) 브랜치(Branch) 사용 기본
- 새 브랜치 만들기 및 이동:
```bash
git checkout -b feature/my-feature
```
- 브랜치 목록 보기:
```bash
git branch
```
- 브랜치 전환:
```bash
git checkout main
```
- 브랜치 병합:
```bash
git merge feature/my-feature
```
- 병합 후 필요 없으면 브랜치 삭제:
```bash
git branch -d feature/my-feature
```

---

## 10) 로그와 변경 내용 보기
- 커밋 로그:
```bash
git log --oneline
```
- 파일 변경(diff):
```bash
git diff          # 스테이징 전
git diff --staged # 스테이징된 변경
```

---

## 11) 되돌리기 기초
- 마지막 커밋 되돌리기(작업은 남기고 커밋만 취소):
```bash
git reset --soft HEAD~1
```
- 마지막 커밋과 변경 모두 되돌리기(조심):
```bash
git reset --hard HEAD~1
```
- 이미 푸시한 커밋을 되돌릴 때는 `git revert` 사용 권장:
```bash
git revert <커밋해시>
```

---

## 12) 임시로 숨기기(stash)
- 작업 도중 브랜치를 바꿔야 할 때 임시 저장:
```bash
git stash
# 다시 복원
git stash apply
```

---

## 13) 원격(remote) 관련
- 원격 URL 보기:
```bash
git remote -v
```
- 원격 URL 변경(HTTPS → SSH 등):
```bash
git remote set-url origin git@github.com:사용자/리포지토리.git
```

---

## 14) .gitignore
- Git이 무시할 파일 목록을 `.gitignore`에 적습니다. 예:
```
node_modules/
.DS_Store
.env
```

---

## 15) GitHub 협업 기초 (Fork & Pull Request)
- 다른 사람의 리포지토리를 포크(Fork) → 로컬로 클론
- 브랜치 생성 → 작업 → 커밋 → 포크된 리포지토리에 푸시
- GitHub에서 원본 저장소로 Pull Request(PR) 생성하여 변경 요청

간단한 PR 단계:
1. 원본 저장소 Fork
2. 로컬로 Clone
3. `git checkout -b feature/...`
4. 작업, `git add` → `git commit`
5. `git push origin feature/...`
6. GitHub에서 PR 생성

---

## 16) 인증 방식 (HTTPS vs SSH)
- HTTPS: URL에 사용자 인증(보통 Personal Access Token 필요)
- SSH: 한 번 SSH 키를 등록하면 편리하게 사용 가능

SSH 예시 설정(간단):
```bash
# 로컬에서 키 생성
ssh-keygen -t ed25519 -C "you@example.com"
# 공개키(~/.ssh/id_ed25519.pub)를 GitHub 계정에 추가
```

---

## 17) 자주 쓰는 빠른 명령어 모음
```bash
git status
git add .
git commit -m "메시지"
git push
git pull
git checkout -b 새브랜치
git merge 브랜치명
git log --oneline
```

---

## 18) 초보자 팁
- 자주 `git status`로 상태를 확인하세요.
- 커밋 메시지는 짧고 명확하게 쓰기(무엇을 왜 했는지).
- 원격에 푸시하기 전에 로컬에서 잘 동작하는지 확인하세요.
- GitHub 데스크톱이나 GUI를 처음에 사용해보는 것도 학습에 도움이 됩니다.

---

원하시면 `Git 기초 실습 예제(초기화 → 커밋 → 푸시)`, `충돌 해결 예시`, 또는 `GitHub에서 SSH 설정 자세히`를 추가해 드릴게요.

---

## 19) 명령어 단축(aliases) — 자주 쓰는 명령어를 짧게
초보자는 자주 쓰는 긴 명령을 짧게 만드는 `alias`를 설정하면 편리합니다. `git config --global`로 설정하면 모든 저장소에서 바로 사용 가능합니다.

예: 자주 쓰는 alias 설정
```bash
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.lg "log --oneline --graph --decorate --all"
git config --global alias.unstage "reset HEAD --"
git config --global alias.last "log -1 --stat"
```

설정 후 사용 예:
- `git st` → `git status`
- `git co main` → `git checkout main`
- `git br` → `git branch`
- `git ci -m "메시지"` → `git commit -m "메시지"`
- `git lg` → 그래프 형식의 한줄 로그

`.gitconfig`에 직접 추가하는 방법 (텍스트 편집기로 열어 아래 블록을 추가):
```ini
[alias]
	st = status
	co = checkout
	br = branch
	ci = commit
	lg = log --oneline --graph --decorate --all
	unstage = reset HEAD --
	last = log -1 --stat
```

팁:
- 복잡한 명령은 따옴표(`"`)로 묶어서 alias에 넣습니다.
- alias는 로컬(저장소별)으로도 설정할 수 있으니 팀에서 룰이 있다면 전역 설정 대신 팀 규칙을 따르세요.

