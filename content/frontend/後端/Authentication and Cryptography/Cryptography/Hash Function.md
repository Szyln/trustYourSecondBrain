---
title: "Hash Function"
tag: 
- 
---
# Hash Function
>[[bcrypt]]


- 將密碼存入 [[Database 數據庫]]前，會先用 Hash Function 加密
- 以目前技術近乎不可逆
- 不管原始密碼(input)多少，Hash Function 都會產生相同長度的 [[Cipher]]
- 原始密碼做些微的更動後，[[Cipher]] 會有很大的差異
- 但是同樣的 input 會得到相同的結果 -> [[Dictionary Attack]] -> [[Salting]]

## 問題：[[Dictionary Attack]]
由於同一個密碼 Hash Function 的結果一樣，駭客會透過 [[Dictionary Attack]] 的方法破解

### 解決方式：[[Salting]]

#cryptogrphy 