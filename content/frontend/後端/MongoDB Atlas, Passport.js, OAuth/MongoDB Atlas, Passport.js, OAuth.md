---
title: "MongoDB Atlas, Passport.js, OAuth"
tag: 
- 
---
# MongoDB Atlas, Passport.js, OAuth
```
專案/
|
|– routes/
|   |– auth-routes.js	# Authenticate Request
|– config/
|   |– passport.js   # Cofigure Strategy
|– views/
|   |– ejs 檔案
|– public/
|   |– css 檔案
|– .env
|– index.js
|– 
|– 
```
- [[MongoDB Atlas]]
- [[建置生命週期（MongoDB Atlas, Passport. OAuth）]]
	- [[OAuth]]
		- 登入、登出 routing
		- passport 建置
		- google OAuth 憑證
		- Session （不用每次重開都要登入）

- model
	- [[user-model]]
	- [[post-model.js]]

- [[EJS]] 檔案
	- index.ejs
	- login.ejs
	- profile
	- partial/header.ejs

## 認證類型
- [[Stateful Authentication]]
- [[Stateless Authentication(JWT)]]
