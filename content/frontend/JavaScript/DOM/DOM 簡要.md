# DOM｜Document Object Model
 [DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)
-   類似 object

## 節點 node｜在 document 裡的物件們
-   element node
-   text node
-   attribute node

## 選取｜節點、內容、屬性
### 選取節點｜單一選取、群體選取
-   選起來存在一個 const 裡面
-   第一個符合的節點｜document.querySelector(’該 CSS 選擇器’)

#### 符合的全部節點｜document.querySelectorAll(’該 CSS 選擇器’)
會是一個 node list（一個 array，存取各個節點可使用 array 的技巧）

### 選取內容｜內容、文字
-   有可能修正就存在 let 變數裡
-   內部內容｜{某節點}.innerHTML
-   內部文字｜{某節點}.textContent

### 選取屬性｜{某節點}.getAttribute(’{欲取得屬性}’)

## 新增與修改｜內容、文字、屬性
### 標籤與內容｜{某節點}.innerHTML = {欲修改或新增的內容};
```js
main.innerHTML = `<a href="${link}" class="header">超連結</a>;`
```
-   可搭配 Template Literals （`字串 ${變數}`） 來寫
-   若該節點本來裡面就有內容，則會被清除

### 標籤內文字｜{某節點}.textContent = {欲修改或新增的內容};
### 標籤的屬性｜{某節點}.setAttribute({屬性名稱}, {屬性內容})
```js
document.querySelector(’a’).setAttribute(’href’, ’#’ );
```
## 反查節點名｜{ 某 selector }.nodeName
##  querySelector
-   querySelector｜一個節點
-   querySelectorAll｜一個 array
```js
// 有地蓋房子

  

// 在 document 上找地(section) 
const section = document.querySelector('section');
  

	 // 在 document 上生材料
	 const para = document.createElement('p');
	 para.textContent = 'hello world';

	 // 把生好的材料放上地(section)
	 section.appendChild(para);
 
```
## createElement()
```js
// 沒地蓋房子


// 先在 document 上生地
const section = document.createElement('section');

  

// 把地放上 document 上的 body
**document****.****body****.**appendChild(section);

  
// 在 document 上生材料
const para = document.createElement('p');
para.textContent = 'hello world';

  

// 把生好的材料放上地(section，不用從document開始寫)
**section****.**appendChild(para);
```


## 範圍取值
-   用 class 取比較不會撞到

## 自訂標籤屬性｜data-{自訂名稱}=”自訂內容”

  
#js #dom
