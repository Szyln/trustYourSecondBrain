---
title: "select & datalist 選單"
tag: 
- 
---
#  select & datalist
[select](https://developer.mozilla.org/ja/docs/Web/HTML/Element/select)

兩者差別在 `select` 只能選取 `option` 內容
`datalist` 可自填

## select
value 要記得寫
```html
<select name="choice" required>

	 <!-- 空白的選項是不能送出的 -->
	 <option></option>

	 <!-- 也可以自訂預設選項 -->
	 <option value="first" selected>第一個選項</option>
	 
	 <option value="second">第二個選項</option>
	 <option value="third">第三個選項</option>
</select>
```


## datalist
為一個 input 的候選清單，實際送出的值會是 value ，不一定是字面上的內容
![](https://i.imgur.com/mADrmTJ.png)
![](https://i.imgur.com/klYQhsr.png)
資料會是台中市而非台中

```html
<input 
	type="text" 
	name="area" 
	<!-- 需特別註明對應 datalist -->
	list="areaList"
>
<datalist 
	<!-- 需特別註明對應 input -->
	id="areaList"
>
	 <option></option>
	 <option value="first">第一個選項</option>
	 <option value="second">第二個選項</option>
	 <option value="third">第三個選項</option>
</datalist>
```

### select 不要修改
- [ ] 點選的地方
- [x] 下拉選單
- [x] 手機版的樣式