## 更新既有表格內容
```sql
SELECT * FROM employees;

-- 更新符合條件（WHERE）的內容，都改成（SET）

UPDATE employees SET employeeID = 107 WHERE employeeID = 108;

-- 同時更新好幾個符合條件的也可以

UPDATE employees SET salary = 1700 WHERE salary = 1500;

```

#sql #database 