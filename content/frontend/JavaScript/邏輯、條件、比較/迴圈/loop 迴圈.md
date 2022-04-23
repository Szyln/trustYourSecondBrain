## 循環 loop｜while, for, for in, for of

### while
```js
var start = 0; // 何時開始
while (start < 10) { // 何時停止，不要在沒寫完前運行，瀏覽器會當掉
 console.log(start);
 start = start + 2; // 如何進入下一個項目
}
```
### [[for]]
### 在循環中循環｜Nesting Loop
```js
for (var x = 0; x < 5; x = x + 1) {
 for (var y = 0; y < 3; y = y + 1) {
 console.log(x + "," + y);
 }
}
```
  
  ## break and continue
  ### continue
 ```js
 for (let i = -; i<= 10; i++) {
 	if(i==5) {
		continue;  // 跳過這次的迴圈，直接進到下一次
	}
	console.log(i);  // i == 5 的這次迴圈，這裡會被跳掉不執行
 }
 ```
 
   ### break
 ```js
 for (let i = -; i<= 10; i++) {
 	if(i==5) {
		break;  // 跳過之後的所有迴圈，直接停止
	}
	console.log(i);  // 只執行到 i == 5 之前， i == 5 就停止
 }
 ```
 
 #js #loop