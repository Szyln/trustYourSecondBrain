---
title: "SCSS"
tag: 
- 
---
# SCSS 簡介
金魚腦用｜[Sass cheatsheet](https://devhints.io/sass)

  

## 介紹

### codepen 的環境下
-   使用時 css 格式要調整成 scss
-    view complied css
	-   可切換看編譯前後的 css
### sass and scss 兩種寫法
#### scss
接近原本的 css
#### sass
空格取代階層

### 編譯軟體

#### Editor 內建編譯軟體
-   使用沒有支援內建編譯的 Editor 就必須用其他軟體
-   用過兩種都很當
-   Live Sass Compiler
	-  啟動要開 watch Sass
練習 bootstrap 時卡到懷疑人生，懷疑寫錯，懷疑 bug
當到怕，換軟體，真的不要浪費時間

#### Prepos
-   學長姊老師推薦
-   但廣告很多
-  有支援手機上即時預覽
-  
#### Scout
-   開源無廣告
-   目前用起來覺得蠻好用的
-   介面有點顯眼，但可以自訂主題
-   謎因萬歲

#### gulp webpack前端任務 / 打包工具 (JS)
-   學習曲線較高

---

  

## 寫法

1. 不要忘記分號｜每行都有分號;
2. 有關係放一起｜有層級關係的親元素包住子元素選擇器

3. 縮短選擇器長度｜取代親元素 > 子元素的選擇器
4. 整理 class 脈絡｜搭配 & 寫出元件樣式

  

## 功能符號

### 自訂全域變數｜Variable $
```scss
$red: #833;  // 宣告
body { color: $red; }  // 使用
```

#### 常見變數
-   數字
-   字串 ”” or ‘’
-   字體名稱
	-   “Helvetica, Arial, sans-serif”
-   顏色
	-   primary
	-   secondary
	-   不建議用顏色分
-   boolean
-   空值：null
#### 特性
-   支援運算

### 簡化子層名稱｜Nesting &

:Pseudo class, ::Pseudo, 甚至一般 class 名稱都可以連結
```scss
a { &:hover {} }
.menu { &-item {} }
```


### darken(), lighten() 顏色調整
```scss
darken($color, 5%)
lighten($color, 5%)
```
### !default

## 一頁做一件事｜@import
```scss
@import “{（不加底線）其他子sass（不加附檔名）}”;
```
### 常見架構
-   all
	-   _variable
	-   _utils.scss // 通用類別
	-   _reset
		-   meyerweb
		-   nomalize.css
	-   _mixin
	-   layout // 共同框架
	-   module // button, form, table
	-   _main
	-   _base
		-   對基礎標籤的設定a, h1, ...
	-   其他 plugin
	-   
#### 架構分類目的
-   彙整子 sass 到 親 sass
-   不同類型的 sass 分開管理
-   子 sass 檔名需在開頭加_，編譯時才不會編出獨立的 css 檔

  

## 統整常用語法｜@mixin and @include
```scss
@mixin heading-font {
 font-family: sans-serif;
 font-weight: bold;
}

h1 {
 @include heading-font;
}
```
-   有點像 js 的 object
-   
### 常用 mixin
```scss
// 圖片取代文字
@minxin hide-text {
 test-indent: 110%;
 white-space: nowrap;
 ovwrflow: hidden;
}
```
  

  

## 統整常用 class｜@mixin and @content
```scss
// media query RWD

@mixin pad {
 @media (max-width: 768px) {
 **@content**
 }
}

.header {
 font-size: 12px;
 @include pad {
 font-size: 16px;   // @content
 }
}
```
只取選擇器本身，裡面的屬性可自填

## 註解
```scss
// scss 的註解，不會編譯出來
/* 區塊的註解，會編譯出來 */
```

 ## extend
 一個專門拿來繼承的樣式，
```scss
%forInherit {
	display: block;
}
 .a-link {
	@extend %button;
}
```
[鐵人賽 26 - 實戰心法 - 應避免的 Sass @extend](https://wcc723.github.io/css/2016/12/26/sass-extend/)
 
 ## extend 與 mixin 的差別
 輸出結果不一樣
 extend ：選擇器很多個共用一個 { 樣式 }
 mixin：一個 { 樣式 }  寫到很多個選擇器內
## function 
```scss
@function line($num: 1) {
	@return $baseLineHeight * $num;
}

.box {
	border-width: line(); // 讀取預設值 1
}
```
### 備忘
-   用順序蓋important
## 待讀
[鐵人賽 26 - 實戰心法 - 應避免的 Sass @extend](https://wcc723.github.io/css/2016/12/26/sass-extend/)
[最好的CSS方式——OOCSS+ Sass - 技术翻译 - OSCHINA 社区](https://www.oschina.net/translate/oocss-plus-sass-is-the-best-way-to-css?print)

#css #scss 