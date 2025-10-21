# 🧭 GitHub 
* [git + bash](https://git-scm.com/)
* [SourceTree](https://www.sourcetreeapp.com/)
* [.gitignore 형식](https://git-scm.com/docs/gitignore/)
  
## 1. Git 최초 설정
Git 전역으로 사용자 이름과 이메일 주소를 설정 (GitHub 계정과는 별개)
```bash
git config --global user.name "본인 이름"
git config --global user.email "본인 이메일"

# 기본 브랜치명 변경
git config --global init.defaultBranch main
```

## 2. 프로젝트 생성 & Git 관리 시작
```bash
git init
git status
```

## 3. Git에서 과거로 돌아가는 두 방식
- reset : 원하는 시점으로 돌아간 뒤 이후 내역들을 삭제
```bash
git log # 되돌아갈 시점의 커밋 해시 복사
git reset --hard (돌아갈 커밋 해시)

# reset 하기 전 시점으로 복원 (.git 복원 후 사용)
git reset --hard 
```
> SourceTree <br>
: 해당 커밋에 마우스 우클릭 - 이 커밋까지 현재 브런치를 초기화 Hard

- revert : 되돌리기 원하는 시점의 커밋을 거꾸로 실행합니다.
```bash
git log # 되돌릴 커밋 해시 복사
git revert 되돌릴 커밋 해시 #:wq로 커밋 메시지 저장

# 오류 시 해결 후
git revert --continue

# 커밋해버리지 않고 revert
git revert --no-commit 되돌릴  커밋 해시
```
> SourceTree <br>
: 해당 커밋에 마우스 우클릭 - 커밋 되돌리기

## 4. Branch 
```bash
git branch add-coach  # add-coach라는 브랜치 생성
git branch # 브랜치 목록 확인
git switch add-coach # 해당 브랜치로 이동
git switch -c new-teams # 브랜치 생성과 동시에 이동
git branch -d 삭제할 브랜치명 # 브랜치 삭제
git branch -D 강제삭제할 브랜치명
git branch -m (기존 브랜치명) (새 브랜치명) # 브랜치 이름 변경
git log --all --decorate --oneline --graph # 브랜치 내역 보

```



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

### 상황별 예시
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

```
---

📘 **작성자:** kkaengji
📅 **최종 업데이트:** 2025-10-14  
**출처:** [https://www.yalco.kr/@git-github/2-1/](https://www.yalco.kr/lectures/git-github/)
