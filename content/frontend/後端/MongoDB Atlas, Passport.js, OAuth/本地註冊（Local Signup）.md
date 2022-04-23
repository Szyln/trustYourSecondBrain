# 本地註冊
這個註冊完，存到數據庫後不會有 googleID
```js
// auth-route
// 匯入 bcrypt 做註冊密碼加密
// 匯入 User model
router.get('/signup', (req, res) => {
	res.render('signup', { user: req.user });
})

router.post('/signup', async (req, res) => {
	console.log(req.body);
	let { name, email, password } = req.body;
	// 檢查 email 是否已註冊
	const emailExist = await User.findOne({ email });
	if (emailExist) {
			req.flash('error_msg', 'Email 已經被註冊');
			req.redirect('/auth/signup')
		}
	/////return res.status(400).send('此 email 已註冊');
	// 加密
	const hash = await bcrypt.hash(password, 10);
	let newUser = new User({ name, email, password: hash});
	try {
		// 通常不會顯示給用戶看這個，可以 flash（下一段）
		// const savedUser = await newUser.save();
		// res.status(200).send({
		//	msg: '用戶已儲存',
		//	savedObj: savedUser,
		// });
		await newUser.save();
		req.flash('success_msg','感謝您的註冊，請登入');
		res.redirect('/auth/login')
	} catch(err) {
		req.flash('error_msg', err.errors.name.properties.message);
	}
	res.send('感謝您的註冊');
})
```
>[[Hash Function]]：[[bcrypt]]


## 註冊成功
>[[Sessions in Passport]]
>[[Flash]]
>- [[express-session]]
>- [[connect-flash]]
>- [[cookie-session]]

### middleware(index.js)
```js
// index.js(why
// auth-route 匯入之前
// 為什麼這段又把 cookie-session 刪掉了
// 突然又不用 cookie-session 的 middleware 了
// ?????
// 需要會匯入 express-session, connect-flash

app.use(session({
	secret: process.env.SECRET,
	resave: false,
	saveUninitialized: false
	
}))
// session in passport
app.use(passport.initialize());
app.use(passport.session());
// flash
app.use(flash());
app.use((req, res, next) => {
	res.locals.success_msg = req.flash('success_msg');
	res.locals.error_msg = req.flash('error_msg');
	next();
}) 
```

### message.ejs (partials)
#### include 到會顯示這行訊息的頁面
```js
<!-- signup.ejs -->
<%- include ('partials/message') %>
```
```js
<!-- login.ejs -->
<%- include ('partials/message') %>
```
```js
<% if (error_msg != '') { %>
	<div class="alert alert-warning alert-dismissible fade show" role="alert">
		<strong><%= error_msg %> </strong>
	</div>
<% } %>	
<!-- break -->
<% if (success_msg != '') { %>
	<div class="alert alert-warning alert-dismissible fade show" role="alert">
		<strong><%= success_msg %> </strong>
	</div>
<% } %>	
```

