# 🚀 Zero to Deploy: 개발 환경 & 터미널 명령어 치트시트

---

## 🗂️ 1. 파일 및 디렉토리 이동 / 관리

| 명령어 | 설명 |
|--------|------|
| `pwd` | 현재 디렉토리 경로 확인 |
| `ls` | 현재 폴더 내 파일/폴더 목록 보기 |
| `ls -a` | 숨김 파일(`.`으로 시작하는 파일)까지 모두 보기 |
| `cd ~` | 홈 디렉토리로 이동 |
| `cd ..` | 상위 폴더로 이동 |
| `cd '경로'` | 특정 경로로 이동 |
| `mkdir 폴더명` | 새 폴더 생성 |
| `rmdir 폴더명` | 비어있는 폴더 삭제 |
| `rm 파일명` | 파일 삭제 |
| `rm -rf 폴더명` | 폴더 및 내부 파일 강제 삭제 (⚠️ 주의!) |
| `mv 원래이름 새이름` | 파일 또는 폴더 이름 변경 / 이동 |
| `cp 파일명 새위치` | 파일 복사 |
| `cp -r 폴더명 새위치` | 폴더 전체 복사 |
| `touch 파일명` | 새 파일 생성 |
| `code .` | 현재 폴더를 VS Code로 열기 |
| `open .` (Mac) / `explorer .` (Windows) | 현재 폴더를 파일 탐색기로 열기 |

> 💡 **팁**
> - `ls -lh`: 파일 크기를 보기 좋게 표시  
> - `ls -al`: 권한/날짜 등 자세히 보기  
> - `rm -rf`: **되돌릴 수 없으므로 주의!**

---

## ⚛️ 2. React 프로젝트 생성 명령어

### 🔹 Vite (최신 권장)
```bash
npm create vite@latest
```

### 🔹 Create React App (CRA)
```bash
npx create-react-app [프로젝트명]
```

### 🔹 Next.js (버전별)
```bash
npx create-next-app@14 [프로젝트명]    # Next.js 14 버전 기반
npx create-next-app@latest [프로젝트명] # 최신 버전
```
<img width="566" height="141" alt="캡처" src="https://github.com/user-attachments/assets/9064622a-4883-45a0-b870-980a87cca050" />

#### eslintrc.config.json
```bash
const eslintConfig = [
  ...compat.extends("next/core-web-vitals", "next/typescript"),
  {
    // 이 부분 추가
    rules: { 
      "@typescript-eslint/no-unused-vars": "warn", //사용하지 않는 변수가 있을 때 경고로 표시
      "@typescript-eslint/no-explicit-any": "off", //any 타입을 명시적으로 정의할 수 있도록 허용
    },
  },
];
```
---

## ⚙️ 3. 프로젝트 초기 설정 및 실행

| 명령어 | 설명 |
|--------|------|
| `npm init -y` | Node.js 프로젝트 초기화 |
| `npm install` | 의존성 설치 (node_modules 생성) |
| `npm run build` | 배포용 빌드 파일 생성 |
| `npm run start` | 프로덕션 모드 실행 (CRA / Next.js) |
| `npm run dev` | 개발 모드 실행 (Vite) |
| `touch .gitignore` | 버전 제외 파일 목록 생성 |
| `ctrl + c` | 실행 중인 서버 종료 (터미널 강제 종료) |

### ⚙️ 3-1. 필수 라이브러리 & 유틸리티 설치
📦 기본 개발 도구
```bash
npm i @types/node        # Node.js 타입 정의 추가
npm i -g typescript      # TypeScript 전역 설치
npm i -g nodemon         # 서버 자동 재시작 유틸리티
```
🎨 스타일링 관련
```bash
npm i tailwindcss @tailwindcss/vite  # Tailwind CSS 및 Vite 플러그인
```
🚀 배포 도구
```bash
npm i -g vercel           # Vercel CLI 전역 설치
```
✅ 
- TypeScript + Node 환경: @types/node, typescript 
- 스타일링: tailwindcss, @tailwindcss/vite
- 자동 실행: nodemon
- 배포용 CLI: vercel

---


## 🧭 4. Git 버전 관리 (로컬 + 원격)

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

---

## 🧩 5. TypeScript 기본 명령어

| 명령어 | 설명 |
|--------|------|
| `npm init` | 프로젝트 초기화 |
| `npm i @types/node` | Node 타입 정의 추가 |
| `npm install -g typescript` | TypeScript 전역 설치 |
| `tsc -v` | TypeScript 버전 확인 |
| `tsc src/index.ts` | TS → JS 컴파일 |
| `node src/index.js` | JS 파일 실행 |
| `npm install -g tsx` | TSX 실행기 설치 |
| `tsx src/index.ts` | TS 파일 직접 실행 |
| `tsc --init` | tsconfig.json 생성 |
| `tsc` | 전체 TS 프로젝트 컴파일 |

---

## 🧮 6. Prisma + 데이터베이스 명령어

| 명령어 | 설명 |
|--------|------|
| `npx prisma db push` | Prisma 스키마를 데이터베이스에 반영 |
| `npx prisma studio` | Prisma Studio 실행 (DB 시각화 도구) |
| `npm run seed` | 초기 데이터(seeding) 실행 |

---

## 🌈 7. Tailwind CSS 설치 및 적용
https://tailwindcss.com/docs/installation/using-vite

| 명령어 | 설명 |
|--------|------|
| `npm install tailwindcss @tailwindcss/vite` | Tailwind CSS와 Vite 전용 플러그인 설치 |
| `npx tailwindcss init -p` | Tailwind 초기화 파일 생성 |

---

## 🌐 7. Vercel 배포 과정

| 명령어 | 설명 |
|--------|------|
| `npm run build` | 배포용 빌드 파일 생성 (`dist` 또는 `build` 폴더) |
| `npm install -g vercel` | Vercel CLI 전역 설치 (최초1회) |
| `vercel login` | 이메일 인증 로그인 (최초1회) |

---

## 💡 빠른 실행 요약

### ⚛️ React (Vite)
```bash
npm create vite@latest .
npm install

npm install tailwindcss @tailwindcss/vite

npm run dev
```

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
