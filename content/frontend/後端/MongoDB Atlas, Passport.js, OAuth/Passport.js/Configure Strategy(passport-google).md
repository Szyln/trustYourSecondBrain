---
title: "Configure Strategy(passport-google)"
tag: 
- 
---
# Configure Strategy (passport-google)
>[[Configure Strategy]]

存取（clientID, cilentSecret）導向 [[Configure Strategy]] 設定的 callbackURL



> - callbackURL 需要在	Google Cloud Platform 設定：[[Web Application Client ID 設定]]
> - 導過去之後的行為：[[Passport Verified Callback]]
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
						email: profile.emails[0].value,
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
> - [[dotenv（使用 env 變數）]]
>	 - [[passport-google-oauth20 的 .env 變數]]
>- callbackURL 需要設定：
>	 [[建立 Google 的 OAuth 憑證]]：[[Web Application Client ID 設定]]
