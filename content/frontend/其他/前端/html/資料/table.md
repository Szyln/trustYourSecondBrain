# table

![](https://i.imgur.com/uy93kDm.png)

```html
<table class="table">
	<caption>caption 為表格標題</caption>
	<!-- 對縱向 column 群組設定樣式 -->
	<colgroup>
		<col />
		<col />
		<col span="1" class="bg-secondary-light" />
		<col />
		<col span="1" class="bg-secondary-light" />
		<col />
		<col span="1" class="bg-secondary-light" />
	</colgroup>
	<thead>
		<tr>
			<th scope="col">th：每 row 都要用 tr 包起來</th>
			<th scope="col">th</th>
			<th scope="col">th，用 colgroup 上縱向樣式</th>
			<th scope="col">th</th>
			<th scope="col">th</th>
			<th scope="col">th</th>
			<th scope="col">th</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<th scope="row">th：th 有兩種<br/>row 或 col 的標題<br/>用 scope 屬性區分</th>
			<td>td</td>
			<td colspan="2" className="border border-4 border-secondary">td:用 colspan 橫向合併</td>
			<td>td</td>
			<td>td</td>
			<td rowspan="2" className="border border-4 border-secondary">td：用 rowspan 縱向合併</td>
		</tr>
		<tr>
			<th scope="row">th</th>
			<td>td</td>
			<td>td</td>
			<td>td</td>
			<td>td</td>
			<td>td</td>
		</tr>
	</tbody>
</table>
```

---

## 必要架構
- `tr`(table row)
	- `th` (table headings)
	- `td` (table data)

每 row 都有一個標題 `th`，其餘都是 `td`

## 語意架構
- `thead`
- `tbody`
- `tfoot`

用於包住不同段落的 `tr`
非必要架構

## 合併表格用屬性
```html
<th colspan="2">大標題</th>
```
可對 `th` , `td` 等使用
- `colspan`
- `rowspan`

value 為數字，代表要橫跨多少 row 或 column

## 其他 table 內可使用標籤
- [[caption 表格標題]]
- [[colgroup 表格縱向群組產生樣式]]

#html/table #css 