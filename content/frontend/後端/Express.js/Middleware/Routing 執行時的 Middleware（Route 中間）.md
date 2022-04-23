---
title: "Routing 執行時的 Middleware（Route 中間）"
tag: 
- 
---

# Routing 執行時的 [[Middleware(express)]]（route 中間）
- 之後在驗證單元會常用到
- 可以一個以上
```js
// 通常不會這樣寫，會先把 middleware 存進變數內
// 在第二個參數加入 middleware
app.get('/student',
	(req, res, next) => {
		console.log('middleware');
		next();
	},
	(req, res) => {
		res.send('student page');
	}
);
```

```js
const studentMiddleware = function(req, res, next) {
		console.log('middleware');
		next();
};

const secondStudentMiddleware = function(req, res, next) {
		console.log('middleware');
		next();
};
			
// 在第二個參數加入 middleware
// 可以多個
app.get('/student',
	studentMiddleware,
	secondStudentMiddleware
	(req, res) => {
		res.send('student page');
	}
);
```

#js #advanceJs #library #framework #nodeJs #backEnd #module #expressJs #npm #server 