## Local Login
[[passport-local]]
```js
// local
router.get('/login', (req, res) => {
	res.render('login', { user: req.user });
});

app.post('/login', 
  passport.authenticate('local', { 
		failureRedirect: '/auth/login',
		failureFlash: '帳密錯誤',
	}),
  (req, res) => {
    res.redirect('/profile');
  });
```