 Node.js 中 fs 模块的常用方法。
1. **文件读写**
   - 异步读取文件内容：`fs.readFile(path[, options], callback)`
     ```javascript
     fs.readFile('file.txt', 'utf8', (err, data) => {
       if (err) throw err;
       console.log(data);
     });
     ```
   - 同步读取文件内容：`fs.readFileSync(path[, options])`
     ```javascript
     try {
       const data = fs.readFileSync('file.txt', 'utf8');
       console.log(data);
     } catch (err) {
       console.error(err);
     }
     ```
   - 异步写入文件：`fs.writeFile(file, data[, options], callback)`
     ```javascript
     fs.writeFile('file.txt', 'Hello, Node.js!', (err) => {
       if (err) throw err;
       console.log('File written successfully!');
     });
     ```
   - 同步写入文件：`fs.writeFileSync(file, data[, options])`
     ```javascript
     try {
       fs.writeFileSync('file.txt', 'Hello, Node.js!');
       console.log('File written successfully!');
     } catch (err) {
       console.error(err);
     }
     ```
    
   - 异步创建可读流：`fs.createReadStream(path[, options])`
     ```javascript
     options: {
       encoding: 'utf8', // 指定编码，默认不指定
       flags: 'r', // 指定文件操作模式，默认'r'
       autoClose: true, // 指定是否自动关闭文件，默认true
       start: 0, // 指定从文件起始位置开始读取，默认0
       end: undefined, // 指定从文件结束位置开始读取，默认undefined
     }
    
     const readStream = fs.createReadStream('file.txt', {
       encoding: 'utf8',
     });
     ```
   - 同步创建可读流：`fs.createReadStreamSync(path[, options])`
     ```javascript
     options: {
       encoding: 'utf8', // 指定编码，默认不指定
       flags: 'r', // 指定文件操作模式，默认'r'
       autoClose: true, // 指定是否自动关闭文件，默认true
       start: 0, // 指定从文件起始位置开始读取，默认0
       end: undefined, // 指定从文件结束位置开始读取，默认undefined
     }
     const readStream = fs.createReadStreamSync('file.txt', {
       encoding: 'utf8',
       });
     ```
   - 异步创建可写流：`fs.createWriteStream(path[, options])`
     ```javascript
     options: {
       encoding: 'utf8', // 指定编码，默认不指定
       flags: 'w', // 指定文件操作模式，默认'w'
       autoClose: true, // 指定是否自动关闭文件，默认true
       start: 0, // 指定从文件起始位置开始写入，默认0
       end: undefined, // 指定从文件结束位置开始写入，默认undefined
     }
     const writeStream = fs.createWriteStream('file.txt');
     ```
   - 同步创建可写流：`fs.createWriteStreamSync(path[, options])`
     ```javascript
     options: {
       encoding: 'utf8', // 指定编码，默认不指定
       flags: 'w', // 指定文件操作模式，默认'w'
       autoClose: true, // 指定是否自动关闭文件，默认true
       start: 0, // 指定从文件起始位置开始写入，默认0
       end: undefined, // 指定从文件结束位置开始写入，默认undefined
     }
     const writeStream = fs.createWriteStreamSync('file.txt');
     ```
           
   - 异步复制文件：`fs.copyFile(src, dest[, flags], callback)`
     ```javascript
     fs.copyFile('source.txt', 'destination.txt', (err) => {
       if (err) throw err;
       console.log('File copied successfully!');
     });
     ```
   - 同步复制文件：`fs.copyFileSync(src, dest[, flags])`
     ```javascript
     try {
       fs.copyFileSync('source.txt', 'destination.txt');
        console.log('File copied successfully!');
     } catch (err) {
        console.error(err);
     }
       ```

   - 异步重命名文件：`fs.rename(oldPath, newPath, callback)`
     ```javascript
     fs.rename('oldfile.txt', 'newfile.txt', (err) => {
       if (err) throw err;
       console.log('File renamed successfully!');
     });
     ```
   - 同步重命名文件：`fs.renameSync(oldPath, newPath)`
     ```javascript
     try {
           fs.renameSync('oldfile.txt', 'newfile.txt');
       console.log('File renamed successfully!');
     } catch (err) {
       console.error(err);
       }
       ```

