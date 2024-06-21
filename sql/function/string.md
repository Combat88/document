下面是 SQL 中常见的所有字符串函数,包括功能描述、示例和返回结果:

1. **CONCAT(str1, str2, ...)**
   - 功能: 将多个字符串连接成一个字符串。
   - 示例: `SELECT CONCAT('Hello', ' ', 'World') FROM dual;`
   - 返回结果: Hello World

2. **CHAR_LENGTH(str)** 或 **LENGTH(str)**
   - 功能: 返回字符串 str 的字符长度。
   - 示例: `SELECT CHAR_LENGTH('SQL'), LENGTH('SQL') FROM dual;`
   - 返回结果: 3, 3

3. **LOWER(str)** 或 **LCASE(str)**
   - 功能: 将字符串 str 转换为小写。
   - 示例: `SELECT LOWER('SQL'), LCASE('SQL') FROM dual;`
   - 返回结果: sql, sql

4. **UPPER(str)** 或 **UCASE(str)**
   - 功能: 将字符串 str 转换为大写。
   - 示例: `SELECT UPPER('sql'), UCASE('sql') FROM dual;`
   - 返回结果: SQL, SQL

5. **LTRIM(str)** 
   - 功能: 删除字符串 str 左侧的空格。
   - 示例: `SELECT LTRIM('   SQL   ') FROM dual;`
   - 返回结果: SQL   

6. **RTRIM(str)**
   - 功能: 删除字符串 str 右侧的空格。
   - 示例: `SELECT RTRIM('   SQL   ') FROM dual;`
   - 返回结果:    SQL

7. **TRIM(str)**
   - 功能: 删除字符串 str 左右两侧的空格。
   - 示例: `SELECT TRIM('   SQL   ') FROM dual;`
   - 返回结果: SQL

8. **SUBSTRING(str, pos, [len])**
   - 功能: 从字符串 str 的指定位置 pos 开始,截取长度为 len 的子字符串。
   - 示例: `SELECT SUBSTRING('SQL Tutorial', 5, 7) FROM dual;`
   - 返回结果: Tutorial

9. **REPLACE(str, from_str, to_str)**
   - 功能: 将字符串 str 中所有出现的 from_str 替换为 to_str。
   - 示例: `SELECT REPLACE('SQL Tutorial', 'SQL', 'MySQL') FROM dual;`
   - 返回结果: MySQL Tutorial

10. **REPEAT(str, count)**
    - 功能: 将字符串 str 重复 count 次。
    - 示例: `SELECT REPEAT('SQL ', 3) FROM dual;`
    - 返回结果: SQL SQL SQL 

11. **REVERSE(str)**
    - 功能: 将字符串 str 反转。
    - 示例: `SELECT REVERSE('SQL') FROM dual;`
    - 返回结果: LQS

12. **SPACE(n)**
    - 功能: 返回 n 个空格组成的字符串。
    - 示例: `SELECT CONCAT('SQL', SPACE(3), 'Tutorial') FROM dual;`
    - 返回结果: SQL   Tutorial

13. **LOCATE(substr, str, [pos])**
    - 功能: 在字符串 str 中查找子字符串 substr 首次出现的位置,如果未找到则返回 0。
    - 示例: `SELECT LOCATE('Tutorial', 'SQL Tutorial', 1) FROM dual;`
    - 返回结果: 5

以上就是 SQL 中常见的字符串函数,希望对您有帮助。如有任何其他问题,欢迎继续询问。