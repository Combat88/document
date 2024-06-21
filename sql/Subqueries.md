好的,以下是 SQL 中常见的子查询及其功能和示例:
1. **单行子查询**
   功能: 返回单个值,可以用于 `SELECT`、`WHERE`、`HAVING` 等子句中
   示例:
   ```sql
   -- 查找工资高于部门平均工资的员工
   SELECT employee_name, salary
   FROM employees
   WHERE salary > (
     SELECT AVG(salary)
     FROM employees
     WHERE department_id = employees.department_id
   );

   -- 查找订单总额高于所有订单平均总额的订单
   SELECT order_id, total
   FROM orders
   WHERE total > (
     SELECT AVG(total)
     FROM orders
   )
   ORDER BY total DESC;
   ```

2. **多行子查询**
   功能: 返回多个值,可以使用 `IN`、`ANY`、`ALL` 等操作符
   示例:
   ```sql
   -- 查找所有曾经下过订单的用户
   SELECT user_name
   FROM users
   WHERE user_id IN (
     SELECT user_id
     FROM orders
   );

   -- 查找工资高于部门所有员工工资的员工
   SELECT employee_name, salary
   FROM employees e1
   WHERE salary > ALL (
     SELECT salary
     FROM employees e2
     WHERE e1.department_id = e2.department_id
   );
   ```

3. **相关子查询**
   功能: 子查询引用了外层查询的列
   示例:
   ```sql
   -- 查找每个部门工资最高的员工
   SELECT employee_name, salary
   FROM employees e1
   WHERE salary = (
     SELECT MAX(salary)
     FROM employees e2
     WHERE e1.department_id = e2.department_id
   );

   -- 查找每个用户最近一次的订单
   SELECT u.user_name, o.order_date, o.total
   FROM users u
   JOIN (
     SELECT user_id, MAX(order_date) AS latest_order_date
     FROM orders
     GROUP BY user_id
   ) latest_order ON u.user_id = latest_order.user_id
   JOIN orders o ON latest_order.user_id = o.user_id AND latest_order.latest_order_date = o.order_date;
   ```

4. **EXISTS 子查询**
   功能: 检查子查询是否至少返回一行数据
   示例:
   ```sql
   -- 查找有下过订单的用户
   SELECT user_name
   FROM users u
   WHERE EXISTS (
     SELECT 1
     FROM orders o
     WHERE o.user_id = u.user_id
   );

   -- 查找没有下过任何订单的用户
   SELECT user_name
   FROM users u
   WHERE NOT EXISTS (
     SELECT 1
     FROM orders o
     WHERE o.user_id = u.user_id
   );
   ```