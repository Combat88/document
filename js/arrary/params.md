JavaScript 数组常见的属性包括:

1. `length`
   - 功能: 获取数组的长度
   - 是否改变原数组: 否
   - 示例:
     ```javascript
     const arr = [1, 2, 3];
     console.log(arr.length); // 输出: 3
     ```

2. `constructor`
   - 功能: 返回创建数组实例的函数
   - 是否改变原数组: 否
   - 示例:
     ```javascript
     const arr = [1, 2, 3];
     console.log(arr.constructor); // 输出: function Array() { [native code] }
     ```

3. `prototype`
   - 功能: 允许向数组添加属性和方法
   - 是否改变原数组: 否
   - 示例:
     ```javascript
     Array.prototype.square = function() {
       return this.map(x => x * x);
     };
     const arr = [1, 2, 3];
     console.log(arr.square()); // 输出: [1, 4, 9]
     ```

4. `index` 
   - 功能: 获取元素的索引
   - 是否改变原数组: 否
   - 示例:
     ```javascript
     const arr = [10, 20, 30, 40, 50];
     console.log(arr.indexOf(30)); // 输出: 2
     ```

5. `lastIndex`
   - 功能: 获取元素最后一次出现的索引
   - 是否改变原数组: 否
   - 示例:
     ```javascript
     const arr = [10, 20, 30, 40, 30];
     console.log(arr.lastIndexOf(30)); // 输出: 4
     ```

6. `isArray`
   - 功能: 判断是否为数组
   - 是否改变原数组: 否
   - 示例:
     ```javascript
     console.log(Array.isArray([1, 2, 3])); // 输出: true
     console.log(Array.isArray({})); // 输出: false
     ```
