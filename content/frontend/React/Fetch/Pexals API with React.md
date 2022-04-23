---
title: "Pexals API with React"
tag: 
- 
---
# Pexals API with React
>本篇使用 [Pexels](https://www.pexels.com/zh-tw/api/documentation/?) API 做例子，需註冊
>- [精選相片 API](https://www.pexels.com/zh-tw/api/documentation/?#photos-curated)
>- [搜尋相片 API](https://www.pexels.com/zh-tw/api/documentation/?#photos-search)
>[[Fetch]]

- `<main.jsx>` ：[[ReactDOM：渲染]]
	- `<BrowserRouter>` ：[[react-router-dom]]
		- `<App />` ：包含共同區塊的完整頁面
			- `<Nav />` ：[[react-router-dom#Link]]，提供連結
			- `<Routes>` ：[[react-router-dom]]，回應連結請求
				- `<About />` 
				- `<Homepage />` ： API 處理，金鑰、lift (input, data（）)，searchClick event 設定、一開啟頁面就先執行一次 searchClick 事件（useEffect）
					- `<Search searchClick={searchClick} />` ：
					- `<Result data={data} setData={setData} />` ：map `<Picture />`
						- `<Picture data={item} />` ：item 是 map 出來的個別 data，將個別 data 做處理、顯示

## Homepage
>[[API]] > [[endpoint]]

>[[useState 預設值為 null 的問題]]
```jsx
const Homepage = () => {
	// [[useState 預設值為 null 的問題]]
	let [data, setData] = useState(null)
	// Search lift 上來的，
	let [input, setInput] = useState('')

	const auth = '金鑰'
	const initialPhotoURL = '<精選照片 endpoint>'
	// lift
	const searchPhotoURL = `<搜尋相片 endpoint，path 要依照 input （搜尋結果）state>`
	// 傳下去給 Search 用
	const searchClick = async () => {
		// fetch 要不要做成一個 function
		const dataFetch = await fetch(initialPhotoURL, {
			method: 'GET',
			headers: {
				Accept: 'application/json',
				Authorization: auth,
			},
		})
				
		let parsedData = await dataFetch.json
		setData(parsedData.photos)
	}
}
```

>[[useEffect Hook]]