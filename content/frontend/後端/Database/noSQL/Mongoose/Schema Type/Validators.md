# Validators
[官方文件](https://mongoosejs.com/docs/schematypes.html#string-validators)

> [[Schema Type#簡易寫法]] 可以簡單的做規範，但通常都還是會搭配 [[Validators]] 來寫


在 [[Mongoose]] 也可以用 [[Validators]] 規範 [[Schema Type]] 

>類似 [[SQL create 製作表格]] 中有提到 [[Constraints]] 可以將資料內容做規範

## Shcema Type 的 [[Validators]]
- [[String 用 Validators]]
- [[Number 用 Validators]]
- [[通用的 Validators]]

## [[Database 數據庫#C R U D]] 的 [[Validators]]

[[Update with Validators]]


## 特性
- 輸入的資料不完全符合 validators 的話，還是有機會送成功
```js
// create an object
const newStudent = new Student({
	age: 18,
	scholoarship: { merit: "1500", other: "2000" }	
	// 在 number 的類型欄位送出 string
})
// 可以成功
```

- 如果送出不存在的 Schema ，不會產生 error ，但也不會存進 DB 裡面
- [[Validators]] 只有在一開始 set 的時候會做驗證，後續跑像是 [[Update]] 的功能就不會再驗證了


#database #nosql #mongoose #mongodb #validators