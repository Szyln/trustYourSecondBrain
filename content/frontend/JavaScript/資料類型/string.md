---
title: "string"
tag: 
- 
---
# string
## string 的串接
可以做串接（+），但不能做運算（加減乘除）
### string concatenate 串接
concatenate 簡稱 concat
```js
let str = `hi` + ", I am fine."
```

> 但在 python 可以做乘法

### string number concat
數字可以串接字串


|兩個資料類型|執行動作|
|-|-|
|string + 任意|串接|
|number + number|運算|
```js
1 + 100 + "1000" + 3 + 6
// 答案是：101100036

// 運算順序是左到右
// "1001000" + 3 + 6
// "10010003" + 6
```

## 其他功能
-   扣除字尾空白｜.trim（不更改原字串）

### 組合字與變數｜[[Template literals (Template strings)]](ES6)


## 邏輯
string 可以做邏輯判斷，只看字首順序
```js
"A" > "B" // true 因為 字母 A 比 B 早出現
"Apple" > "Banana" // true 只看字首的順序
"20" > "100" // true 只看字首順序

```

#js #dataType 