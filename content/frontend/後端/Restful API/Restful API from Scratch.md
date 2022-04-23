---
title: "Restful API from Scratch"
tag: 
- 
---
# Restful API from Scratch
從頭開始製作一個 Restful API （以 [[Express and Mongoose]] 改寫）
把原本要拿來顯示在網頁上的東西（EJS），用資料的方法送給 API 用戶

## 步驟
[[建置（連接數據庫的表單）]]中 [[Request handling（搭配數據庫CRUD）]]需要更動的有；
- 不用網頁的介面
	- Homepage 不用了
	- EJS 也不用了
	- 也不用提供表單了
	- 傳送的內容幾乎都是 [[Object]] 格式
	- 也不用傳 console.log 的資料了

| 動作           | 網頁版                                          | Restful API 版             |
|:-------------- |:----------------------------------------------- |:-------------------------- |
| [[Find(Read)]] | [[將數據庫資料顯示於網頁]]                      | [[API 提供所有資料]]       |
| [[Find(Read)]] | [[使用 Routing for pattern 顯示特定數據庫物件]] | [[API 提供特定資料]]       |
| [[Create]]     | [[表單資料存入數據庫]]                          | [[API 提供新增資料的管道]] |
| [[Update]]     | [[表單更新數據庫既有資料]]                      | [[API 提供更新資料的管道]] |
| [[Delete]]     |               | [[API 提供刪除資料的管道]]|




#api #js #restfulapi #api #crud #database #json 