---
title: "Modal"
tag: 
- 
---
# Modal


## 運作
- 除 html, css 也需要 js 才能運作
- 啟動時無法滾動 `body` 內容
- 只能一個同時用單一 `modal`
- 點擊背景會關閉視窗：（`.modal` 上寫 `data-bs-backdrop="static"` 可取消)
- 內容過長時可滾動視窗（ `.modal>.modal-dialog`加上`.modal-dialog-scrollable`可不滾動視窗只滾動 `modal` 內文）

## 基本組合

| 屬性                 | 按鈕                                              | Modal（`.modal`）           | `.modal>.modal-dialog`     |
| -------------------- | ------------------------------------------------- | --------------------------- | -------------------------- |
| 成立 Modal 元件      | `data-bs-toggle="modal"` <br/> `data-bs-target="#id"` | `.modal`   `id="id"`        |
| 阻止點擊背景關閉視窗 |                                                   | `data-bs-backdrop="static"` |
| 內文可滾動           |                                                   |                             | `.modal-dialog-scrollable` |
| Modal 置中於視窗     |                                                   |                             | `.modal-dialog-centered`   |


- 按鈕：
- Modal：`.modal`
  - `.modal-dialog`：modal 內文
    - `.modal-content`
      - `modal-header`
      - `modal-body`：下層使用 `container-fluid` 可以使用網格系統
      - `modal-footer`

- `modal-title` `h*`
- 
```html
<!-- 啟動 modal 按鈕 -->
<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal">
  Launch demo modal
</button>

<!-- Modal -->
<div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="exampleModalLabel">Modal title</h5>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">
        ...
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary">Save changes</button>
      </div>
    </div>
  </div>
</div>
```

```html
<button type="button" class="btn btn-primary" 
				data-bs-toggle="modal"
				data-bs-target="#exampleModal" 
				data-bs-whatever="@mdo"
>
	Open modal for @mdo
</button>
<button type="button" class="btn btn-primary" 
				data-bs-toggle="modal" 
				data-bs-target="#exampleModal" 
				data-bs-whatever="@fat"
>
	Open modal for @fat
</button>
<button type="button" class="btn btn-primary" 
				data-bs-toggle="modal" 
				data-bs-target="#exampleModal" 
				data-bs-whatever="@getbootstrap"
>
	Open modal for @getbootstrap
</button>

<div class="modal fade" 
		 id="exampleModal" 
		 tabindex="-1" 
		 aria-labelledby="exampleModalLabel" 
		 aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" 
        id="exampleModalLabel">New message</h5>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">
        <form>
          <div class="mb-3">
            <label for="recipient-name" class="col-form-label">Recipient:</label>
            <input type="text" class="form-control" id="recipient-name">
          </div>
          <div class="mb-3">
            <label for="message-text" class="col-form-label">Message:</label>
            <textarea class="form-control" id="message-text"></textarea>
          </div>
        </form>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary">Send message</button>
      </div>
    </div>
  </div>
</div>
```


#css/scss #bs/component/modal