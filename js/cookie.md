下面详细介绍 Cookie 的相关配置以及示例代码:
1. **设置 Cookie**:
   - 设置一个名为 "username" 的 Cookie,值为 "John Doe"
   - Cookie 的有效期为 1 小时,并且可以在站点的任意路径下访问
```javascript
document.cookie = "username=John Doe; expires=" + new Date(Date.now() +1000*60*60*24*365).toUTCString() + "; path=/";
```
2. **设置 Secure 和 HttpOnly Cookie**:
   - Secure: 
     - 设置 Cookie 只能在 HTTPS 协议下访问,
       - true: 表示 Cookie 只能通过 HTTPS 协议访问,
       - false: 表示 Cookie 可以在 HTTP 和 HTTPS 协议下访问
   - HttpOnly:
     -  设置 Cookie 只能通过 HTTP 协议访问,不能被 JavaScript 访问
```javascript
document.cookie = "session_id=abcd1234; expires=" + new Date(Date.now() + 86400000).toUTCString() + "; path=/; secure; HttpOnly";
```


3. **设置 SameSite 属性**:
    代码分别设置了 SameSite=Strict 和 SameSite=Lax 的 Cookie。Strict 模式下,浏览器只会在同站请求中发送 Cookie,Lax 模式下,浏览器会在某些跨站请求中发送 Cookie。
    - SameSite:
      - Strict: 
        - 浏览器只会在同站请求中发送 Cookie,
        - 设置 Cookie 时,必须指定 SameSite=Strict
      - Lax:
        - 浏览器会在某些跨站请求中发送 Cookie,
        - 设置 Cookie 时,可以不指定 SameSite 属性,默认值为 SameSite=Lax
      - None:
        - 浏览器会在所有跨站请求中发送 Cookie,
        - 设置 Cookie 时,必须指定 SameSite=None
  
```javascript
document.cookie = "csrf_token=abcd1234; expires=" + new Date(Date.now() + 86400000).toUTCString() + "; path=/; SameSite=Strict";

// 设置一个 SameSite=Lax 的 Cookie
document.cookie = "session_id=efgh5678; expires=" + new Date(Date.now() + 86400000).toUTCString() + "; path=/; SameSite=Lax";
```


4. **读取 Cookie**:
   
```javascript
// 读取 Cookie
function getCookie(name) {
  const cookies = document.cookie.split(";");
  for (let i = 0; i < cookies.length; i++) {
    const cookie = cookies[i].trim();
    if (cookie.startsWith(name + "=")) {
      return cookie.substring(name.length + 1);
    }
  }
  return "";
}

const username = getCookie("username");
const sessionId = getCookie("session_id");
```