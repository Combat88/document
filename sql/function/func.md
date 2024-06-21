好的,以下是 SQL 中所有常用的聚合函数及其功能和示例:

1. **COUNT()**
   功能: 统计满足条件的记录数
   示例:
   ```sql
   SELECT COUNT(*) FROM users;                 -- 统计 users 表中的总行数
   SELECT COUNT(email) FROM users;            -- 统计 users 表中 email 列不为 NULL 的行数
   SELECT COUNT(DISTINCT email) FROM users;   -- 统计 users 表中 email 列的唯一值个数
   SELECT COUNT(*) FROM orders WHERE status = 'completed'; -- 统计 orders 表中 status 列值为 'completed' 的行数
   ```

2. **SUM()**
   功能: 计算指定列的总和
   示例:
   ```sql
   SELECT SUM(total) AS total_sales FROM orders;             -- 计算 orders 表中 total 列的总和
   SELECT department_id, SUM(salary) AS total_salary FROM employees GROUP BY department_id; -- 按部门统计工资总和
   ```

3. **AVG()**
   功能: 计算指定列的平均值
   示例:
   ```sql
   SELECT AVG(age) AS average_age FROM users;               -- 计算 users 表中 age 列的平均值
   SELECT product_id, AVG(price) AS average_price FROM products GROUP BY product_id; -- 按产品统计平均价格
   ```

4. **MAX()**
   功能: 返回指定列的最大值
   示例:
   ```sql
   SELECT MAX(order_date) AS latest_order FROM orders;      -- 查找 orders 表中最新的订单日期
   SELECT department_id, MAX(salary) AS max_salary FROM employees GROUP BY department_id; -- 按部门查找最高工资
   ```

5. **MIN()**
   功能: 返回指定列的最小值
   示例:
   ```sql
   SELECT MIN(join_date) AS earliest_join_date FROM employees; -- 查找最早加入公司的员工
   SELECT category_id, MIN(price) AS min_price FROM products GROUP BY category_id; -- 按类别查找最低价格
   ```

6. **GROUP_CONCAT()**
   功能: 将一列中的值连接成字符串
   示例:
   ```sql
   SELECT user_id, GROUP_CONCAT(product_name) AS purchased_products FROM orders GROUP BY user_id; -- 按用户查看购买的所有商品
   SELECT department, GROUP_CONCAT(DISTINCT employee_name) AS department_employees FROM employees GROUP BY department; -- 按部门列出所有员工姓名
   ```
7.**coalesece**
    功能: 返回第一个非 NULL 的值
    示例:
    ```sql
    SELECT coalesce(NULL, 'default value'); -- 返回 'default value'
    SELECT coalesce(NULL, NULL, 'third value'); -- 返回 'third value'
    ```
        
8. **IFNULL()**
    功能: 返回第一个非 NULL 的值
    示例:
    ```sql
    SELECT IFNULL(NULL, 'default value'); -- 返回 'default value'
    SELECT IFNULL(NULL, NULL, 'third value'); -- 返回 NULL
    ```
    
9. **NULLIF()**
    功能: 返回第一个非 NULL 的值
    示例:
    ```sql
    SELECT NULLIF(1, 1); -- 返回 NULL
    SELECT NULLIF(1, 2); -- 返回 1
    ```
