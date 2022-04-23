## flex 碰上 overflow
overflow 之外的項目無法 scroll 到
[Can't scroll to top of flex item that is overflowing container](https://stackoverflow.com/questions/33454533/cant-scroll-to-top-of-flex-item-that-is-overflowing-container)
放 jusitify-content-center 在窄螢幕會有問題
scroll 沒辦法滾到第一項目
查到兩種作法
1. 使用 margin: auto 做推擠
2. justify-content: safe center （*目前看起來只有 firefox 有用）

## scroll
### 隱藏 scrollbar 但要可以滾
ul 用 pb-2 將 scrollbar 推下去，

再用負的 mb-n2

將 pb-2 抵消藏起來