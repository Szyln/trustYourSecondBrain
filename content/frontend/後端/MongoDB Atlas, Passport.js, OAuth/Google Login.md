# Google Login

- 檢查是否有設定 [[Configure Strategy(passport-google)]]
		- 否：
		- 是：得到客戶端 ID 跟密碼與 Google 取得資料後，導向 [[Configure Strategy]] 設定的 callbackURL
```js
// google
router.get('/google',
	// 這是一個 middleware
	// 透過 passport 與取得 google 驗證
	// 對應 config/passport.js 的設定
	passport.authenticate('google', {
		// 取得 google 的 profile, email 資料
		scope: ['profile', 'email'],
	});
);
```
> - callbackURL 需要在	Google Cloud Platform 設定：[[Web Application Client ID 設定]]
> - 導過去之後的行為：[[Passport Verified Callback]]
>- [[req.user]]

## （選用）google 登入可選擇登入帳號
```js
router.get('/google',
	passport.authenticate("google", {
		scope: ["profile", "email"],
		prompt: "select_account",
	})
);
```