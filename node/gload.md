以下是 Node.js 中常见的全局变量,以及它们的功能和示例:

1. __filename
   - 功能: 返回当前模块的完整文件路径。
   - 示例:
     ```javascript
     console.log(__filename); // 输出: /path/to/your/file.js
     ```

2. __dirname
   - 功能: 返回当前模块所在的目录路径。
   - 示例:
     ```javascript
     console.log(__dirname); // 输出: /path/to/your/directory
     ```

3. module
   - 功能: 代表当前模块本身,包含与当前模块相关的信息和方法。
   - 示例:
     ```javascript
     console.log(module.filename); // 输出: /path/to/your/file.js
     ```

4. exports
   - 功能: 用于导出模块中的公共接口。
   - 示例:
     ```javascript
     // 在 my-module.js 文件中
     exports.hello = function() {
       console.log('Hello, world!');
     };

     // 在其他文件中使用
     const myModule = require('./my-module');
     myModule.hello(); // 输出: Hello, world!
     ```

5. require()
   - 功能: 用于加载模块。
   - 示例:
     ```javascript
     const fs = require('fs');
     ```

6. console
   - 功能: 提供控制台输出功能。
   - 示例:
     ```javascript
     console.log('Hello, world!');
     console.error('An error occurred');
     ```

7. process
   - 功能: 代表当前 Node.js 进程,提供与操作系统交互的接口。
   - 示例:
     ```javascript
     console.log(process.version); // 输出: v14.15.4
     console.log(process.platform); // 输出: darwin (macOS)
     ```

8. Buffer
   - 功能: 提供处理二进制数据的功能。
   - 示例:
     ```javascript
     const buf = Buffer.from('Hello, world!', 'utf-8');
     console.log(buf.toString('hex')); // 输出: 48656c6c6f2c20776f726c6421
     ```

9. setTimeout()
   - 功能: 设置定时器,在指定的毫秒数后执行回调函数。
   - 示例:
     ```javascript
     setTimeout(function() {
       console.log('Timer completed');
     }, 2000);
     ```

10. setInterval()
   - 功能: 设置定时器,每隔指定的毫秒数执行回调函数。
   - 示例:
     ```javascript
     let count = 0;
     const intervalId = setInterval(function() {
       count++;
       console.log('Count:', count);

       if (count === 5) {
         clearInterval(intervalId);
       }
     }, 1000);
     ```
           
11. clearTimeout()
   - 功能: 清除指定的定时器。
   - 示例:
     ```javascript
     const timerId = setTimeout(function() {
       console.log('Timer completed');
     }, 2000);

     clearTimeout(timerId);
     ```

12. clearInterval()
   - 功能: 清除指定的定时器。
   - 示例:
     ```javascript
     let count = 0;
     const intervalId = setInterval(function() {
       count++;
       console.log('Count:', count);

       if (count === 5) {
         clearInterval(intervalId);
       }
     }, 1000);
     ```

13. global
   - 功能: 全局对象,提供全局变量和函数的访问。
   - 示例:
     ```javascript
     console.log(global.process); // 输出: 当前 Node.js 进程对象
     ```
14. require.main
   - 功能: 获取当前模块的入口文件。
   - 示例:
     ```javascript
     console.log(require.main === module); // 输出: true
     ```


