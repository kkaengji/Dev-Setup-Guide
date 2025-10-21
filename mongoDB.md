# 1. Mongosh
#### MongoDB CRUD 핵심 명령어 요약
- 삽입: insertOne(), insertMany()
- 조회: find(), find(filter), find(filter, projection) + $gt_초과, $gte_이상, $lt_미만, $lte_이하, $ne_같지않음, $in_포함o, $nin_포함x
- 정렬: .sort({ 필드명: 1 }), .sort({ 필드명: -1 })
- 제한: .limit(숫자), .sort().limit()
- 수정: updateOne(filter, update), updateMany(filter, update) + $set_필드 값 추가 또는 변경, $unset_필드 삭제
- 삭제: deleteOne(filter), deleteMany(filter)

---
## 1-1. Mongosh 예시
```bash
$ mongosh

> use testdb

# 컬렉션(users)에 문서 삽입
> db.users.insertOne({name: "Nam", age: 30})
> db.users.insertMany([
> {name: "Mina", age: 25, email: "mina@example.com"},
> {name: "Bak", age: 27, email: "Bak@example.com"}])

# 전체 조회
> db.users.find()

# 조건 필터(나이 > 25)
> db.users.find({age: { $gt: 25 }})

# 정렬(나이 내림차순)
> db.users.find().sort({age: -1})

# 정렬(나이 오름차순) + 다중 정렬(나이, 이름)
> db.users.find().sort({age: 1})
> db.users.find().sort({age: 1, name: 1})

# 페이징: limit
> db.users.find().sort({age: 1}).limit(1)
> db.users.find().sort({age: 1}).limit(2)

# 비교 연산자: >=
> db.users.find({age: { $gte: 26 }})

# 정규표현식으로 문자열 검색
> db.users.find({email: /example/})

# projection: 특정 필드만 표시 (_id 제외)
> db.users.find({}, {name: 1, email: 1, _id: 0})

# 업데이트
> db.users.updateOne({name: "Nam"}, {$set: {age: 29}})
> db.users.updateMany({age: {$lte: 30}}, {$set: {status: "veteran"}})
> db.users.updateOne({name: "Mina"}, {$set: {gender: "female"}})
> db.users.updateOne({name: "Mina"}, {$unset: {gender: ""}}) # 필드 제거

# 삭제
> db.users.deleteOne({name: "Nam"})
> db.users.deleteMany({age: {$lt: 31}})

# 예제 시나리오: 사용자 추가 및 조건 조회
> db.users.insertOne({name: "Nam", age: 30})
> db.users.insertMany([{name: "bak", age: 27}, {name: "lee", age: 33}])
> db.users.find({age: {$gte: 26}}, {name: 1, age: 1})
> exit
```

---

# 2. Mongoose 설치 및 기본 사용법
```bash
# 프로젝트 폴더에서
$ npm init -y
$ npm install mongoose dotenv
$ npm i express # (Express 사용 시)
```
