---
title: "編譯 EJS 樣板 res.render()"
tag: 
- 
---
# 編譯 EJS 樣板 res.render ()
> ejs 檔案要放在[[樣板：views 資料夾]]裡
```js
// 單純編譯
// .ejs 可以省略
res.render('page.ejs')
// 搭配變數
res.render('page.ejs'), { name }}
```

>- [[生成與使用 EJS 樣板可用的變數]]
> `{name}` 是 `{ name: name }` 的語法糖

>>指定路徑可能會想用：[[res.redirect()]]
#npm #gulp #html #js #ejs #expressJs 