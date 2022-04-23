---
title: "Colocating"
tag: 
- 
---
# Colocating
在 [[State Lifting]] 時，因為子層多個元件需要同時用一個 state 資訊，所以將該 state 提升到母層使用，並以 props 的方式下放到子層做使用

但遇到修改 code 時，共用的 state 不再需要共用時（只剩下一個元件要使用），就必須做 Colocating，將在母層的 state 回歸需要的子層，保持 state 離使用環境最近的原則

#js/react/hook