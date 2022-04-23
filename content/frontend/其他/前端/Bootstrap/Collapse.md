# Collapse

| 作用               | 按鈕                                            | 展開內容                                        |
| ------------------ | ----------------------------------------------- | ----------------------------------------------- |
| 添加元件           | `data-bs-toggle="collapse"`                     | `class="collapse"`                              |
| 指定展開誰         | `href="#展開 id" role="button"`                 | `id="展開id"`                                   |
| 一對多控制         | `href=".multi-collapse"  role="button"`         | `class="multi-collapse"`(對應多個展開內容)      |
| 親和性，初始狀態   | `aria-expanded="boolean"`                       | true: `.collapse.show` <br/> false: `.collapse` |
| 親和性，說明展開誰 | `aria-controls="將展開內容 id(有多個就寫多個)"` | `id="展開id"`                                   |

## 結構
### 按鈕
使用 `<button>` 或 `<a>`

#### 必填屬性
- `data-bs-toggle="collapse"`
  
- 指定展開誰（擇一）：
	- （優） `href="#將展開內容 id" role="button"`
	- `data-bs-target="#將展開內容 id"` 

- 親和性
   - `aria-expanded="boolean` ：初始狀態 true（打開）、false（收合）
   - `aria-controls="將展開內容 id(不加 #)"`：對應控制的展開內容 id，可寫多個

### 將展開的內容
預設狀態為 `height: 0` 來隱藏

#### 必填屬性
- `class="collapse"`
- `id="將展開內容 id"`

#### 其他屬性
- `.collapse-horizontal`：改成預設 `width: 0`
- `.collapse.show`：改成初始狀態為展開




#bs/component/collapse