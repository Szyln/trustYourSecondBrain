---
title: "DOM 需要知道的 methods, properties"
tag: 
- 
---
![](https://i.imgur.com/42G4N5a.png)
# Element Object
- 所有 html 的 element（所有標籤）都可以用這些功能（都從 element object 中繼承而來）
- 不同的 element 可能有其他特殊的功能或屬性（繼承後還有自己獨有的屬性與功能）

- innerHTML, innerText
- createElement
- appendChild()
- children, childNode
- classList
	- add()
	- remove()
	- toggle()
	- contains()
- getAttribute
- querySelector()
- querySelectorAll()
- remove()


## 透過 DOM 修改 html 內容
```javascript
// mark 標籤會作用
h1.innerHTML = "<mark>字字字</mark>";
// mark 只會被讀作文字
h1.innerText = "<mark>字字字</mark>";
```
### innerHTML
讀作程式碼
### innerText
讀作 string


## 製造 element
creatElement
## 加入 element
appendChild

## 動態修改 class
```javascript
title.classList.add("flex"); 
```
classList 也是一個 object
回傳該 html 標籤所有的 class
### classList 的功能
- add()
- remove()
- toggle()
- contains()

#### contains()
```javascript
title.classList.contains("blue");
// 判定 class 是否有包含 blue （回傳 true / false）
```

## 取得屬性
```javascript
title.getAttribute("href")
```
![](https://i.imgur.com/0nHFx1H.png)



## document 跟 element 都可以用的選擇器
從 document 繼承而來
- querySelector()
- querySelectorAll()

```javascript
// 從 document 的階層來選擇
let docPara = document.querySelectorAll("p");
// 從特定 HTML 標籤的階層做選擇
let section = document.querySelector("section");
let sectionPara = section.querySelectorAll("p");
```

## 移除標籤
像是在增減待辦事項時，想要刪掉事項就可以用這個
```javascript
title.remove();
```

## style
選取 CSS 的 style，由於 js 裡面不能用 `-` 所以要用大寫串起來，是直接寫入 **inline style**

```js
console.log(title.style);
// #1
title.style.backgroundColor = "Blue";
// #2
title.style = "background-color: blue; font-size: 20pt;"
```

#js #dom