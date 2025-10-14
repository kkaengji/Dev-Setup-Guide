# ⚡ React + TypeScript + Prisma + Vercel 종합 터미널 명령어 치트시트

---

## 🗂️ 1. 파일 및 디렉토리 이동 / 관리

| 명령어 | 설명 |
|--------|------|
| `cd ~` | 홈 디렉토리로 이동 |
| `cd ..` | 상위 폴더로 이동 |
| `cd '경로'` | 특정 경로로 이동 |
| `code .` | 현재 폴더를 VS Code로 열기 |

---

## ⚛️ 2. React 프로젝트 생성 명령어

### 🔹 Vite (최신 권장)
```bash
npm create vite@latest .
```

### 🔹 Create React App (CRA)
```bash
npx create-react-app my-app
```

### 🔹 Next.js
```bash
npx create-next-app@latest
```

---

## ⚙️ 3. 프로젝트 초기 설정 및 실행

| 명령어 | 설명 |
|--------|------|
| `npm init -y` | Node.js 프로젝트 초기화 |
| `npm install` | 의존성 설치 (node_modules 생성) |
| `npm run dev` | 개발 서버 실행 (Vite) |
| `npm run start` | 개발 서버 실행 (CRA / Next.js) |
| `touch .gitignore` | 버전 제외 파일 목록 생성 |

---

## 🧭 4. Git 버전 관리 (로컬 + 원격)

| 명령어 | 설명 |
|--------|------|
| `git init` | Git 저장소 초기화 |
| `git add .` | 모든 변경 파일 추가 |
| `git commit -m "메시지"` | 변경 내용 커밋 |
| `git remote add origin [주소]` | 원격 저장소 연결 |
| `git push -u origin main` | 첫 업로드 |
| `git push` | 이후 업로드 |

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

## ⚛️ 6. React + TypeScript 통합

| 명령어 | 설명 |
|--------|------|
| `npx create-react-app .` | 현재 폴더에 React 프로젝트 생성 |
| `npm i @types/node @types/react @types/react-dom @types/jest` | 타입 정의 패키지 설치 |
| `npx create-react-app my-app --template typescript` | TypeScript 템플릿으로 생성 |
| `npm run start` | 개발 서버 실행 |

---

## 🧮 7. Prisma + 데이터베이스 명령어

| 명령어 | 설명 |
|--------|------|
| `npx prisma db push` | Prisma 스키마를 데이터베이스에 반영 |
| `npx prisma studio` | Prisma Studio 실행 (DB 시각화 도구) |
| `npm run seed` | 초기 데이터(seeding) 실행 |

---

## 🚀 8. 빌드 및 실행 / 종료

| 명령어 | 설명 |
|--------|------|
| `npm run build` | 배포용 빌드 파일 생성 |
| `npm run start` | 빌드된 프로젝트 실행 |
| `ctrl + c` | 실행 중인 서버 종료 (터미널 강제 종료) |

---

## 🌐 9. Vercel 배포 과정

| 명령어 | 설명 |
|--------|------|
| `npm run build` | 배포용 빌드 파일 생성 (`dist` 또는 `build` 폴더) |
| `npm install -g vercel` | Vercel CLI 전역 설치 |
| `vercel login` | 이메일 인증 로그인 |
| `vercel` | 프로젝트 배포 실행 |
| ✅ 결과 | 자동 URL 생성 → `https://프로젝트명.vercel.app` |

---

## 💡 빠른 실행 요약

### ⚛️ React (Vite)
```bash
npm create vite@latest .
npm install
npm run dev
```

### ⚛️ React + TypeScript
```bash
npx create-react-app my-app --template typescript
cd my-app
npm run start
```

### 🧭 Git 업로드
```bash
git init
git add .
git commit -m "init"
git remote add origin [URL]
git push -u origin main
```

### 🧩 TypeScript 실행
```bash
npm init
npm i @types/node
tsc --init
tsc
node dist/index.js
```

### 🧮 Prisma + Seed + 빌드 + 실행
```bash
npx prisma db push
npm run seed
npm run build
npm run start
ctrl + c
```

### 🌐 Vercel 배포
```bash
npm run build
vercel login
vercel
```

---

📘 **작성자:** _Your Name_  
📅 **최종 업데이트:** 2025-10-14  
🔗 **배포용 Markdown 파일 이름:** `react-typescript-prisma-vercel-cheatsheet.md`
