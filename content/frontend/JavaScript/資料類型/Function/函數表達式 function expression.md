---
title: "函數表達式 function expression"
tag: 
- 
---
# 函數表達式 function expression 
將函數儲存進一個變數中
因牽涉給變數賦值，故不會 hoisting

## 給變數賦予……

-   匿名函數｜let funExpressionName = function(parameter) { 功能 }
-   有名稱的函數｜ let funExpressionName = function fnA(parameter) { 功能 }

## 執行……
-   返回函數結構｜執行 funExpressionName
-   執行該函數｜執行 funExpressionName({ 要給 argument })

##  函數當參數｜callback fuction
-   function fnB(callbackFunc) { callbackFunc(預設要給fnA的參數) }
-   函數表達式 fnA（一個被賦與匿名函數的變數）當 fnB 的參數，讓 fnB 可以調用 fnA

## 內嵌函數表達式｜inline function expression
-   fnC(callbackFunc, value)
-   可以多一個 parameter，來指定給 callback function 的 argument
-   也可以直接少掉將 callbackFunc 在之前建立函數表達式的步驟，直接在 fnC 的 parameter 裡定義 function
#js #function