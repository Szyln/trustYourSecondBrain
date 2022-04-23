# 原始資料類型使用 Prototype Inheritance 的功能
## Coercion
[[原始資料類型 Primitive Data Types]]沒有自己的 methods，但因為 JS 有 Coercion 的特性，就算不是物件，也可以使用物件繼承來的功能。 
## 示範
[[原始資料類型 Primitive Data Types#Primitive Coercion]]

不推薦：可以透過 [[Constructor]] 的方法去做[[原始資料類型 Primitive Data Types#Primitive Coercion#不正常的作法]]物件類型的 string
推薦：利用 Coercion 的特性，讓原始資料類型讀取 prototype

#js #advanceJs #object #oop #dataType #primitiveDataType 