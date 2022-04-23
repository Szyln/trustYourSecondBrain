# Creation Phase
在 [[Execution Phase]] 之前，後台處理的部份

## [[Global Execution Context]]
- 生成 window object
- 生成 [[Scope]] （依照 [[Closure(Scope Chaining)]] 閉包原則）
- 生成 [[this]] （指向 window）
- [[Hoisting]]

## Function Execution Context
- 不是 [[Global Execution Context]] 所以不會生成 window object
- this 生成，但[[4.箭頭函式 arrow function]] 不會

#js #window #executionContext