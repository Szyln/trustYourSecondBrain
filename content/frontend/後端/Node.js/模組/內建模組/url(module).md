---
title: "url(module)"
tag: 
- 
---
# url 模組
```js
const url = reuqire('url');

const blaURL = 'http://126.0.0.0:5501/blablabla.html?inputName=Peter'
const parsedURL = url.parse(blaURL, true); // string -> array

// 取得網址第一段（126.0.0.0:5501）
console.log(parsedURL.host);

// 取得網址第一段，不包含 port（126.0.0.0）
console.log(parsedURL.hostname);

// 取得路徑（/blablabla.html）
console.log(parsedURL.pathname);

// 取得路徑＋query(/blablabla.html?inputName=Peter)
console.log(parsedURL.path);

// 取得 query
console.log(parsedURL.query);
// 取得 query 的特定內容
console.log(parsedURL.query.email);
```
>[[類型轉換#JSON]]：parse() 是 string -> array


- host：[[IP]] + [[Port]]
- hostname：[[IP]]
- pathname：路徑
- path: 路徑 + [[Query]]
- query: [[Query]]

[[內建模組(Node.js)]]
#js #library #framework #nodeJs #backEnd #module