---
title: "mySQL"
tag: 
- 
---
# mySQL
- [[SQL]] 的其中一種 [[DBMS(RDBMS)]]
- [[mySQL 環境建置]]

## [[Database 數據庫#C R U D]]

 - create：[[SQL create 製作表格]]
 - read：[[SQL read 檢視表格內容]]
 - update：[[SQL update 更新既有表格內容]]
 - delete：[[SQL delete 刪除既有表格內容]]


## 構成
- [[SQL 的 Keys]]
- [[Data Types]]

## query(查詢)
[[SQL read 檢視表格內容]] 可以檢視整個表格內容
使用 query 可以建立篩選功能
```sql
-- 所有內容
SELECT * FROM employees;
```
### 顯示特定欄位
```sql
-- 只檢視特定 column
SELECT employeeID, employeeName FROM employees;
```
### 排序
```sql
-- 按照指定 column 遞減
SELECT * FROM employees ORDER BY age DESC;

-- 指定特定行遞減後，再指定另一行遞增
-- OREDER BY 的預設就是遞增不用再多寫
SELECT * FROM employees 
ORDER BY age DESC, salary;
```
### 限制資料數量
```sql
-- 只回傳符合條件的前幾項
SELECT * FROM employees 
ORDER BY age DESC, salary;
LIMIT 3;	-- 只回傳三項
```
### 顯示符合條件的內容
```sql
-- WHERE
SELECT * FROM employees 
WHERE department = 1;
```

#### 邏輯
做判斷條件的時候可以使用的一些邏輯符號
```sql
-- AND
SELECT * FROM employees 
WHERE department = 1 AND salary >= 2000;

-- OR
WHERE department = 1 OR salary >= 2000;

-- not
WHERE department != 1;
```



#database #sql