Node.js 中 `http` 模块的常用方法

1. **创建 HTTP 服务器**
   - `http.createServer([options][, requestListener])`: 创建一个 HTTP 服务器实例。
   ```javascript
   const http = require('http');
   const server = http.createServer((req, res) => {
     res.statusCode = 200;
     res.setHeader('Content-Type', 'text/plain');
     res.end('Hello, World!\n');
   });
   server.listen(3000, () => {
     console.log('Server running at http://localhost:3000/');
   });
   ```

2. **发送 HTTP 请求**
   - `http.request(options[, callback])`: 发起一个 HTTP 请求。
   ```javascript
   const http = require('http');
   const options = {
     hostname: 'www.example.com',
     port: 80,
     path: '/index.html',
     method: 'GET'
   };

   const req = http.request(options, (res) => {
     console.log(`Status Code: ${res.statusCode}`);
     res.on('data', (chunk) => {
       console.log(`Body: ${chunk}`);
     });

     res.on('end', () => {
       console.log('No more data in response.');
     });
   });

   req.on('error', (e) => {
     console.error(`problem with request: ${e.message}`);
   });

   req.end();
   ```

3. **发送 HTTP 响应**
   - `http.ServerResponse.writeHead(statusCode[, statusMessage][, headers])`: 向请求发送响应头。
   - `http.ServerResponse.write(chunk[, encoding][, callback])`: 向请求发送响应主体。
   - `http.ServerResponse.end([data][, encoding][, callback])`: 完成并发送响应。
   ```javascript
   const http = require('http');
   const server = http.createServer((req, res) => {
     res.writeHead(200, { 'Content-Type': 'text/plain' });
     res.write('Hello, World!');
     res.end();
   });
   server.listen(3000, () => {
     console.log('Server running at http://localhost:3000/');
   });
   ```

4. **获取 HTTP 请求信息**
   - `http.IncomingMessage.url`: 获取请求的 URL 信息。
   - `http.IncomingMessage.method`: 获取请求方法。
   - `http.IncomingMessage.headers`: 获取请求头。
   ```javascript
   const http = require('http');

   const server = http.createServer((req, res) => {
     console.log(`Request URL: ${req.url}`);
     console.log(`Request Method: ${req.method}`);
     console.log(`Request Headers: ${JSON.stringify(req.headers)}`);

     res.statusCode = 200;
     res.setHeader('Content-Type', 'text/plain');
     res.end('Hello, World!\n');
   });

   server.listen(3000, () => {
     console.log('Server running at http://localhost:3000/');
   });
   ```

5. **处理 HTTP 错误**
   - `http.ServerResponse.statusCode`: 设置响应状态码。
   - `http.ServerResponse.statusMessage`: 设置响应状态消息。
   ```javascript
   const http = require('http');
   const server = http.createServer((req, res) => {
     if (req.url === '/error') {
       res.statusCode = 404;
       res.statusMessage = 'Not Found';
       res.end('Error 404: Page not found');
     } else {
       res.statusCode = 200;
       res.setHeader('Content-Type', 'text/plain');
       res.end('Hello, World!');
     }
   });
   server.listen(3000, () => {
     console.log('Server running at http://localhost:3000/');
   });
   ```
 
