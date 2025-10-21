# 🧭 GitHub
- git + bash 🔗https://git-scm.com/
- SourceTree 🔗https://www.sourcetreeapp.com/
  
## 1. Git 최초 설정
Git 전역으로 사용자 이름과 이메일 주소를 설정 (GitHub 계정과는 별개)
```bash
git config --global user.name "(본인 이름)"
git config --global user.email "(본인 이메일)"

# 기본 브랜치명 변경
git config --global init.defaultBranch main
```

## 2. 프로젝트 생성 & Git 관리 시작
```bash
git init
git status
```

## 3. .gitignore 형식
🔗 https://git-scm.com/docs/gitignore 참조
```bash
# 이렇게 #를 사용해서 주석

# 모든 file.c
file.c

# 최상위 폴더의 file.c
/file.c

# 모든 .c 확장자 파일
*.c

# .c 확장자지만 무시하지 않을 파일
!not_ignore_this.c

# logs란 이름의 파일 또는 폴더와 그 내용들
logs

# logs란 이름의 폴더와 그 내용들
logs/

# logs 폴더 바로 안의 debug.log와 .c 파일들
logs/debug.log
logs/*.c

# logs 폴더 바로 안, 또는 그 안의 다른 폴더(들) 안의 debug.log
logs/**/debug.log
```


| 명령어 | 설명 |
|--------|------|
| `git init` | Git 저장소 초기화 |
| `git add .` | 모든 변경 파일 추가 |
| `git commit -m "메시지"` | 변경 내용 커밋 |
| `git remote add origin [주소]` | 원격 저장소 연결 |
| `git push -u origin main` | 첫 업로드 |
| `git clone 주소` | 로컬로 저장소 클론 |
| `git push` | 이후 업로드 |
| `git mv 원래파일명.md 바꿀파일명.md` | 파일명 변경 |

### Git 업로드
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
