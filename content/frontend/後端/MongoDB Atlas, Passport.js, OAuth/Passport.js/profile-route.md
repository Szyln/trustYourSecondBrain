# profile-route
>[[Authenticate Requests]]

[[登入後]] 會顯示 profile.ejs 頁面

>[[登入前後頁面的變化]]
## 匯出匯入
```js
// routes/profile-route.js
const router = require('express').Router();
// 新增貼文用
const Post = reuqire('../models/post-model');
```

```js
// 最後匯出
export.modules = router;
```
## middleware
`/profile` 的路徑會先執行 profile-route 模組
```js
// index.js
const profileRoute = require('./routes/profile-route');

// middleware
app.use('/profile', profileRoute);
```
>[[建置生命週期（MongoDB Atlas, Passport. OAuth）]]

## profile-route
>[[req.user]]
>[[res.redirect()]]
>[[req.isAuthenticated()]]
```js
// routes/profile-route.js

// 只給特定 route 用的 middleware 
const authCheck = (req, res, next) => {
	if(!req.isAUthenticated) {
		res.redirect('/auth/login');
	} else {
		next();
	}
}

// 使用 req.user
// /profile 請求中，客戶端會先經過 authCheck
// 如果尚未認證會導去登入畫面，有的話就會執行這個 route
// render porfile 頁面
router.get('/', authCheck, (req, res) => {

	res.render('profile', { user: req.user });
})
```
>[[Routing 執行時的 Middleware（Route 中間）]]

## profile 新增貼文
再新增一個 [[post-model.js]] 來儲存貼文的數據
```js
// routes/profile-route.js
// 匯入 post-model.js
router.get('/post', authCheck, (req, res) => {
	res.render('post', { user: req.user });
})

router.post('/post', authCheck, async (req, res) => {
	// 看 post.ejs 上面表單送出的 name
	let { title, content } = req.body;
	let newPost = new Post({ title, content, author: req.user._id });
	try {
		await newPost.save();
			res.status(200).redirect('/profile');
	} catch(err) {
		req.flash('error_msg', '標題與內文必填');
		req.redirect('/profile/post');
	}
})

```
>[[Routing 執行時的 Middleware（Route 中間）]]
>新增貼文的 model：[[post-model.js]]
>[[登入前後頁面的變化]]
>[[Form]]
>[[Flash]]：參考[[本地註冊（Local Signup）]]
### 顯示所有貼文
繼續修改顯示 profile 的頁面
```js
router.get('/', authCheck, async (req, res) => {
	// 將 post-model 內的資料顯示到頁面上
	let postFound = await Post.find({ author: req.user._id });
	res.render('profile', { user: req.user, posts: postFound });
})
	
```

```js
// profile.ejs
<% if (posts.length > 0) { %>
	<% for (let i = 0; i < posts.length; i++ ) { %>
		<div class="card" style="width: 18rem">
			<div class="card-body">
				<h5 class="card-title"><%= posts[i].title %></h5>
				<p class="card-text"><%= posts[i].content %></p>
				<a href="#" class="btn btn-primary"><%= posts[i].date %> </a>
			</div>
		</div>
	<% } %>
<% } %>
```
#passport #oauth #authentication #expressJs