# fieldset
`<fieldset>` 搭配 `disabled` 可以一次禁用整個區域 ^c9e148

```html
<form>
  <fieldset disabled>
    <legend>Disabled fieldset example</legend>
    <div class="mb-3">
      <label for="disabledTextInput" class="form-label">Disabled input</label>
      <input type="text" id="disabledTextInput" class="form-control" placeholder="Disabled input">
    </div>
    <div class="mb-3">
      <label for="disabledSelect" class="form-label">Disabled select menu</label>
      <select id="disabledSelect" class="form-select">
        <option>Disabled select</option>
      </select>
    </div>
    <div class="mb-3">
      <div class="form-check">
        <input class="form-check-input" type="checkbox" id="disabledFieldsetCheck" disabled>
        <label class="form-check-label" for="disabledFieldsetCheck">
          Can't check this
        </label>
      </div>
    </div>
    <button type="submit" class="btn btn-primary">Submit</button>
  </fieldset>
</form>
```

## 包含自訂按鈕需要額外……
如果有自訂的按鈕元素在 fieldset 內，則需要額外再加入
- `tabindex="-1"` ：防止用鍵盤聚焦
- `aria-disabled="disabled"` ：輔助技術傳達狀態

#html #bs/form #form