以下是 SQL 中常见的所有聚合函数,包括功能描述和示例:

1. **COUNT(expr)** 
   - 功能: 返回指定列中非 NULL 值的行数。
   - 示例: `SELECT COUNT(age) FROM employees;`

2. **COUNT(*)**
   - 功能: 返回表中的行数,包括 NULL 值。
   - 示例: `SELECT COUNT(*) FROM employees;`

3. **SUM(expr)** 
   - 功能: 返回指定列的所有值之和。
   - 示例: `SELECT SUM(salary) FROM employees;`

4. **AVG(expr)**
   - 功能: 返回指定列的平均值。
   - 示例: `SELECT AVG(salary) FROM employees;`

5. **MAX(expr)**
   - 功能: 返回指定列的最大值。
   - 示例: `SELECT MAX(salary) FROM employees;`

6. **MIN(expr)**
   - 功能: 返回指定列的最小值。
   - 示例: `SELECT MIN(salary) FROM employees;`

7. **GROUP_CONCAT(expr [,separator])**
   - 功能: 将指定列的值连接成一个字符串,可以指定分隔符。
   - 示例: `SELECT GROUP_CONCAT(name, ', ') FROM employees;`

8. **VAR_POP(expr)**
   - 功能: 返回总体variance。
   - 示例: `SELECT VAR_POP(salary) FROM employees;`

9. **VAR_SAMP(expr)**
    - 功能: 返回样本variance。
    - 示例: `SELECT VAR_SAMP(salary) FROM employees;`

10. **STDEV_POP(expr)**
    - 功能: 返回总体标准差。
    - 示例: `SELECT STDEV_POP(salary) FROM employees;`

11. **STDEV_SAMP(expr)**
    - 功能: 返回样本标准差。
    - 示例: `SELECT STDEV_SAMP(salary) FROM employees;`

这些就是 SQL 中常见的聚合函数,它们可以对一组数据执行计算并返回单个值。希望对您有帮助!如有其他问题,欢迎继续询问。