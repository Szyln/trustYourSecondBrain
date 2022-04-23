# flexbox
> [Animated Flexbox Playground](https://codepen.io/osublake/full/dMLQJr)
-   [[flex-wrap]]: wrap-reverse;
-   flex:1 代表 flex-grow
-   ul > li > a > 字＋圖
```html
    <ul class="d-flex">
      <li>
        <a>AAAA</a>
      </li>
    </ul>
```
-   ul: d-flex, width
-   li: flex-1
-   a: d-block, padding（一致）, 連結的互動設定
-   img: d-block, m-auto

## 外容器
[[d-flex]]

| display         | flex                                   |
| --------------- | -------------------------------------- |
| flex-flow       | `<flex-direction>` `<flex-wrap>` 縮寫  |
| flex-direction  | 流向                                   |
| flex-wrap       | 出血後是否換行（影響交錯軸）           |
| justify-content | 分配各內容的主軸空間                   |
| align-items     | 內容在交錯軸的定位（不影響主軸）       |
| align-content   | flex-wrap 設定後有效，分配交錯軸的空間 |

### 內容
# flex
-  `flex-grow` 
-  `flex-shrink`
-  `flex-basis`
# align-self
# order


## flex 中 flex
如果需要多層次的內容，在內層再下 `flex`

## max-width
容器下 max-width
內容物的寬度下 %

---

![](https://i.imgur.com/DtbIkHM.png)

#css