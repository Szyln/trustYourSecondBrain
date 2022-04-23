---
title: "用元件處理 CSS Styling"
tag: 
- 
---
# 用元件處理 CSS Styling
>[[Component：可重複利用、自定參數的元件]]
>[[Styling in JSX]]

- 會多次出現的類似內容，就可以做成元件
- 內容若有需要微調的需求，則設定參數供調整

## 找出類似內容
```jsx
const element = (
	<div>
		{/* 觀察有沒有可以異中求同的要素： className 有 box */}
		<div className="box box-small">small box</div>		
		<div className="box box-medium">medium box</div>
	</div>
)
```

## 拉出來做成元件
>[[Component：可重複利用、自定參數的元件#生成元件]]
```jsx
// 建立 Box 元件
function Box(props) {
	return (
		// 最一開始長這樣，沒有異中求同，只有單純元件化
		<div {...props} />
	)
}
// 改寫
const element = (
	<div>
		{/* 全部屬性都要手動寫 */}
		<Box className="box box-small">small box</Box>		
		<Box className="box box-medium">medium box</Box>
	</div>
)
```

## 不同的內容則拉出來做自訂參數
> [[string]]：可以使用 `trim()` 避免 `className` 字串沒有寫額外 `className` 的空白字串
```jsx
// 預設 className 為空字串，不然會顯示 undefined
function Box({className = '', ...rest}) {
	return (
		// 注意包在 HTML 標籤內要寫 JS 程式碼的話要用 {} 包起來
		<div className={`box ${className}`} {...rest} />
	)
}
const element = (
	<div>
		{/* class 裡共通的 box 就可以拿掉了 */}
		<Box className="box-small">small box</Box>		
		<Box className="box-medium">medium box</Box>
	</div>
)
```
>## 注意
>不要這樣寫，如果手動寫 `props` 的時候寫了 `className` 屬性會蓋過前者（只能有一個 `className`）
>```jsx
><div className="box" {...props} />
>```

## 改良：可以再改良元件的易讀性（就算不懂 CSS 也可以改元件）
### 生成
```jsx
function Box({className = '', size, ...rest}) {
	// 如果有寫入 sizeClassName 就新增一個指定的 class 名字
	const sizeClassName = size ? `box--${size}` : ''
	return (
		<div className={`box ${sizeClassName}`}, {size}, {...rest} />
	)
}
```
### 使用
```jsx
const element = (
	<div>

		<Box size="small">small box</Box>		
		<Box size="medium">medium box</Box>
	</div>

)

```

## Inline Styling 
與 className 的處理一樣
```jsx
function Box({className = '', style, ...rest}) {
	return (
		<div 
			className={`box ${className}`} 
			style={{fontStyle: 'italic', ...style}}
			{...rest} />
	)
}
```

#js/react #css 