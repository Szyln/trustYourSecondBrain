---
title: "深層拷貝、非 string 類型的資料類型轉換"
tag: 
- 
---
# 深層拷貝 (Deep Copy)
[[物件不要傳參考的時候：深層、淺層拷貝]]

深層拷貝會將物件先轉成 [[string]] 再轉回物件
賦值到 newObject 之後，與原物件就不會再具有傳參考特性(link)
```
const newObject = JSON.parse(JSON.stringify(object))
```

## [[Storage]] 內的資料使用
#### 非 [[string]] 的資料類型 [[類型轉換]]
由於 storage 裡面只會有 string ，其他的[[資料類型]]都會被轉成 string，如果想要其他的資料提出時還是維持資料原本的類型，可以用以下功能（object, array, boolean 皆可）
- [[類型轉換#JSON]]