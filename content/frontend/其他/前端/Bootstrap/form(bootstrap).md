# form (bootstrap)
- `form`
	- `div` ：每個 input 都用 div 包住，設定 `mb-*`
		- `label.form-label`
			- `for` 對應 `input` 的 `id`
			- `aria-describedby="註解"`
		- `input.form-control`
			- 屬性：type, id（對應 `label` 的 `for` ）
		- `div.form-text#註解` （不想用 block 元素的話可以用 `span`, `small`, `p` 都可 ）
			- id 對應 label 的 `aria-describedby`

## input(bootstrap)
- `class="form-control"`
	- `form-control-尺寸` （sm, lg） 
- type
- id(對應 label for)
- disabled
- readonly：搭配 `.form-control-plaintext` 可使 input 取消樣式（外框），僅保留文字

![[fieldset(form)#^c9e148]]

### 親和性
可以使用的（推薦 -> 還可以）
1. label
2. aria-labelledby
3. title
4. aria-label
5. placeholder

# select & datalist(bs)
[[select & datalist 選單]]
- `select.form-select`
	- `form-select-尺寸` (sm, lg)

# checks & radios
 - `div.form-check-inline` ：input + label 成 inline 狀態
- `div.form-check`
	- `input.form-check-input` `type="checkbox"`
	- `label.form-check-label`

- `div.form-check`
	- `input.form-check-input` `type="radio"`
	- `label.form-check-label`

# switch
- `div.form-check.form-switch`
	- `input.form-check-input` `type="checkbox" role="switch"`
	- `label.form-check-label`


#bs/form #form