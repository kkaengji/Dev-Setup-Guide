# 🍃 MongoDB
```bash
$ mongosh
> use testdb
```
- mongosh는 **MongoDB 전용 터미널(셸)**
- use testdb는 ‘testdb’라는 이름의 데이터베이스로 전환하는 명령어 (만약 해당 DB가 없으면 자동으로 생성)

---

## MongoDB CRUD 핵심 정리
### 🟢 **삽입 (Insert)**  
```
insertOne()   → 단일 데이터 삽입
ex) db.users.insertOne({ name: "Nam", age: 30 })

insertMany()  → 여러 데이터 한 번에 삽입
ex) db.users.insertMany([
  { name: "Mina", age: 25 },
  { name: "Bak", age: 27 }
])
```

### 🔍 **조회 (Find)**
```
find()                            → 전체 조회
find(filter)                      → 조건 조회
find(filter, projection)          → 조건 + 특정 필드만 표시

비교 연산자:
  $gt   → 초과 (greater than)
  $gte  → 이상 (greater than or equal)
  $lt   → 미만 (less than)
  $lte  → 이하 (less than or equal)
  $ne   → 같지 않음 (not equal)
  $in   → 포함 (in)
  $nin  → 포함되지 않음 (not in)

ex)
db.users.find({ age: { $gte: 25 } })
db.users.find({ age: { $gt: 25 } }, { name: 1, _id: 0 })
```

### 🔢 **정렬 (Sort)**
```
.sort({ 필드명: 1 })   → 오름차순 정렬 (작은 → 큰)
.sort({ 필드명: -1 })  → 내림차순 정렬 (큰 → 작은)

ex)
db.users.find().sort({ age: 1 })
db.users.find().sort({ age: -1 })
```

### 🎯 **제한 (Limit)**
```
.limit(숫자)               → 조회 결과 개수 제한
.sort().limit()            → 정렬 + 제한 동시 적용

ex)
db.users.find().limit(2)
db.users.find().sort({ age: 1 }).limit(1)
```

### 🛠️ **수정 (Update)**
```
updateOne(filter, update)   → 조건에 맞는 첫 번째 문서 수정
updateMany(filter, update)  → 조건에 맞는 여러 문서 수정

수정 연산자:
  $set    → 필드 값 추가 또는 변경
  $unset  → 필드 삭제

ex)
db.users.updateOne({ name: "Nam" }, { $set: { age: 29 } })
db.users.updateMany({ age: { $lte: 30 } }, { $set: { status: "veteran" } })
db.users.updateOne({ name: "Mina" }, { $unset: { gender: "" } })
```

### 🔴 **삭제 (Delete)**
```
deleteOne(filter)   → 조건에 맞는 첫 번째 문서 삭제
deleteMany(filter)  → 조건에 맞는 여러 문서 삭제

ex)
db.users.deleteOne({ name: "Nam" })
db.users.deleteMany({ age: { $lt: 31 } })
```

### 💡 **요약 한눈에 보기**
```
삽입: insertOne(), insertMany()
조회: find(), find(filter), find(filter, projection)
비교: $gt, $gte, $lt, $lte, $ne, $in, $nin
정렬: .sort({ 필드명: 1 }), .sort({ 필드명: -1 })
제한: .limit(숫자), .sort().limit()
수정: updateOne(), updateMany() + $set, $unset
삭제: deleteOne(), deleteMany()
```

---

# Mongoose + Express (Node.js 서버에서 MongoDB 연결)
```
$ npm install mongoose dotenv   # MongoDB 연결 및 환경 변수 관리용 패키지 설치
$ npm i express                 # 서버 구축용 프레임워크 Express 설치
```
