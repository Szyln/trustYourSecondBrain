#  input tag
> [[label]] 的 for 屬性內容對應 [[input]] 的 id 屬性內容，互成一組
- 選單用這個：[[select & datalist 選單]] 
```html
<label for="對應 input 的 id"></label>
<input 
	type="多種類型，限定 input 內容類型" 
	name="最重要屬性，代表會被提交，在網址上也會顯示" 
	id="（這裡需與 label for 相同）"
	placeholder="value 為空時，暫存預設輸入框內容"
	value="會被送出的值，也可以設定預設值"
	
	<!-- 
	禁止輸入的兩種屬性 
		disabled（不會傳輸資料）
		readonly（會傳輸資料）
	-->
	
	<!-- 驗證，通常用不到會自己刻 -->
	required
>
```

## 提交的內容
提交有 `name` 的資料， `value` 是傳輸的值
`type="checkbox"` 這種只能勾選的類型一定要 value
`type="text"` 可以輸入內容，就不用

## required（必填項目）
沒有符合格式要擋掉，通常會手刻取代這個

## 常見 type
```html
<input 
	type="多種類型，限定 input 內容類型" 
>
```
[input 標籤](https://developer.mozilla.org/ja/docs/Web/HTML/Element/input)
### 選擇 checkbox（任選）／radio（單選）
一個選項對應一個 label
```html
<input 
	type="checkbox"
	name="訂閱"
	
	<!-- 有勾才會送出 value -->
	value="是"
	
	<!-- 可預設勾起 -->
	checked
>
``` 

#### name 相同為同一群組
```html
<label for="性別">女
<input
	id="性別"
	name="性別選項"
	type="ratio"
	value="女"
	
	<!-- 寫在第一個就可以了 -->
	required  
>
</label>

<label for="性別">男
<input
	id="性別"
	name="性別選項"
	type="ratio"
	value="男"
>
</label>
``` 
### number
信用卡不是用這個類型
```html
<input 
	type="number"
	name="年齡"
	placeholder="請填入年齡"

	value=""
	
	<!-- 限制數字範圍，防止無效數值 -->
	min="0"
	max="150"
	
	<!-- 單位，一次增減多少 -->
	step="0.01"
>
```

### range
拉桿，number 的變形
```html
0<input 
	type="range"
	name="password"
	value=""
	
	<!-- 字串使用 length 限制 -->
	min="0"
	max="100"
	
	<!-- 單位，一次增減多少 -->
	step="0.01"
>
100
```

### password
記得要用 form method post，加密注意
show password 需要寫 JS
```html
<input 
	type="password"
	name="password"
	value=""
	
	<!-- 字串使用 length 限制 -->
	minlength="8"
	maxlength="12"
>
```



-   email
-   file
-   number
-   password



### date 不建議使用
格式、時區不一樣，通常會用套件
例如 datepicker (jQuery)
> [[vanillajs-datepicker]]
>![[vanillajs-datepicker#^e804de]]

[react-datepicker](https://github.com/Hacker0x01/react-datepicker)
#form #html 