# Fetch
- 利用 fetch 可以使用 JS 來連接別人的 [[API]]
- 是一種 [[Promise]]


## 可以直接使用的 API
用 [JokeAPI](https://sv443.net/jokeapi/v2/#info) 做示範
### [[async, await, try, catch]] 來寫
單純取得之後他不會是一個 json 檔
```js
async function getJoke() {
	// 取得 endpoint
	let data = await fetch("https://v2.jokeapi.dev/joke/Any");
	console.log(data);
}

getJoke();		// 這不會是一個 json
```

> ### [[Promise]] 來寫
> fetch 也是一種 [[Promise]] 所以也可以串 then, catch
> ```js
> function getJoke() {
> 	// 取得 endpoint
> 	fetch("https://v2.jokeapi.dev/joke/Any")
> 		.then((d) => {
> 			console.log(d);
> 		}).catch((e) => {
> 			console.log(e);
> 		});
> }
> 
> getJoke();
> ```

### 調整格式
```js
async function getJoke() {
	// 取得 endpoint
	let data = await fetch("https://v2.jokeapi.dev/joke/Any");
	let parsedData = await data.json();
	console.log(parsedData);
}

getJoke();
```

## 需要有 Authorization Key 才能使用的 API
[OpenWeather](https://openweathermap.org/)(需要註冊，才會獲得金鑰)
[WeatherAPI Doc](https://openweathermap.org/api)

### 如何使用
讀 api 文件的時候會看到這種內容，這是一個 [[endpoint]]
```js
api.openweathermap.org/data/2.5/weather?q={city name}&appid={API key}
```

#### app.js
[[async, await, try, catch]]
```js
let key = 'weather給你的金鑰';
let cityname = 'taipei';
// 將 endpoint 貼過來，並且讓他符合樣板字面值
let url = `api.openweathermap.org/data/2.5/weather?q=${city name}&appid=${key}`

async function getWeather() {
	let data = await fetch(url);
	let dataParsed = await data.json();
	console.log(dataParsed);
}

getWeather();
```
>[[Template literals (Template strings)]]

## 搭配後端來寫
[[Node to API]]
#js #async #api #promise