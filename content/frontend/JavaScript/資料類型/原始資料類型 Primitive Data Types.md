# 原始[[資料類型]] primitive data types
**不是物件**，沒有自己的屬性與功能
擁有自己的值，不是參考

- [[Number]]
- [[string]]
- [[Boolean]]: falsy value
- symbol

## [[物件傳參考#傳值 Call By Value]]
不會改變原始值（進階的時候才會理解 primitive data types 為什麼不會被改變）

```js
let n1 = 100;
let n2 = n1;

n1 = 1;
console.log(n1, n2); // 傳值的特性 log 1 100
```

## Primitive Coercion

JS 可以強迫把原始資料類型改成 object 來使用（比如說使用 `.length`功能）
### 不正常的作法
使用 new String() 的方式生成 object，再去讀取 object 的功能但會佔記憶體，吃效能
[[Prototype Inheritance#Coercion 強迫]] 的特性，其實不需要這樣處理
```js
let str = new String("Hello");
cosole.log(type str); // log object
```
### 正常的作法
JS 直接讀取就可以了
```js
let str = "Hello";
cosole.log(type str); // log string
cosole.log(str.toLowerCase()); // log hello

```
#js #dataType #primitiveDataType 