JavaScript 数组的常用方法:

1. `concat()`
   - 功能: 合并两个或多个数组,返回一个新数组
   - 是否改变原数组: 否
   - 示例:
     ```javascript
     const arr1 = [1, 2];
     const arr2 = [3, 4];
     const newArr = arr1.concat(arr2);
     console.log(newArr); // 输出: [1, 2, 3, 4]
     console.log(arr1); // 输出: [1, 2]
     ```

2. `slice()`
   - 功能: 返回一个新数组,包含从开始到结束（不包括结束）的数组元素
   - 是否改变原数组: 否
   - 示例:
     ```javascript
     const arr = [1, 2, 3, 4, 5];
     const newArr = arr.slice(1, 4);
     console.log(newArr); // 输出: [2, 3, 4]
     console.log(arr); // 输出: [1, 2, 3, 4, 5]
     ```

3. `splice()`
   - 功能: 向/从数组中添加/删除元素,并返回被删除的元素
   - 是否改变原数组: 是
   - 示例:
     ```javascript
     const arr = [1, 2, 3, 4, 5];
     const deleted = arr.splice(2, 1, 'a', 'b');
     console.log(arr); // 输出: [1, 2, 'a', 'b', 4, 5]
     console.log(deleted); // 输出: [3]
     ```

4. `reverse()`
   - 功能: 反转数组中元素的顺序
   - 是否改变原数组: 是
   - 示例:
     ```javascript
     const arr = [1, 2, 3, 4, 5];
     arr.reverse();
     console.log(arr); // 输出: [5, 4, 3, 2, 1]
     ```

5. `sort()`
   - 功能: 对数组元素进行排序,默认按照字符串 Unicode 码点进行排序
   - 是否改变原数组: 是
   - 示例:
     ```javascript
     const arr = [5, 2, 9, 1, 7];
     arr.sort();
     console.log(arr); // 输出: [1, 2, 5, 7, 9]
     
     // 自定义排序规则
     arr.sort((a, b) => a - b);
     console.log(arr); // 输出: [1, 2, 5, 7, 9]
     ```

6. `map()`
   - 功能: 创建一个新数组,其结果是该数组中的每个元素都调用一个提供的函数后的返回值
   - 是否改变原数组: 否
   - 示例:
     ```javascript
     const arr = [1, 2, 3, 4, 5];
     const newArr = arr.map(x => x * 2);
     console.log(newArr); // 输出: [2, 4, 6, 8, 10]
     console.log(arr); // 输出: [1, 2, 3, 4, 5]
     ```

7. `filter()`
   - 功能: 创建一个新数组,其包含通过所提供函数实现的测试的所有元素
   - 是否改变原数组: 否
   - 示例:
     ```javascript
     const arr = [1, 2, 3, 4, 5];
     const newArr = arr.filter(x => x % 2 === 0);
     console.log(newArr); // 输出: [2, 4]
     console.log(arr); // 输出: [1, 2, 3, 4, 5]
     ```
8. `forEach()`
   - 功能: 对数组的每个元素执行一次提供的函数
   - 是否改变原数组: 否
   - 示例:
     ```javascript
     const arr = [1, 2, 3, 4, 5];
     arr.forEach(x => console.log(x));
     // 输出:
     1
     2
     3
     4
     5
     ```

9. `every()`
    - 功能: 检查数组中的所有元素是否都通过了指定函数的测试
    - 是否改变原数组: 否
    - 示例:
      ```javascript
      const arr = [1, 2, 3, 4, 5];
      const result = arr.every(x => x > 0);
      console.log(result); // 输出: true
      ```

10. `some()`
    - 功能: 检查数组中是否存在至少一个元素通过了指定函数的测试
    - 是否改变原数组: 否
    - 示例:
      ```javascript
      const arr = [1, 2, 3, 4, 5];
      const result = arr.some(x => x > 3);
      console.log(result); // 输出: true
      ```

11. `reduce()`
    - 功能: 对数组中的元素进行累积
    - 是否改变原数组: 否
    - 示例:
      ```javascript
      const arr = [1, 2, 3, 4, 5];
      const result = arr.reduce((acc, cur) => acc + cur);
      console.log(result); // 输出: 15
      ```

12. `reduceRight()`
    - 功能: 对数组中的元素进行累积,从右到左
    - 是否改变原数组: 否
    - 示例:
      ```javascript
          const arr = [1, 2, 3, 4, 5];
          const result = arr.reduceRight((acc, cur) => acc + cur);
          console.log(result); // 输出: 15
      ```

