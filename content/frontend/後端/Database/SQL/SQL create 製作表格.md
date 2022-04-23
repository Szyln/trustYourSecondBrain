# 製作表格
```sql
create table employee(				-- 生成表單
	-- Constraints：自動遞增
	employeeID int PRIMARY key AUTO_INCREMENT,
	-- Constraints：不可為 null
	employeeName varchar(25) NOT NULL,
	age int,
	-- Constraints：預設值
	salary int DEAFAULT 1500,
	supervisor int,
	department int
);
```
```sql
-- 可以使用的功能
DESCRIBE employee;		-- 檢視屬性
```

> [[Constraints]]：將表格內容限定做規範

## 新增項目
```sql

-- 每欄照順序填入
INSERT INTO employees VALUES(100, "John", 35, 3500, null, 1);

-- 指定欄位填入
INSERT INTO employees(employeeName, age, salary, supervisor, department) VALUES("Mike", 40, 2000, 100, 1);
```

#sql #database #crud