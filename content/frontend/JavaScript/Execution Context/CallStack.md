# CallStack
[loupe 實際 CallStack 運算的樣子](http://latentflip.com/loupe/?code=ZnVuY3Rpb24gZjEoKSB7CiAgY29uc29sZS5sb2coJ1RoaXMgaXMgZjEnKQoKICBmMigpCgogIGZ1bmN0aW9uIGYyKCkgewogICAgY29uc29sZS5sb2coJ1RoaXMgaXMgZjInKQoKICAgIGYzKCkKCiAgICBmdW5jdGlvbiBmMygpIHsKICAgICAgY29uc29sZS5sb2coJ1RoaXMgaXMgZjMnKQoKICAgICAgY29uc29sZS5sb2coJ2YzIGRvbmUnKQogICAgfQoKICAgIGNvbnNvbGUubG9nKCdmMiBkb25lJykKICB9CgogIGNvbnNvbGUubG9nKCdmMSBkb25lJykKfQoKZjEoKQ%3D%3D!!!PGJ1dHRvbj5DbGljayBtZSE8L2J1dHRvbj4%3D)

[[Execution Context]]中，到了 [[Execution Phase]] 會按照 CallStack 的原則開始跑

## 解釋
### Call
指 Calling funtions ，執行 funciton 時會產生 callstack
### Stack
> Stack 是一種資料結構（資料結構跟演算法相關）

![](https://i.imgur.com/hrYe0z6.png)

一個像容器，先放進去的東西會最後拿出來

#### LIFO
Last-In-First-Out 後進先出

## 目的
JS 是單一線性(single-[[thread]])程式語言，一次指能做一件事，所以我們需要一個方法來追蹤 [[Execution Context]]，就是 CallStack

## 實際步驟
```js
function f1() {
	console.log("f1");			// 1. log f1
	
	f2()

	function f2() {
		console.log("f2");		// 2. log f2
		
		f3();			
		
		function f3() {			
			console.log("f3");	// 3. log f3
		}						// 4. f3 執行完畢，清除 f3
	}							// 5. f2 執行完畢，清除 f2
								
	console.log("done");		// 6. log done 
}								// 7. f1 執行完畢，清除 f1

f1()
```

#js #window #executionContext 