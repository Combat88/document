详细介绍 Webpack 中的 Loaders:
1. **什么是 Loader?**
   - Loader 是 Webpack 的核心功能之一,用于对模块的源代码进行转换。
   - 当 Webpack 遇到不同类型的文件(如 JavaScript、CSS、图像等)时,它会使用相应的 Loader 来处理这些文件。

2. **常见的 Loader**
   - `babel-loader`: 用于将 ES6+ 代码转换为浏览器兼容的 JavaScript 代码。
   - `css-loader`: 功能：用于解析 CSS 文件,并返回 CSS 模块。
   - `style-loader`: 用于将 CSS 注入到 HTML 中。
   - `file-loader`: 用于处理静态资源文件(如图片、字体等)。
   - `url-loader`: 类似于 `file-loader`,但可以将小文件转换为 base64 编码,减少 HTTP 请求。
   - `sass-loader`: 用于编译 Sass/SCSS 文件为 CSS。
   - `less-loader`: 用于编译 Less 文件为 CSS。
   - `ts-loader`: 用于将 TypeScript 文件转换为 JavaScript。

1. **Loader 的使用**
   - 在 Webpack 配置文件的 `module.rules` 中定义 Loader:
     ``` javascript
     {
       test: /\.js$/,
       exclude: /node_modules/,
       use: {
         loader: 'babel-loader',
         options: {
           presets: ['@babel/preset-env']
         }
       }
     },
     {
       test: /\.css$/,
       use: ['style-loader', 'css-loader']
     }
     ```
   - `test` 属性用于匹配文件,`use` 属性指定要使用的 Loader。
   - Loader 可以链式使用,从右到左的顺序执行。

2. **自定义 Loader**
   - 创建方法
     - 自定义 Loader 是一个 Node.js 模块,需要导出一个函数。
     - 这个函数接收源代码作为参数,并返回转换后的代码。
   - 示例:自定义 Markdown Loader
     - 首先,创建一个 Loader 文件,例如 markdown-loader.js
     - 在这个 Loader 中,我们使用 marked 库将 Markdown 源代码转换为 HTML。然后我们将 HTML 字符串封装成一个 CommonJS 模块,以便在 Webpack 中使用  
     - 在 Webpack 配置文件中,添加对自定义 Loader 的引用:
        ``` javascript
        {
         test: /\.md$/,
         use: [{ 
                 loader: path.resolve(__dirname, 'markdown-loader.js') 
              }]
         }
        ```
     - 在这个配置中,我们告诉 Webpack 对 .md 后缀的文件使用我们自定义的 markdown-loader.js Loader。

        ``` javascript 
        const marked = require('marked');
        module.exports = function(source) {
            const html = marked(source);
            return `module.exports = ${JSON.stringify(html)};`;
        };
        ```