---
title: "req.user"
tag: 
- 
---
# req.user
客戶端使用者的資料（設定 passport 之後可以用的資料）
```js
router.get('/', (req, res) => {
	res.render('page', { req.user });
})
```

可以使用像類似這種資料
```js

<%= user.name %>
<%= user.name %>
<%= user.thumbnail %>
<%= user.date %>
```