---
title: "Configure Strategy(passport-local)"
tag: 
- 
---
# Configure Strategy (passport-local)
>[[Configure Strategy]]
>- [[bcrypt#檢查密碼]]：登入時加密
```js
passport.use(new LocalStrategy(
	(username, password, done) => {
		User.findOne({ email: username }.then(async (user) => {
			if (!user) {
				// 不進行認證
				return done(null, false);
			}
			await bcrypt.compare(password, user.password, function(err, result) {
				if (err) {
					return done(null, false);
				}
				if (!result) {
					return done(null, false);
				} else {
					return done(null, user);
				}
			});
		}).catch(err) {
		 return done(null, false);
		});
	})
	);
```