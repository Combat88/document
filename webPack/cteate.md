好的,让我们来详细介绍一下 Webpack 的安装和基本配置。

1. **安装 Webpack**

   首先,需要在你的项目中安装 Webpack 及其相关依赖包。可以使用 npm 或 yarn 进行安装:

   ``` 
   # 使用 npm
   npm install --save-dev webpack webpack-cli

   # 使用 yarn
   yarn add --dev webpack webpack-cli
   ```

   上述命令会将 Webpack 及其命令行工具 `webpack-cli` 安装为项目的开发依赖。

2. **创建 Webpack 配置文件**

   Webpack 的行为是通过配置文件 `webpack.config.js` 进行定义的。在项目根目录下创建此文件,并添加以下基本配置:

   ```javascript
   // webpack.config.js
   module.exports = {
     entry: './src/index.js',
     output: {
       filename: 'bundle.js',
       path: `${__dirname}/dist`
     }
   };
   ```

   - `entry`: 指定 Webpack 构建的入口点,通常是你的应用程序的主 JavaScript 文件。
   - `output`: 配置 Webpack 输出的文件名和目录。在这个例子中,输出文件名为 `bundle.js`，输出目录为 `dist` 文件夹。

3. **运行 Webpack**

   现在可以使用 Webpack 命令行工具来构建项目:

   ```
   # 使用 npm
   npx webpack

   # 使用 yarn
   yarn run webpack
   ```

   这将会根据你的 `webpack.config.js` 文件中的配置,将你的应用程序打包成一个 `bundle.js` 文件,并输出到 `dist` 目录。

4. **添加 development 和 production 模式**

   Webpack 支持两种主要的环境模式: `development` 和 `production`。你可以根据需要进行配置:

   ```javascript
   // webpack.config.js
   module.exports = (env, argv) => {
     const isProduction = argv.mode === 'production';
     return {
       mode: isProduction ? 'production' : 'development',
       entry: './src/index.js',
       output: {
         filename: 'bundle.js',
         path: `${__dirname}/dist`
       }
     };
   };
   ```

   现在你可以使用不同的模式运行 Webpack:

   ```
   # 开发模式
   npx webpack --mode development

   # 生产模式
   npx webpack --mode production
   ```