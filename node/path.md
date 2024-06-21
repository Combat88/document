Node.js 中 `path` 模块的常用方法及示例:

1. **路径拼接**
   - `path.join([...paths])`: 使用平台特定的分隔符把所有给定的 `path` 片段连接起来,并规范化生成的路径。
   ```javascript
   const path = require('path');
   const joinedPath = path.join('/user', 'local', 'bin');
   console.log(joinedPath); // '/user/local/bin'
   ```

2. **路径解析**
   - `path.parse(path)`: 解析路径字符串,返回一个对象,包含路径字符串的重要元素。
   ```javascript
   const path = require('path');
   const parsedPath = path.parse('/home/user/dir/file.txt');
   console.log(parsedPath);
   // {
   //   root: '/',
   //   dir: '/home/user/dir',
   //   base: 'file.txt',
   //   ext: '.txt',
   //   name: 'file'
   // }
   ```

3. **路径规范化**
   - `path.normalize(path)`: 规范化给定的 `path`，解析 '..' 和 '.' 片段。
   ```javascript
   const path = require('path');
   const normalizedPath = path.normalize('/foo/bar//baz/asdf/quux/..');
   console.log(normalizedPath); // '/foo/bar/baz/asdf'
   ```

4. **路径基准**
   - `path.resolve([...paths])`: 将路径或路径片段的序列解析为一个绝对路径。
   ```javascript
   const path = require('path');
   const resolvedPath = path.resolve('/foo/bar', './baz');
   console.log(resolvedPath); // '/foo/bar/baz'
   ```

5. **路径相对**
   - `path.relative(from, to)`: 从 `from` 路径计算到 `to` 路径的相对路径。
   ```javascript
   const path = require('path');
   const relativePath = path.relative('/data/orandea/test/aaa', '/data/orandea/impl/bbb');
   console.log(relativePath); // '../../impl/bbb'
   ```

6. **路径扩展名**
   - `path.extname(path)`: 返回路径中文件的扩展名。
   ```javascript
   const path = require('path');
   const ext = path.extname('index.html');
   console.log(ext); // '.html'
   ```

7. **路径基础名**
   - `path.basename(path[, ext])`: 返回路径的最后一部分。
   ```javascript
   const path = require('path');
   const base = path.basename('/foo/bar/baz/asdf/quux.html');
   console.log(base); // 'quux.html'
   ```

8. **路径分隔符**
   - `path.sep`: 提供特定于平台的路径段分隔符。
   ```javascript
   const path = require('path');
   console.log(path.sep); // '/' on POSIX, '\\' on Windows
   ```

9. **路径定界符**
   - `path.delimiter`: 提供特定于平台的路径定界符。
   ```javascript
   const path = require('path');
   console.log(path.delimiter); // ':' on POSIX, ';' on Windows
   ```
