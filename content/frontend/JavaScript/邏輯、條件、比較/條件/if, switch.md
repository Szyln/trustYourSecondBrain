# 條件語句｜if, switch
## 程式的運算思維
-   流程圖：[Whimsical](https://whimsical.com/)
## if, if else, else if
若要判斷「是否為 NaN」
```js
if(x == NaN) {}  // 怎麼樣都是 false
if(isNaN(x)) {}	 // isNaN()
```
只有 true / false 判斷，可以不用寫條件語句

```js
if(x) {
  console.log('truthy');
} else {
  cosole.log('falsy');		
} 
```
### [[條件簡寫 ternary operator(語法糖)]]

## 更多的條件｜switch 語句
```js
switch (option) {
	 case 1:
		 console.log("You selected option 1.");
		 break;
	 case 2:
		 console.log("You selected option 2.");
		 break;
	 case 3:
		 console.log("You selected option 3.");
		 break;

	 default:
		 ...;
}
```

## 判斷停止條件

-   if｜一旦符合即停止
-   switch｜碰到 break 即停止
#js #math #logic