13. `fill()`
    - 功能: 使用一个固定值填充一个数组中从起始索引到终止索引内的全部元素
    - 是否改变原数组: 是
    - 示例:
      ```javascript
      const arr = [1, 2, 3, 4, 5];
      arr.fill(0, 2, 4);
      console.log(arr); // 输出: [1, 2, 0, 0, 5]
      ```

14. `copyWithin()`
    - 功能: 浅复制数组中的一部分到同一数组中的另一个位置,并返回它,不会改变原数组的长度
    - 是否改变原数组: 是
    - 示例:
      ```javascript
      const arr = [1, 2, 3, 4, 5];
      arr.copyWithin(0, 3);
      console.log(arr); // 输出: [4, 5, 3, 4, 5]
      ```

15. `find()`
    - 功能: 返回数组中满足提供的测试函数的第一个元素的值
    - 是否改变原数组: 否
    - 示例:
      ```javascript
      const arr = [1, 2, 3, 4, 5];
      const result = arr.find(x => x > 3);
      console.log(result); // 输出: 4
      ```

16. `findIndex()`
    - 功能: 返回数组中满足提供的测试函数的第一个元素的索引
    - 是否改变原数组: 否
    - 示例:
      ```javascript
          const arr = [1, 2, 3, 4, 5];
          const result = arr.findIndex(x => x > 3);
          console.log(result); // 输出: 3
      ```

17. `entries()`
    - 功能: 返回一个新的Array Iterator对象,该对象包含数组中每个索引的键值对
    - 是否改变原数组: 否
    - 示例:
      ```javascript
              const arr = ['a', 'b', 'c'];
              const iterator = arr.entries();
              console.log(iterator.next().value); // 输出: [0, 'a']
              console.log(iterator.next().value); // 输出: [1, 'b']
              console.log(iterator.next().value); // 输出: [2, 'c']
      ```

18. `keys()`
    - 功能: 返回一个新的Array Iterator对象,该对象包含数组中每个索引的键
    - 是否改变原数组: 否
    - 示例:
      ```javascript
              const arr = ['a', 'b', 'c'];
              const iterator = arr.keys();
              console.log(iterator.next().value); // 输出: 0
              console.log(iterator.next().value); // 输出: 1
              console.log(iterator.next().value); // 输出: 2
      ```

19. `values()`
    - 功能: 返回一个新的Array Iterator对象,该对象包含数组中每个索引的值
    - 是否改变原数组: 否
    - 示例:
      ```javascript
              const arr = ['a', 'b', 'c'];
              const iterator = arr.values();
              console.log(iterator.next().value); // 输出: 'a'
              console.log(iterator.next().value); // 输出: 'b'
              console.log(iterator.next().value); // 输出: 'c'
      ```

20. `includes()`
    - 功能: 判断一个数组是否包含一个指定的值,返回布尔值
    - 是否改变原数组: 否
    - 示例:
      ```javascript
              const arr = [1, 2, 3, 4, 5];
              console.log(arr.includes(3)); // 输出: true
              console.log(arr.includes(6)); // 输出: false
      ```

21. `fill()`
    - 功能: 使用一个固定值来填充数组
    - 是否改变原数组: 是
    - 示例:
      ```javascript
              const arr = [1, 2, 3, 4, 5];
              arr.fill(0);
              console.log(arr); // 输出: [0, 0, 0, 0, 0]
      ```

22. `copyWithin()`
    - 功能: 从数组的指定位置开始复制元素到数组的另一个指定位置中
    - 是否改变原数组: 是
    - 示例:
      ```javascript
              const arr = [1, 2, 3, 4, 5];
              arr.copyWithin(0, 3);
              console.log(arr); // 输出: [4, 5, 3, 4, 5]
      ```

23. `flat()`
    - 功能: 将一个多维数组扁平化为一维数组
    - 是否改变原数组: 是
    - 示例:
      ```javascript
              const arr = [1, 2, [3, 4, [5, 6]]];
              console.log(arr.flat()); // 输出: [1, 2, 3, 4, [5, 6]]
      ```

24. `flatMap()`
    - 功能: 先对数组中的每个元素应用一个函数,然后将结果扁平化为一维数组
    - 是否改变原数组: 是
    - 示例:
      ```javascript
              const arr = [1, 2, 3, 4, 5];
              console.log(arr.flatMap(x => [x, x * 2])); // 输出: [1, 2, 2, 4, 3, 6, 4, 8, 5, 10]
      ```