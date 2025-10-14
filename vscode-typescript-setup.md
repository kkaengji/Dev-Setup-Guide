# 🧩 Visual Studio Code & TypeScript 개발 환경 세팅 가이드

---

## 💻 Visual Studio Code (VS Code)

### 🧰 추천 확장 프로그램

| 확장 프로그램 | 설명 | 비고 |
|----------------|------|------|
| **Prettier - Code Formatter** | 코드를 일관된 스타일로 자동 포맷팅 | ⚙️ **설정 방법**<br>① `Ctrl + ,` → 설정창 열기<br>② `format on save` 검색 후 체크<br>③ `default formatter` 검색 → `Prettier` 선택 |
| **ESLint** | 코드의 오류 및 잠재적인 문제점 탐지 | 코드 품질 유지 |
| **Live Server** | HTML, CSS, JS 실시간 미리보기 서버 실행 | 프론트엔드 로컬 서버 |
| **Material Icon Theme** | 파일 아이콘을 구분하기 쉽게 변경 | 디자인 향상 |
| **Error Lens** | 에러 및 경고를 코드 라인에 인라인 표시 | 디버깅 효율 ↑ |

---

### ⚛️ React Developer Tools

**📦 크롬 확장 프로그램 링크:**  
🔗 [React Developer Tools](https://chromewebstore.google.com/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=ko&pli=1)

---

### 💡 그 외 확장 프로그램 추천

📚 참고 링크 →  
🔗 [VSCode 필수 확장 프로그램 TOP 10 (2025)](https://devnam.tistory.com/entry/VSCode-%ED%95%84%EC%88%98-%ED%99%95%EC%9E%A5-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%A8-TOP-10-2025%EB%85%84-%EC%B5%9C%EC%8B%A0)

---

## 🧠 TypeScript 개발 환경

### 📦 설치해야 할 프로그램

| 프로그램 | 설명 |
|-----------|------|
| **VS Code** | 코드 에디터 |
| **TypeScript** | TS 언어 컴파일러 |
| **Scoop** | 윈도우용 패키지 매니저 |
| **Node.js** | JS 런타임 환경 |
| **Git Bash** | Git 및 Bash 터미널 |

---

### 🧾 설치 확인 명령어

```bash
node -v      # Node.js 버전 확인
npm -v       # NPM 버전 확인
tsc -v       # TypeScript 버전 확인
```

---

### 💻 PowerShell 터미널 명령어

| 명령어 | 설명 |
|--------|------|
| `scoop list` | Scoop으로 설치된 프로그램 목록 확인 |
| `scoop install <프로그램명>` | Scoop으로 새로운 프로그램 설치 |

**예시:**
```bash
scoop install nodejs
scoop install git
scoop install python
```

---

📘 **작성자:** kkaengji
📅 **최종 업데이트:** 2025-10-14  
