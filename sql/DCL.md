好的,以下是 SQL 中常用的数据控制语言(DCL)语句及其功能和示例:

1. **GRANT**
   功能: 授予用户特定的权限
   示例:
   ```sql
   -- 授予 John 用户对 users 表的 SELECT 和 INSERT 权限
   GRANT SELECT, INSERT ON users TO 'john'@'localhost';
   -- 授予 admin 用户所有数据库的所有权限
   GRANT ALL PRIVILEGES ON *.* TO 'admin'@'%';
   ```

2. **REVOKE**
   功能: 撤销用户的特定权限
   示例:
   ```sql
   -- 撤销 John 用户对 users 表的 INSERT 权限
   REVOKE INSERT ON users FROM 'john'@'localhost';

   -- 撤销 admin 用户的所有数据库的所有权限
   REVOKE ALL PRIVILEGES ON *.* FROM 'admin'@'%';
   ```

3. **BEGIN**
   功能: 开始一个事务
   示例:
   ```sql
   BEGIN;
   UPDATE users SET email = 'new_email@example.com' WHERE id = 1;
   DELETE FROM orders WHERE user_id = 2;
   COMMIT;
   ```

4. **COMMIT**
   功能: 提交当前事务的所有更改
   示例:
   ```sql
   BEGIN;
   INSERT INTO products (name, price) VALUES ('Product A', 9.99);
   INSERT INTO products (name, price) VALUES ('Product B', 14.99);
   COMMIT;
   ```

5. **ROLLBACK**
   功能: 撤销当前事务中所有的更改
   示例:
   ```sql
   BEGIN;
   UPDATE users SET email = 'invalid_email' WHERE id = 1;
   SELECT * FROM users; -- 这里可以看到更新还未生效
   ROLLBACK;
   SELECT * FROM users; -- 这里可以看到更新被撤销了
   ```

6. **SAVEPOINT**
   功能: 在事务中设置一个保存点,允许部分回滚
   示例:
   ```sql
   BEGIN;
   INSERT INTO orders (user_id, total) VALUES (1, 100.00);
   SAVEPOINT save_point_1;
   INSERT INTO orders (user_id, total) VALUES (2, 50.00);
   ROLLBACK TO save_point_1; -- 只会回滚第二条 INSERT 语句
   COMMIT;
   ```

7. **SET TRANSACTION**
   功能: 设置事务的隔离级别和其他选项
   示例:
   ```sql
   SET TRANSACTION ISOLATION LEVEL READ COMMITTED;
   SET TRANSACTION READ ONLY;
   ```

8. **SHOW GRANTS**
   功能: 显示用户的权限
   示例:
   ```sql
   SHOW GRANTS FOR 'john'@'localhost';
   ```
    
9. **SHOW VARIABLES**
   功能: 显示数据库的变量和值
   示例:
   ```sql
   SHOW VARIABLES LIKE '%isolation%';
   ```
       
10. **SHOW ENGINES**
   功能: 显示数据库的存储引擎和状态
   示例:
   ```sql
   SHOW ENGINES;
   ```
        
11. **SHOW CREATE TABLE**
   功能: 显示创建指定表的 SQL 语句
   示例:
   ```sql
   SHOW CREATE TABLE users;
   ```

12. **SHOW DATABASES**
   功能: 显示所有数据库的列表
   示例:
   ```sql
   SHOW DATABASES;
   ```
    
13. **SHOW TABLES**
   功能: 显示指定数据库的所有表的列表
   示例:
   ```sql
   SHOW TABLES FROM my_database;
   ```
    
14. **SHOW COLUMNS**
   功能: 显示指定表的所有列的列表
   示例:
   ```sql
   SHOW COLUMNS FROM users;
   ```
    
15. **SHOW INDEXES**
   功能: 显示指定表的所有索引的列表
   示例:
   ```sql
   SHOW INDEXES FROM users;
   ```

16. **SHOW PROCESSLIST**
   功能: 显示当前正在运行的所有进程的列表
   示例:
   ```sql
   SHOW PROCESSLIST;
   ```

17. **SHOW STATUS**
   功能: 显示数据库的系统状态信息
   示例:
   ```sql
   SHOW STATUS LIKE '%connections%';
   ```

18. **SHOW WARNINGS**
   功能: 显示最近执行的语句的警告信息
   示例:
   ```sql
   SHOW WARNINGS;
   ```

19. **START TRANSACTION**
   功能: 开始一个新的事务
   示例:
   ```sql
   START TRANSACTION;
   ```

20. **TRUNCATE TABLE**
   功能: 清空指定表的数据,但不删除表
   示例:
   ```sql
   TRUNCATE TABLE users;
   ```

21. **UPDATE**
   功能: 更新指定表的记录
   示例:
   ```sql
   UPDATE users SET name = 'John Doe', email = 'johndoe@example.com' WHERE id = 1;
   ```
    
22. **WHILE**
   功能: 重复执行指定语句,直到条件不满足为止
   示例:
   ```sql
   WHILE condition DO
       -- 执行的语句
   END WHILE;
   ```

23. **WITH**
   功能: 创建一个临时表,用于存储查询结果
   示例:
   ```sql
   WITH temp_table AS (
       SELECT * FROM users WHERE id > 10
   )
   SELECT * FROM temp_table;
   ```
