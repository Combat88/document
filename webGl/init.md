### WebGL 环境设置

设置 WebGL 环境的步骤包括创建 HTML 页面、初始化 WebGL 上下文以及配置基本的渲染环境。以下是详细的步骤：

#### 1. 创建 HTML 页面

首先，创建一个基本的 HTML 页面结构：

```html
<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>WebGL 示例</title>
    <style>
        canvas {
            width: 100%;
            height: 100%;
            display: block;
        }
    </style>
</head>
<body>
    <canvas id="webgl-canvas"></canvas>
    <script src="script.js"></script>
</body>
</html>
```

#### 2. 初始化 WebGL 上下文

在 `script.js` 文件中，添加以下代码来初始化 WebGL 上下文：

```javascript
// 获取画布元素
const canvas = document.getElementById('webgl-canvas');

// 初始化 WebGL 上下文
const gl = canvas.getContext('webgl');

if (!gl) {
    console.error('无法初始化 WebGL，上下文可能不支持。');
}
```

#### 3. 设置画布大小

确保 WebGL 画布的大小与窗口大小一致：

```javascript
canvas.width = window.innerWidth;
canvas.height = window.innerHeight;

// 设定视口
gl.viewport(0, 0, canvas.width, canvas.height);
```

#### 4. 清除颜色和深度缓冲区

在每一帧开始时，清除画布：

```javascript
// 设置清除颜色
gl.clearColor(0.0, 0.0, 0.0, 1.0); // 黑色背景
gl.clear(gl.COLOR_BUFFER_BIT | gl.DEPTH_BUFFER_BIT);
```

#### 5. 处理窗口大小变化

添加事件监听器，以便在窗口大小变化时调整画布大小：

```javascript
window.addEventListener('resize', () => {
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
    gl.viewport(0, 0, canvas.width, canvas.height);
});
```

#### 6. 运行基本的渲染循环

创建一个简单的渲染循环，使 WebGL 能够持续绘制：

```javascript
function render() {
    // 清除画布
    gl.clear(gl.COLOR_BUFFER_BIT | gl.DEPTH_BUFFER_BIT);

    // 这里添加绘制代码...

    // 继续请求下一帧
    requestAnimationFrame(render);
}

// 启动渲染循环
render();
```

### 完整示例

将上述代码整合在一起，形成一个简单的 WebGL 环境设置示例：

```html
<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>WebGL 示例</title>
    <style>
        canvas {
            width: 100%;
            height: 100%;
            display: block;
        }
    </style>
</head>
<body>
    <canvas id="webgl-canvas"></canvas>
    <script>
        const canvas = document.getElementById('webgl-canvas');
        const gl = canvas.getContext('webgl');

        if (!gl) {
            console.error('无法初始化 WebGL，上下文可能不支持。');
        }

        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;
        gl.viewport(0, 0, canvas.width, canvas.height);
        gl.clearColor(0.0, 0.0, 0.0, 1.0);

        window.addEventListener('resize', () => {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
            gl.viewport(0, 0, canvas.width, canvas.height);
        });

        function render() {
            gl.clear(gl.COLOR_BUFFER_BIT | gl.DEPTH_BUFFER_BIT);
            requestAnimationFrame(render);
        }

        render();
    </script>
</body>
</html>
```
