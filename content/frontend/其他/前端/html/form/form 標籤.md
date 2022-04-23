## form 標籤
```html
<form
	action="資料傳送的目的地（到後端）" 
	method="預設GET（公開），POST（非公開）"
>
</form>
```
- 與後端（[[Database 數據庫]]）相關的標籤
- 需要傳送的資料都要寫在這個標籤裡，不然不會傳輸

- action: 傳輸目的地，[[Database 數據庫]]、API 位置
- method: 執行的請求動作（[[HTTP request]] 中 HTML 可以執行的有：GET, POST）
	- GET：公開，會顯示在網址（[[Query]]）
	- POST：不會公開，需要安全性的資料要選這個



#html #form #request 