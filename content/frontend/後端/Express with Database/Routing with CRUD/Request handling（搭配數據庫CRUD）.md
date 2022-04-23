---
title: "Request handling（搭配數據庫CRUD）"
tag: 
- 
---
# Request handling（搭配數據庫 CRUD）
- 使用數據庫多會用到 [[Promise]] 的功能
- 需要使用 [[Mongoose]] 進行讀取、存入資料庫的行為

---
## 想要做到的效果
用填入資訊建立 object，並且存入資料庫

```
首頁(localhost)/
|- students/			-> 數據庫資料顯示與網頁	
|	|- insert/			-> accept / reject
|	|- edit/:id			-> 更新資料
|	|- :id			 	-> 網址輸入 id 就顯示對應學生 
```

- [[Find(Read)]]
	- 讀取整個數據庫：[[將數據庫資料顯示於網頁]]
	- 讀取數據庫單一物件：[[使用 Routing for pattern 顯示特定數據庫物件]]
- [[Create]]
	- [[表單資料存入數據庫]]
- [[Update]]
	- [[HTTP request#更新]]
	- [[表單更新數據庫既有資料]]
- [[Delete]]：[[透過 Postman 刪除數據庫資料]]
-  Error handing: [[Routing for all 回應亂打的網址]]：[[404 Not Found]]（一定要放在最後面）


> - [[使用與操作 Mongoose]]
> - [[POST 表單(express)]]

#js #npm #node #expressJs #mongoose #database #form #ejs #backEnd #routing #crud 