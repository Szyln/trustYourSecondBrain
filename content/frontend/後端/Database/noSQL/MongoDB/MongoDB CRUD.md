---
title: "MongoDB CRUD"
tag: 
- 
---
# MongoDB CRUD
[[DBMS(RDBMS)]] 都有一套自己的 [[Database 數據庫#C R U D]]
[CRUD](https://docs.mongodb.com/manual/crud/)
- Insertion(create): [[MongoDB CRUD#Insertion create]]
- Find(read):[[MongoDB CRUD#find read]]
- Update: [[MongoDB CRUD#Update]]
- Delete: [[MongoDB CRUD#Delete]]

## Insertion(create)
新增 collection，裡面就放一個 object
```js
// shell
db.students.insertOne({
	name: "Sam",
	age: 22,
	major: "Computer Science",
	scholarship: {
		merit:3000,
		other: 1400
	}
})
```
```js
// 回傳
{
	"acknowledged": true,				// 確認傳成功
	"insertedId": ObjectId("blabla")
}
```
> `ObjectId("blablabla")`跟[[SQL 的 Keys]]中的 Primary Key 意思一樣

### 新增多個 collections
`.inserMany()`裡面限定放 array
```js
db.students.insertMany([
	{
		name: "",
		age: ,
		major: ,
		scholarship: {
			merit: ,
			other: ,
		}
	},
	{
		name: "",
		age: ,
		major: ,
		scholarship: {
			merit: ,
			other: ,
		}
	},
])
```
> 回傳與 `.insertOne`一樣，`ObjectID`
### 多個或單個 collection
回傳比較簡略
```js
db.students.insert({放一個物件})
db.students.insert([多個物件])
```
```js
// 他會回傳
WriteResult({ "nInserted": 放入了多少個物件 })
```



## find(read)
### 查看 collection
新增 collection 之後就可以用這個功能找到，看裡面的內容
```js
// 兩種都可，查看 students 這個 collection
db.students.find()
db.students.find({})
```
```js
// 會回傳 ObjectId 跟物件本身
```
### 找到符合條件的項目
像[[mySQL#顯示符合條件的內容]]的功能
```js
db.students.find({ age: 10 })
```
```js
// 會回傳符合條件的內容
```
#### Nesting Object
如果要找物件裡的物件的話
```js
db.students.find({
	"scholarship.merit": 2500
})

```
#### 比較(comparison operator)
[comparison operator](https://docs.mongodb.com/manual/reference/operator/query-comparison/#std-label-query-selectors-comparison)
##### $gt
```js
db.students.find({
	"scholarship.merit": {$gt: 1500}	// 大於 1500
})

```
##### $in
```js
db.students.find({
	"major": {$in: ["design", "chemical"]}	// 大於 1500
})

```

#### 邏輯([logical query operators](https://docs.mongodb.com/manual/reference/operator/query-logical/))
##### AND
```js
db.students.find({
	$and: [
		{ <expression1> }, 
		{ <expression2> } ,
		... ,
		{ <expressionN> } 
	] 
})
```
##### OR
```js
db.inventory.find({
	$or: [
		{ quantity: { $lt: 20 } }, 
		{ price: 10 } 
	] 
})
```



## Update
### 修改第一個符合條件的內容
```js
// 修改第一個符合條件的內容
db.students.updateOne(
	{ name: "Sam" },		// 設定條件
	{
		$set: {				// 設定修改後內容
			name: "John",
			major: "Design"
		}
	},
	$currentDate: {			// 顯示最終更新日期
		lastModified: true
	}

)
```
### 修改所有符合條件的內容
```js
// 修改第一個符合條件的內容
db.students.updateMany(
	{ major: "Design" },		// 設定條件
	{
		$set: {					// 設定修改後內容
			major: "Graphic Design"
		}
	},
	$currentDate: {				// 顯示最終更新日期
		lastModified: true
	}

)
```


## Delete

```js
db.students.deleteOne({物件});
db.students.deleteMany({});		// 全刪
db.students.deleteOne({ major: "design" })	// 刪掉符合條件的
```


#database #mongodb #json