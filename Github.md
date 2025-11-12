# 🧭 Git 기본 설정 및 사용 가이드

---

## 1️⃣ Git 최초 설정 
> Git 전역으로 사용자 이름과 이메일 주소를 설정합니다. <br>
> (⚠️ GitHub 계정 정보와는 별개입니다.) 
```bash
git config --global user.name "본인 이름"
git config --global user.email "본인 이메일"

# 기본 브랜치명을 main으로 변경
git config --global init.defaultBranch main
```

---

## 2️⃣ 프로젝트 생성 & Git 관리 시작
```bash
git init          # 현재 폴더를 Git 저장소로 초기화
git status        # 변경된 파일 상태 확인
```

---

## 3️⃣ Git에서 과거로 돌아가기
### 🔹 1. reset
> 원하는 시점으로 돌아간 뒤, 그 이후의 내역을 완전히 삭제
```bash
git log  # 되돌아갈 커밋 해시 복사
git reset --hard 돌아갈 커밋 해시
```
> 🔁 reset 하기 전 시점으로 복원 ( .git 복원 후 사용 )
```bash
git reset --hard 
```
💡 SourceTree: 해당 커밋 우클릭 → 이 커밋까지 현재 브랜치를 초기화(Hard)

### 🔹 2. revert
> 되돌리고 싶은 커밋을 거꾸로 실행하여 새로운 커밋으로 되돌리기
> (기존 히스토리를 보존)
```bash
git log                                  # 되돌릴 커밋 해시 복사
git revert (되돌릴 커밋 해시)           # :wq 로 커밋 메시지 저장
```
> 오류 시 해결 후 계속 진행
```bash
git revert --continue
```
> 커밋하지 않고 되돌리기 (검토용)
```bash
git revert --no-commit (되돌릴 커밋 해시)
```
💡 SourceTree: 해당 커밋 우클릭 → 커밋 되돌리기

---

## 4️⃣ Branch 

| 명령어 | 설명 |
|--------|------|
| `git branch (브랜치명)` | 브랜치 생성 | 
| `git branch` | 브랜치 목록 확인 | 
| `git switch (브랜치명)` | 브랜치로 이동 | 
| `git switch -c (브랜치명)` | 브랜치 생성 + 이동 | 
| `git branch -d (브랜치명)` | 브랜치 삭제 | 
| `git branch -D (브랜치명)` | 브랜치 강제 삭제 | 
| `git branch -m (기존명) (새이름)` | 브랜치 이름 변경 | 
| `git log --all --decorate --oneline --graph` | 브랜치 내역 그래프로 보기 |

### 4-1. Branch 합치기
#### 🔹 1. merge
> 두 브랜치를 **하나의 커밋에 이어붙이는 방식** (브랜치 사용 내역o) <br>

```bash
# B 브랜치를 A 브랜치로 merge
git switch (A 브랜치)
git merge (B 브랜치)           # :wq 로 커밋 메시지 저장
git branch -d (B 브랜치)       # 병합된 브랜치는 삭제

# 당장 충돌 해결이 어려울 경우
git merge --abort

# 충돌 부분 수정한 뒤
git add .
git commit 
```
💡 SourceTree: A브랜치로 이동 후 B 브랜치를 우클릭하고 현재 브런치로 to-merge 병합

#### 🔹 2. rebase (B → A)
> 한 브랜치를 **다른 브랜치에 이어붙이는 방식** (커밋 내용 한줄로 정리) <br>
> ⚠️ 단, 이미 **팀원과 공유된 커밋**에는 `rebase` 사용을 피하기 (히스토리 충돌 위험이 있음) <br>

```bash
# B 브랜치를 A 브랜치로 rebase
git switch (B 브랜치)
git rebase (A 브랜치)
git switch (A 브랜치)
git merge (B 브랜치)
git branch -d (B 브랜치)

# 당장 충돌 해결이 어려울 경우
git rebase --abort

# 충돌 부분 수정한 뒤
git add .
git rebase --continue
```
💡 SourceTree: 리베이스 할 B브랜치로 이동 후 A 브랜치를 우클릭하고 현재 변경사항을 A에 재배치 


### 4-2. 원격의 브랜치 사용 
```bash
# 브랜치 생성 + 이동 후
git branch from-local
git branch -a

# 로컬에서 브랜치 생성 후 받아오기
git fetch
git switch -t origin/(가져올 브랜치명)

# 원격의 브랜치 삭제
git push (원격 이름) --delete (원격의 브랜치명)
```

---

## 5️⃣ 원격 저장소 사용
| 명령어 | 설명 |
|--------|------|
| `git remote add origin (원격 저장소 주소)` |  | 
| `git branch -M main` |  | 
| `git push -u origin main` |  | 
| `git push` |  |
| `git remote` |  | 
| `git remote -v` |  | 
| `git remote remove (origin 등 원격 이름)` |  | 
| `git clone (원격 저장소 주소)` |  |
| `` |  |

#### push 할 것이 있을 시 pull
```bash
#  merge 방식
git pull --no-rebase
# rebase 방식 (협업시 사용 OK)
git pull --rebase

# 로컬의 내역 강제 push
git push --force 
```
---

### 🪄 터미널 명령어 모음
| 명령어 | 설명 |
|--------|------|
| `git init` | Git 저장소 초기화 |
| `git status` | 변경사항 확인 |
| `git add .` | 모든 변경 파일 추가 |
| `git commit -m "메시지"` | 변경 내용 커밋 |
| `git commit -am "메시지"` | add + commit (새로 추가된 파일이 없을 때 한정) |
| `git log` | 커밋 히스토리 (종료 :q) |
| `git diff` | 두 지점 사이의 변경 사항을 비교, 차이점(위 k, 아래 j, 종료 :q) |
| `git reset --hard 돌아갈 커밋 해시` | 원하는 시점으로 돌아간 뒤 이후 내역 삭제 |
| `git rm 파일명` | 삭제 |
| `git revert --continue` | |
| `git remote add origin [주소]` | 원격 저장소 연결 |
| `git push -u origin main` | 첫 업로드 |
| `git clone 주소` | 로컬로 저장소 클론 |
| `git push` | 이후 업로드 |
| `git mv 원래파일명.md 바꿀파일명.md` | 파일명 변경 |

---

### 🧭 Git 업로드
```bash
// Github에 새 저장소를 만들어 연결할 때
git init
git add .
git commit -m ""
git remote add origin [URL]
git push -u origin main

// 기존 저장소 clone
git clone [URL]
git add .
git commit -m ""
git push

// 이미 작업 중
git add .
git commit -m ""
git push

// 최신 변경 내용 병합
git add .
git status
git pull origin main

// Sparse Checkout
git clone --filter=blob:none --no-checkout [저장소 주소]
cd [저장소 폴더]
git sparse-checkout init --cone
git sparse-checkout set docs src
git checkout

```
---

📘 **작성자:** kkaengji
📅 **최종 업데이트:** 2025-10-14  <br />
* [git + bash](https://git-scm.com/)
* [SourceTree](https://www.sourcetreeapp.com/)
* [.gitignore 형식](https://git-scm.com/docs/gitignore/)
* [출처](https://www.yalco.kr/lectures/git-github/)
