# async, await, try, catch
[[Promise#改寫 Callback Hell]] 還可以再改寫
## async, await
async 搭配 await 可以寫出要等到結果之後再存到變數裡的 [[Async（目錄）]] code（`.then()` 的部份）
```js
// getData 的那段可以放入 function 內
// 這個 function 因為跟非同步有關，所以要使用 async
async function showMovie() {
	const obj = await getData('Wilson');	// 得到 getData 資料之後才會存進去 obj
	const movie = await getMovies(obj.age);	// 同上
	console.log(movie.text);
}

showMovie();
```
## try, catch
再進一步搭配 try, catch 的話就可以寫出 `.catch()` 的部份了
```js
// getData 的那段可以放入 function 內
// 這個 function 因為跟非同步有關，所以要使用 async
async function showMovie() {
	try {
		const obj = await getData('Wilson');	// 得到 getData 資料之後才會存進去 obj
		const movie = await getMovies(obj.age);	// 同上
		console.log(movie.text);
	} catch(e) {
		console.log(e)
	}

}

showMovie();
```

#js #ajax #async #promise