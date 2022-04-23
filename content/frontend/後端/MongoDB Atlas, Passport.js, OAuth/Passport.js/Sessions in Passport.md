# Sessions in Passport
>- 需安裝 [[cookie-session]]
>- [passport.js doc>configure](https://www.passportjs.org/docs/configure/)

僅將 userID 存進 [[Session]]
```js
// index.js
// cookie session 的 middleware 之後
app.use(passport.initialize());
app.use(passport.session());
```
```js
// import 之後
// serialize
passport.serializeUser((user, done) => {
	console.log('Serializing user now');
	// mongoDB 存取的 id 要加底線（我不懂）
  done(null, user._id);
});
// deserialize
passport.deserializeUser((_id, done) => {
	console.log('Deserializing user now');
  User.findById({ _id }).then(() => {
		console.log('found user.')
		done(null, user);
  });
});
```
>[[Find(Read)]]


#session #authentication #oauth #expressJs 