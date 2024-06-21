以下是 SQL 中常见的所有数学函数,包括功能描述、示例和返回结果:

1. **ABS(x)**
   - 功能: 返回数值 x 的绝对值。
   - 示例: `SELECT ABS(-10) FROM dual;`
   - 返回结果: 10

2. **ACOS(x)** 
   - 功能: 返回 x 的反余弦值(范围在 0 到 π 之间)。
   - 示例: `SELECT ACOS(0.5) FROM dual;`
   - 返回结果: 1.0471975511966

3. **ASIN(x)**
   - 功能: 返回 x 的反正弦值(范围在 -π/2 到 π/2 之间)。
   - 示例: `SELECT ASIN(0.5) FROM dual;`
   - 返回结果: 0.5235987755983

4. **ATAN(x)**
   - 功能: 返回 x 的反正切值(范围在 -π/2 到 π/2 之间)。
   - 示例: `SELECT ATAN(1) FROM dual;`
   - 返回结果: 0.7853981633974

5. **ATAN2(y, x)**
   - 功能: 返回 y/x 的反正切值(范围在 -π 到 π 之间)。
   - 示例: `SELECT ATAN2(1, 1) FROM dual;`
   - 返回结果: 0.7853981633974

6. **CEIL(x)** 或 **CEILING(x)**
   - 功能: 返回大于或等于 x 的最小整数。
   - 示例: `SELECT CEIL(3.14) FROM dual;`
   - 返回结果: 4

7. **COS(x)**
   - 功能: 返回 x 的余弦值。
   - 示例: `SELECT COS(1) FROM dual;`
   - 返回结果: 0.5403023058681

8. **COT(x)**
   - 功能: 返回 x 的余切值。
   - 示例: `SELECT COT(1) FROM dual;`
   - 返回结果: 0.6420926159343

9. **DEGREES(x)**
   - 功能: 将弧度 x 转换为度。
   - 示例: `SELECT DEGREES(1.5707963267949) FROM dual;`
   - 返回结果: 90

10. **EXP(x)**
    - 功能: 返回 e 的 x 次幂。
    - 示例: `SELECT EXP(2) FROM dual;`
    - 返回结果: 7.3890560989307

11. **FLOOR(x)**
    - 功能: 返回小于或等于 x 的最大整数。
    - 示例: `SELECT FLOOR(3.14) FROM dual;`
    - 返回结果: 3

12. **LOG(x)**
    - 功能: 返回 x 的自然对数。
    - 示例: `SELECT LOG(10) FROM dual;`
    - 返回结果: 2.3025850929940

13. **LOG10(x)**
    - 功能: 返回 x 的常用对数。
    - 示例: `SELECT LOG10(100) FROM dual;`
    - 返回结果: 2

14. **MOD(x, y)**
    - 功能: 返回 x 除以 y 的余数。
    - 示例: `SELECT MOD(10, 3) FROM dual;`
    - 返回结果: 1

15. **PI()**
    - 功能: 返回 π (pi) 的值。
    - 示例: `SELECT PI() FROM dual;`
    - 返回结果: 3.14159265358979

16. **POWER(x, y)**
    - 功能: 返回 x 的 y 次方。
    - 示例: `SELECT POWER(2, 3) FROM dual;`
    - 返回结果: 8

17. **RADIANS(x)**
    - 功能: 将度 x 转换为弧度。
    - 示例: `SELECT RADIANS(90) FROM dual;`
    - 返回结果: 1.5707963267949

18. **RAND()**
    - 功能: 返回 0 到 1 之间的随机浮点数。
    - 示例: `SELECT RAND() FROM dual;`
    - 返回结果: 一个随机浮点数

19. **ROUND(x, [d])**
    - 功能: 将数值 x 四舍五入到小数点后 d 位。如果省略 d,则四舍五入到最接近的整数。
    - 示例: `SELECT ROUND(3.14159, 2) FROM dual;`
    - 返回结果: 3.14

20. **SIGN(x)**
    - 功能: 返回 x 的符号。如果 x 为负数,返回 -1; 如果 x 为正数,返回 1; 如果 x 为 0,返回 0。
    - 示例: `SELECT SIGN(-10) FROM dual;`, `SELECT SIGN(10) FROM dual;`, `SELECT SIGN(0) FROM dual;`
    - 返回结果: -1, 1, 0

21. **SIN(x)**
    - 功能: 返回 x 的正弦值。
    - 示例: `SELECT SIN(1) FROM dual;`
    - 返回结果: 0.8414709848079

22. **SQRT(x)**
    - 功能: 返回 x 的平方根。
    - 示例: `SELECT SQRT(25) FROM dual;`
    - 返回结果: 5

23. **TAN(x)**
    - 功能: 返回 x 的正切值。
    - 示例: `SELECT TAN(1) FROM dual;`
    - 返回结果: 1.5574077246549
  
24. **TRUNC(x, [d])**
    - 功能: 返回数值 x 截断到小数点后 d 位。如果省略 d,则截断到最接近的整数。
    - 示例: `SELECT TRUNC(3.14159, 2) FROM dual;`
    - 返回结果: 3.14

