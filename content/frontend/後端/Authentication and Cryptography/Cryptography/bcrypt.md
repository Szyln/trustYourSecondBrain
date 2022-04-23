# bcrypt
[npm](https://www.npmjs.com/package/bcrypt)
業界很有名拿來做 [[Salting]], [[Hash Function]] 的演算法

```js
const bcrypt = require('bcrypt');
const saltRounds = 10;				// cost factor：執行 2 的幾次方次
// const myPlaintextPassword = 's0/\/\P4$$w0rD';
// const someOtherPlaintextPassword = 'not_bacon';
```

## 加密密碼
```js
bcrypt.genSalt(saltRounds, function(err, salt) {
		// myPlaintextPassword 這裡應該輸入原始密碼
		// 例如用戶註冊 post 過來的資訊
		// hash 是已經加密好的 cipher，這個就可以存到 DB 了
    bcrypt.hash(myPlaintextPassword, salt, function(err, hash) {
        // Store hash in your password DB.
    });
});
```
>[[註冊頁面]] 應該加密後再儲存

## 檢查密碼
```js
// Load hash from your password DB.
// myPlaintextPassword: 輸入原始密碼（登入畫面用戶輸入的）
// hash: 存在在 db 裡的 cipher
bcrypt.compare(myPlaintextPassword, hash, function(err, result) {
    // result == true
});
bcrypt.compare(someOtherPlaintextPassword, hash, function(err, result) {
    // result == false
});
```
#cryptogrphy #node #npm #module 