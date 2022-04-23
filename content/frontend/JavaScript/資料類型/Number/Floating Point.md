---
title: "Floating Point"
tag: 
- 
---
# Floating Point
因為電腦的二進位跟小數點的十進位換算有點複雜
可能會遇到碰上小數點無法正常運算的問題
```js
console.log(0.2 + 0.1 == 0.3); // false 
```

## 一種解決方法 toFixed(小數點第幾位)
```js
console.log((0.2 + 0.1).toFixed(1) == 0.3.toFixed(1)); // false 
```
#js #dataType #primitiveDataType