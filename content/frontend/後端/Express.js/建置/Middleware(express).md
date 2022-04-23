---
title: "Middleware(express)"
tag: 
- 
---
# Middleware
- 一種 function
- 在 [[Express Life Cycle 生命週期]] 正中間（接收請求到收到回應間）執行
- 每次獲得請求（ 不論哪種 [[HTTP Verbs]] 的請求）就會執行一次
- 每個 Middleware (`app.use(function)`)都可以讀取 req, res 以及下一個 middleware function

---
## 套用 Middleware
- 需要CSS：[[Express 的 CSS 樣式環境建置 (Serving a Static File)]]
- 需要 POST 表單：[[POST 表單(express)]] 用：[[body-parser]]

## 撰寫 Middleware
- [[撰寫 Middleware]]


#js #advanceJs #library #framework #nodeJs #backEnd #module #expressJs #npm #server 