以下是几种常用的 SQL 语句,以及它们的功能和示例:
1. **SELECT 单表 语句**
   - 功能: 从表中查询数据
   - 示例:
   ```sql
   SELECT * FROM users;
   SELECT name, email FROM users;
   SELECT * FROM users WHERE id > 10 AND age < 30;
   ```


2. **INSERT 语句**
   - 功能: 向表中插入新数据
   - 示例:
   ```sql
   INSERT INTO users (name, email) VALUES ('John Doe', 'john@example.com');
   INSERT INTO users (name, email, age) VALUES ('Jane Smith', 'jane@example.com', 25);
   ```

3. **UPDATE 语句**
   - 功能: 更新表中的数据
   - 示例:
   ```sql
   UPDATE users SET email = 'newemail@example.com' WHERE id = 1;
   UPDATE users SET age = age + 1 WHERE id > 10;
   ```

4. **DELETE 语句**
   - 功能: 从表中删除数据
   - 示例:
   ```sql
   DELETE FROM users WHERE id = 1;
   DELETE FROM users WHERE age > 50;
   ```

5. **JOIN 语句**
      1. 内连接
        - 功能:返回两个表中满足连接条件的记录
        - 示例：
          ``` sql
          SELECT users.name, orders.order_date, orders.total
          FROM users
          INNER JOIN orders ON users.id = orders.user_id;
          ```

          
      2. 左连接
        - 功能: 返回左表中的所有记录,以及右表中与左表匹配的记录
        - 示例:
          ``` sql
          SELECT users.name, orders.order_date, orders.total
          FROM users
          LEFT JOIN orders ON users.id = orders.user_id;
          ```

      3. 右连接
        - 功能: 返回右表中的所有记录,以及左表中与右表匹配的记录
        - 示例:
          ``` sql
           SELECT users.name, orders.order_date, orders.total
           FROM users
           RIGHT JOIN orders ON users.id = orders.user_id;
          ```

      4. 交叉连接
        - 功能: 返回两个表中所有记录的组合
        - 示例:
          ``` sql
          SELECT *
          FROM users
          CROSS JOIN orders;
          ```
           
      5. 自然连接
          - 功能: 自动检测两个表中相同列名的列,并返回它们的连接结果
          - 示例:
            ``` sql
            SELECT *
            FROM users
            NATURAL JOIN orders;
            ```
           
      6. 外连接
          - 功能: 返回左表和右表中所有匹配的记录,以及左表和右表中不匹配的记录
          - 示例:
            ``` sql
            SELECT *
            FROM users
            FULL OUTER JOIN orders ON users.id = orders.user_id;
            ```

      7. 半连接
          - 功能: 返回左表中满足连接条件的记录,但不返回右表中的记录
          - 示例:
            ``` sql
            SELECT *
            FROM users
            LEFT JOIN orders ON users.id = orders.user_id
            WHERE orders.user_id IS NULL;
            ```

      8.  全连接
           - 功能:返回两个表中所有的记录,满足连接条件的记录在结果集中
           - 示例：
            ``` sql
            SELECT users.name, orders.order_date, orders.total
            FROM users
            FULL JOIN orders ON users.id = orders.user_id;
           ```

6. **WHERE 子句**
   - 功能: 添加查询条件
   - 示例:
   ```sql
   SELECT * FROM users WHERE email LIKE '%@example.com';
   SELECT * FROM orders WHERE total > 100 AND order_date > '2022-01-01';
   ```

7. **ORDER BY 子句**
   - 功能: 对查询结果进行排序
   - 示例:
   ```sql
   SELECT * FROM users ORDER BY name ASC;
   SELECT * FROM orders ORDER BY total DESC, order_date ASC;
   ```

8. **GROUP BY 子句**
   - 功能: 对查询结果进行分组
   - 示例:
   ```sql
   SELECT department_id, COUNT(*) as num_employees
   FROM users
   GROUP BY department_id;

   SELECT order_date, SUM(total) as total_sales
   FROM orders
   GROUP BY order_date;
   ```

9. **HAVING 子句**
   - 功能: 对分组结果进行筛选
   - 示例:
   ```sql
   SELECT department_id, COUNT(*) as num_employees
   FROM users
   GROUP BY department_id
   HAVING num_employees > 5;

   SELECT order_date, SUM(total) as total_sales
   FROM orders
   GROUP BY order_date
   HAVING total_sales > 1000;
   ```
10. **LIMIT 子句**
      - 功能: 限制查询结果的行数
      - 示例:
      ```sql
      SELECT * FROM users LIMIT 10;
      SELECT * FROM orders LIMIT 5 OFFSET 10;
      ```