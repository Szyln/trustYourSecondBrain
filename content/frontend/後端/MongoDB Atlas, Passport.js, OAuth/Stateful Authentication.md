---
title: "Stateful Authentication"
tag: 
- 
---
# Stateful Authentication
>[[Session]]
- client 發送的請求時，server 會按照請求在 session memory 中尋找對應的 ID

## 缺點
- 後端有權限刪除資料：如果在後端刪掉了這個對應的 ID，客戶端持有的資料就會失效
- 佔據伺服器資源：因為資料都存在 server，隨著登錄的用戶增加，server 的資源也會被佔用
- 很難擴充：如果伺服器佔滿了，要擴充新的伺服器，要為了新的伺服器寫不同的規則
- 安全性：cookies 可以透過客戶端修改，可能真的試出別人的資料

>[[Stateless Authentication(JWT)]]
#session #authentication #oauth 