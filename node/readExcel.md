以下是一个使用 Express.js 和 Node.js 导入 Excel 文件并将其写入数据库的示例代码:

```javascript
const express = require('express');
const app = express();
const multer = require('multer');
const xlsx = require('xlsx');
const mysql = require('mysql');

// 设置 Multer 上传配置
const storage = multer.memoryStorage();
const upload = multer({ storage: storage });

// 连接数据库
const connection = mysql.createConnection({
  host: 'localhost',
  user: 'your_username',
  password: 'your_password',
  database: 'your_database'
});

// 处理 Excel 文件上传
app.post('/upload', upload.single('excel_file'), (req, res) => {
  // 读取 Excel 文件
  const workbook = xlsx.read(req.file.buffer, { type: 'buffer' });
  const sheetName = workbook.SheetNames[0];
  const worksheet = workbook.Sheets[sheetName];
  const data = xlsx.utils.sheet_to_json(worksheet);

  // 将数据写入数据库
  data.forEach(row => {
    const sql = 'INSERT INTO your_table (column1, column2, column3) VALUES (?, ?, ?)';
    connection.query(sql, [row.column1, row.column2, row.column3], (err, result) => {
      if (err) throw err;
    });
  });

  res.send('Excel 文件已成功上传并写入数据库');
});

app.listen(3000, () => {
  console.log('服务器已启动,监听端口 3000');
});
```

这个示例使用了以下库:

- Express.js - 用于创建 Web 服务器
- Multer - 用于处理文件上传
- xlsx - 用于读取 Excel 文件
- mysql - 用于连接和操作 MySQL 数据库

主要步骤如下:

1. 设置 Multer 上传配置,允许通过 POST 请求上传 Excel 文件。
2. 连接到 MySQL 数据库。
3. 在 `/upload` 路由中处理文件上传请求:
   - 读取 Excel 文件内容
   - 遍历数据,并使用 SQL 语句将每一行数据写入数据库
4. 启动服务器,监听端口 3000。
