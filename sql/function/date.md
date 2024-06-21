下面是 SQL 中常见的所有日期函数,包括功能描述、示例和返回结果:

1. **CURRENT_DATE**
   - 功能: 返回当前日期。
   - 示例: `SELECT CURRENT_DATE FROM dual;`
   - 返回结果: 2024-06-20

2. **CURRENT_TIME**
   - 功能: 返回当前时间。
   - 示例: `SELECT CURRENT_TIME FROM dual;`
   - 返回结果: 15:58:00

3. **CURRENT_TIMESTAMP**
   - 功能: 返回当前日期和时间。
   - 示例: `SELECT CURRENT_TIMESTAMP FROM dual;`
   - 返回结果: 2024-06-20 15:58:00

4. **EXTRACT(unit FROM date)**
   - 功能: 从日期中提取指定的时间间隔单位。
   - 示例: `SELECT EXTRACT(YEAR FROM '2024-06-20') FROM dual;`
   - 返回结果: 2024

5. **DATEDIFF(date1, date2)**
   - 功能: 计算两个日期之间相差的天数。
   - 示例: `SELECT DATEDIFF('2024-06-20', '2024-06-01') FROM dual;`
   - 返���结果: 19

6. **TIMEDIFF(time1, time2)**
   - 功能: 计算两个时间之间相差的时间。
   - 示例: `SELECT TIMEDIFF('16:00:00', '15:30:00') FROM dual;`
   - 返回结果: 00:30:00

7. **DATE_FORMAT(date, format)**
   - 功能: 根据指定的格式显示日期。
   - 示例: `SELECT DATE_FORMAT('2024-06-20', '%Y-%m-%d') FROM dual;`
   - 返回结果: 2024-06-20

8. **TIMESTAMPDIFF(unit, datetime1, datetime2)**
   - 功能: 计算两个时间戳之间相差的时间间隔。
   - 示例: `SELECT TIMESTAMPDIFF(SECOND, '2024-06-20 15:58:00', '2024-06-20 15:58:30') FROM dual;`
   - 返回结果: 30

9. **ADDDATE(date, INTERVAL expr unit)**
   - 功能: 将日期加上指定的时间间隔。
   - 示例: `SELECT ADDDATE('2024-06-20', INTERVAL 10 DAY) FROM dual;`
   - 返回结果: 2024-06-30

10. **SUBDATE(date, INTERVAL expr unit)**
    - 功能: 将日期减去指定的时间间隔。
    - 示例: `SELECT SUBDATE('2024-06-20', INTERVAL 10 DAY) FROM dual;`
    - 返回结果: 2024-06-10
