---
title: "使用 Routing for pattern 顯示特定數據庫物件"
tag: 
- 
---
# 使用 Routing for pattern 顯示特定數據庫物件
>[[Routing for pattern 回應有規律的網址]]
>[[Find(Read)]]
```js
// 不是完整的版本，catch 還要調整（看下一段）
app.get('student/:id', async (req, res) => {
	let { id } = req.params;
	try {
		let data = await Student.findOne({ id });
		res.render('studentPage.ejs', { data })
	} catch(e) {
		// 這個不會正常顯示
		res.send('該 ID 尚未被登錄');
		console.log(e);
	}
})
```
## 修正
這邊的 [[Promise]] 並不是反應 findOne 有沒有成功抓到數據
而是反應有沒有被「執行」，如果有被執行，但沒有內容，就會顯示 null，而不是顯示 catch 的內容
```
// 沒有跳出預期的「該 ID 尚未被登錄」
Cannot read property 'name' of null
```
>[[falsy value]]

```js
app.get('student/:id', async (req, res) => {
	let { id } = req.params;
	try {
		let data = await Student.findOne({ id });
		if( data !== null) {
			res.render('studentPage.ejs', { data });
		} else {
			res.send('該 ID 尚未被登錄');
		}
	} catch(e) {
		res.send('資料取得失敗');
		console.log(e);
	}
})
```
#js #npm #node #expressJs #mongoose #database #form #ejs #backEnd #routing 