好的,以下是 SQL 中常用的数据定义语言(DDL)语句及其功能和示例:

1. **CREATE DATABASE**
   功能: 创建一个新的数据库
   示例:
   ```sql
   CREATE DATABASE my_database;
   ```

2. **CREATE TABLE**
   功能: 创建一个新的数据表
   示例:
   ```sql
   CREATE TABLE users (
     id INT PRIMARY KEY,
     name VARCHAR(50) NOT NULL,
     email VARCHAR(50) UNIQUE,
     age INT CHECK (age > 0)
   );
   ```

3. **ALTER TABLE**
   功能: 修改现有表的结构
   示例:
   ```sql
   ALTER TABLE users ADD COLUMN phone VARCHAR(20);
   ALTER TABLE users MODIFY COLUMN email VARCHAR(100);
   ALTER TABLE users DROP COLUMN phone;
   ```

4. **DROP TABLE**
   功能: 删除一个现有的数据表
   示例:
   ```sql
   DROP TABLE users;
   ```

5. **TRUNCATE TABLE**
   功能: 删除表中所有数据,但保留表结构
   示例:
   ```sql
   TRUNCATE TABLE orders;
   ```

6. **CREATE INDEX**
   功能: 在表上创建索引,以提高查询速度
   示例:
   ```sql
   CREATE INDEX idx_users_email ON users (email);
   CREATE UNIQUE INDEX idx_products_code ON products (product_code);
   ```

7. **DROP INDEX**
   功能: 删除表上的索引
   示例:
   ```sql
   DROP INDEX idx_users_email ON users;
   ```

8. **CREATE VIEW**
   功能: 创建一个虚拟表,用于简化查询
   示例:
   ```sql
   CREATE VIEW user_orders AS
   SELECT u.name, o.order_date, o.total
   FROM users u
   JOIN orders o ON u.id = o.user_id;
   ```

9. **DROP VIEW**
   功能: 删除一个现有的视图
   示例:
   ```sql
   DROP VIEW user_orders;
   ```
   
10. **CREATE SEQUENCE**
    功能: 创建一个序列,用于生成唯一标识符
    示例:
    ```sql
    CREATE SEQUENCE order_seq
    START WITH 1
    INCREMENT BY 1;
    ```

11. **DROP SEQUENCE**
    功能: 删除一个现有的序列
    示例:
    ```sql
    DROP SEQUENCE order_seq;
    ```