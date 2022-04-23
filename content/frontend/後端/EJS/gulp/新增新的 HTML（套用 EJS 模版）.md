# HTML 架構
- gulp 內可以新增 html 檔案，表頭上加上以下內容，就可以套用想要用的 EJS 模版
- 用 live server 檢視時，在網址後面補上這個檔案名稱（`檔名.html`）即可
```html
---
title: <title>
layout: ./app/layout.ejs
engine:ejs
current:index
---

<body 內容>

```
> HTML 放在 `app` 下
> EJS 也放在 `app` 下，可以開資料夾放
> [[資料夾架構]]
#gulp