2. **文件追加**
   - 异步追加数据到文件：`fs.appendFile(path, data[, options], callback)`
     ```javascript
     fs.appendFile('file.txt', '\nAppended text.', (err) => {
       if (err) throw err;
       console.log('Data appended to file!');
     });
     ```
   - 同步追加数据到文件：`fs.appendFileSync(path, data[, options])`
     ```javascript
     try {
       fs.appendFileSync('file.txt', '\nAppended text.');
       console.log('Data appended to file!');
     } catch (err) {
       console.error(err);
     }
     ```

3. **文件删除**
   - 异步删除文件：`fs.unlink(path, callback)`
     ```javascript
     fs.unlink('file.txt', (err) => {
       if (err) throw err;
       console.log('File deleted successfully!');
     });
     ```
   - 同步删除文件：`fs.unlinkSync(path)`
     ```javascript
     try {
       fs.unlinkSync('file.txt');
       console.log('File deleted successfully!');
     } catch (err) {
       console.error(err);
     }
     ```

4. **目录操作**
   - 异步创建目录：`fs.mkdir(path[, options], callback)`
     ```javascript
     options: {
       recursive: true // 递归创建父目录
     }
     fs.mkdir('new-directory', (err) => {
       if (err) throw err;
       console.log('Directory created successfully!');
     });
     ```
   - 同步创建目录：`fs.mkdirSync(path[, options])`
     ```javascript
     options: {
       recursive: true // 递归创建父目录
     }
     try {
       fs.mkdirSync('new-directory');
       console.log('Directory created successfully!');
     } catch (err) {
       console.error(err);
     }
     ```
   - 异步删除目录：`fs.rmdir(path[, options], callback)`
     ```javascript
     options: {
       recursive: true // 递归删除目录及其内容
     }
     fs.rmdir('new-directory', (err) => {
       if (err) throw err;
       console.log('Directory removed successfully!');
     });
     ```
   - 同步删除目录：`fs.rmdirSync(path[, options])`
     ```javascript
     try {
       fs.rmdirSync('new-directory');
       console.log('Directory removed successfully!');
     } catch (err) {
       console.error(err);
     }
     ```
   - 异步读取目录内容：`fs.readdir(path[, options], callback)`
     ```javascript
     fs.readdir('.', (err, files) => {
       if (err) throw err;
       console.log(files);
     });
     ```
   - 同步读取目录内容：`fs.readdirSync(path[, options])`
     ```javascript
     try {
       const files = fs.readdirSync('.');
       console.log(files);
     } catch (err) {
       console.error(err);
     }
     ```
   - 判断文件/目录是否存在 `fs.existsSync(path)`
     ```javascript
     fs.existsSync('directory-name');
     ```

   - 判断目录是否为空 `fs.readdirSync(path).length === 0`
      ```javascript
     fs.readdirSync(path).length === 0;
     ```
         
     

5. **文件重命名**
   - 异步重命名文件或目录：`fs.rename(oldPath, newPath, callback)`
     ```javascript
     fs.rename('old-file.txt', 'new-file.txt', (err) => {
       if (err) throw err;
       console.log('File renamed successfully!');
     });
     ```
   - 同步重命名文件或目录：`fs.renameSync(oldPath, newPath)`
     ```javascript
     try {
       fs.renameSync('old-file.txt', 'new-file.txt');
       console.log('File renamed successfully!');
     } catch (err) {
       console.error(err);
     }
     ```

6. **文件状态**
   - 异步获取文件状态信息：`fs.stat(path, callback)`
     ```javascript
     fs.stat('file.txt', (err, stats) => {
       if (err) throw err;
       console.log(stats);
     });
     ```
   - 同步获取文件状态信息：`fs.statSync(path)`
     ```javascript
     try {
       const stats = fs.statSync('file.txt');
       console.log(stats);
     } catch (err) {
       console.error(err);
     }
     ```

7. **文件监视**
   - 监视文件的变化：`fs.watchFile(filename[, options], listener)`
     ```javascript
     fs.watchFile('file.txt', (curr, prev) => {
       console.log(`The file was modified! ${curr.mtime}`);
     });
     ```
