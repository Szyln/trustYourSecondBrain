---
title: "DOM 新舊對比"
tag: 
- 
---
# 功能新舊對比
DOM 的 properties 有很多個，其中有些比較雷同的項目，其中有些已經漸漸不再使用了

|新|舊|
|-|-|
|childNodes|children|
|NodeList|HTMLCollection|
|querySelectorAll|getElementByClassName|


# children 或是 childNode
childNodes 會 return **NodeList**
內容會很多，可以用 children 就好

#js #dom