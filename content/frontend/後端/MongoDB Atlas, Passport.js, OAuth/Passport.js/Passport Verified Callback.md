---
title: "Passport Verified Callback"
tag: 
- 
---
# Passport Verified Callback
[[Configure Strategy]] 中的最後一段，設定用戶用 google 登入後的行為

- 數據庫裡有這個用戶嗎（比對 OAuth 提供的 profile）？
	- 有：將這用戶的資料取出
	- 沒有：將這個用戶加 DB


```js
passport.use(new GoogleStrategy({
		// 用 .env 存起來
    clientID: process.env.GOOGLE_CLIENT_ID,
    clientSecret: process.env.GOOGLE_CLIENT_SECRET,
		// 
    callbackURL: "/auth/google/redirect"
  },
	// done 是一個 callback function
	// passport verified callback
	(accessToken, refreshToken, profile, done) => {
		console.log(profile);
		User.findOne({googleID: profile.id})
			.then((foundUser) => {
				if(foundUser) {
					console.log('User already exist');
					done(null, foundUser);
				} else {
					new User({
						name: profile.displayName,
						googeID: profile.id,
						thumbnail: profile.photos[0].value,
					}).save().then((newUser) => {
						console.log('成功透過 google 新增帳戶');
						done(null, newUser);
					})
				}
			})
	}
 )
);
```
```
// 沒有設定的話網頁會顯示：
cannot get /auth/google/redirect
```



