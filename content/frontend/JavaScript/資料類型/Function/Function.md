# 函數｜function
一種物件
```js
// function declaration
function 名稱(parameter) {
 功能(parameter);
}

// invoke(執行)
名稱(argument);
```
  


## return 或是 console.log
-   fuction 執行之後，若要將執行後的結果儲存於變數中，要用 `return`
-   單純顯示可直接用 `console.log`，除 bug 好用

## 判斷終止｜return 或 }
### return｜一旦碰到第一個 return 就會跳出整個 function
也可以 
```js
function fun(x) {
	return;
}
```
不回傳東西當做終止 function 用

### }｜沒有碰到 return 就會執行到 function 的結尾 }

## [[函數表達式 function expression]]
## 原生 function
### alert
```js
alert('你好');
```
#### prompt
彈出式視窗輸入框
```js
prompt('請輸入年齡');
```
#js #function