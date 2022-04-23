---
title: "background"
tag: 
- 
---
# background 屬性
>[mdn](https://developer.mozilla.org/ja/docs/Web/CSS/background)



## 概括寫法

沒有順序差別，只有 [[background-position]] / [[background-size]] 要注意要寫在一起
可用 0-1 次：

-   [[background-attachment]]：fixed, local, scroll
-   image：url()
-   [[background-position]] / [[background-size]] ：圖片比範圍小的時候好用的定位
-   backgroud-repeat: repeat, space, round, no-repeat, repeat-x, repeat-y

只寫一個代表兩個都一樣，寫兩個的話第一個是 origin，第二個是 clip
- `<origin>`：padding-box, border-box (左上角起始座標)
- [[background-clip]]：padding-box, border-box （整個圖片的座標）
	
## background-size 設定
![[object-fit#^1ffb45]]


## 

[How To - Aspect Ratio / Height Equal to Width](https://www.w3schools.com/howto/howto_css_aspect_ratio.asp)

[Can I use... Support tables for HTML5, CSS3, etc](https://caniuse.com/mdn-css_properties_aspect-ratio)

  
	
#css/background 