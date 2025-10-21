# 🧭 1. Git 버전 관리 (로컬 + 원격)

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

```
---

📘 **작성자:** kkaengji
📅 **최종 업데이트:** 2025-10-14  
