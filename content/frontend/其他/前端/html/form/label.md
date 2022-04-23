# label tag
> [[label]] 的 for 屬性內容對應 [[input]] 的 id 屬性內容，互成一組
- input 的標籤（不強制使用）
- 點擊 `label` 就會反白 `input`
- 不要把 placeholder 當 label 
- 若有 p tag 不要包在裡面

## 架構
```html
<!-- 用 div 包 -->
<div>
	<label for="myName">姓名</label>
	<input type="text" id="myName">
</div>
```
```html
<!-- 用 label 包 -->
<!-- 用 label 包起來的 input 因為關係明顯， for, id 非必要-->
<label for="myName">姓名
	<input type="text" id="myName">
</label>
```


#form #html 