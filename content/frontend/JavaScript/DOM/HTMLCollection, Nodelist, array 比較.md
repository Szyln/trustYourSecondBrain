# HTMLCollection, Nodelist 與 array 類似之處
## 比較
在比較新的功能出來之後，`HTMLCollection` 的侷限多，漸漸不再被使用

|DOM 功能|取得的清單|
|-|-|
|getElementByClassName|HTMLCollection|
|querySelectorAll|NodeList|

但實作上還是 array 最實用，取得 NodeList 之後常會透過 [[展開#轉成純陣列]] 的方法來使用陣列功能

|功能|array|NodeList|HTMLCollection|
|-|-|-|-|
|length, index|O|O|O|
|forEach|O|O|X|
|新增、刪除|O|X|X|


## HTMLCollection
可以透過` getElementByClassName` 取得
很像 array 但是不能執行新增刪除那些功能


## NodeList
`querySelectorAll` 取得




#js #dom