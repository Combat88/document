好的,以下是 SQL 中常见的条件函数:

1. **CASE**
   - 语法: `CASE WHEN condition1 THEN result1 WHEN condition2 THEN result2 ... ELSE result_else END`
   - 功能: 根据一系列条件返回不同的值。
   - 示例: `SELECT name, CASE WHEN age < 18 THEN 'Minor' WHEN age >= 18 AND age < 65 THEN 'Adult' ELSE 'Senior' END AS age_group FROM employees;`

2. **IF(expr1, expr2, expr3)**
   - 功能: 如果表达式 expr1 为 TRUE,则返回 expr2,否则返回 expr3。
   - 示例: `SELECT name, IF(age < 18, 'Minor', 'Adult') AS age_group FROM employees;`

3. **IFNULL(expr1, expr2)** 
   - 功能: 如果 expr1 为 NULL,则返回 expr2,否则返回 expr1。
   - 示例: `SELECT name, IFNULL(department, 'Unknown') AS department FROM employees;`

4. **COALESCE(expr1, expr2, ...)** 
   - 功能: 返回参数列表中第一个非 NULL 值。
   - 示例: `SELECT name, COALESCE(department, division, 'Unknown') AS department FROM employees;`

5. **NULLIF(expr1, expr2)**
   - 功能: 如果 expr1 等于 expr2,则返回 NULL,否则返回 expr1。
   - 示例: `SELECT name, NULLIF(salary, 0) AS salary FROM employees;`

6. **LEAST(expr1, expr2, ...)** 
   - 功能: 返回参数列表中的最小值。
   - 示例: `SELECT LEAST(10, 20, 5, 15) FROM dual;` 

7. **GREATEST(expr1, expr2, ...)**
   - 功能: 返回参数列表中的最大值。
   - 示例: `SELECT GREATEST(10, 20, 5, 15) FROM dual;`

