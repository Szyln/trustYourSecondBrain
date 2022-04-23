---
title: "Global Execution Context"
tag: 
- 
---
# Global Execution Context 全域執行環境
為 [[Execution Phase]] 的其中一種

## Creation Phase
- 生成 window object
- 生成 [[Scope]] （依照 [[Closure(Scope Chaining)]] 閉包原則）
- 生成 this （指向 window）
- [[Hoisting]]
## Execution Phase
開始實際一行一行跑程式 (callstack)

#js #window #executionContext