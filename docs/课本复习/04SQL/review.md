## 简答题

所谓聚集索引 是指索引次序与表中元组的物理次序一致的索引。



## 综合题

```sql
-- 基本的句子得记住怎么写
INSERT INTO table (atrribute1,atrribute2)
VALUES (value1,value2);

DELETE FROM table
WHERE condition;

UPDATE table
SET atrribute = ""
WHERE condition;

SELECT atrribute1,atrribute2 AS what
FROM table1,table2
WHERE condition1
GROUP BY table1.atrribute1
HAVING condition2;
```

### 增

```sql
INSERT   INTO <表名> [(<属性列1>[,<属性列2 >…)]
VALUES (<常量1> [，<常量2>] … )
```

### 删

```sql
DELETE  FROM  <表名>
[WHERE <条件>]
```

### 改

```sql
UPDATE <表名> 
  SET 列名1=<表达式1>[,列名2=<表达式2>]
  [WHERE <条件表达式>]
```

### 查

```sql
SELECT [ALL|DISTINCT] <目标列表达式> [，<目标列表达式>] …
FROM <表名或视图名>[， <表名或视图名> ] …
[ WHERE <条件表达式> ]
[ GROUP BY <列名1> [ HAVING <条件表达式> ] ]
[ ORDER BY <列名2> [ ASC|DESC ] ]
```

### 触发器

```sql
CREATE TRIGGER <触发器名>  
{ BEFORE | AFTER} <触发事件> ON <表名>
FOR EACH  {ROW | STATEMENT}
BEGIN
	DECLARE tmp_value1 INT; -- 声明的临时变量
	...
	-- 赋值
	SELECT COUNT(*) INTO @tmp_value2 -- 不用声明的临时变量
	FROM table
	WHERE condition;
	...
	-- 触发
	IF <触发条件> THEN
		-- 比如报错
		SIGNAL SQLSTATE '45000' 
    	SET MESSAGE_TEXT = '报错';
	END IF;
END;
```

