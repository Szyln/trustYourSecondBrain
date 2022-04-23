---
title: "條件簡寫 ternary operator(語法糖)"
tag: 
- 
---
# 條件簡寫（三元運算符 ternary operator）
可以簡寫[[if, switch#if if else else if]]
`()?`為判斷句 condition ，`:` 代表 else
```js
let price = (age < 18)? 50 : 100;
let price = (age < 18)? 50 : (age < 60)? 100 : 75;
```


```js
conditional ? (if condition is true) : (if condition is false)
```

#js #math #logic