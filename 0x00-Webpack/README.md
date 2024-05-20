# 0x00. Webpack

Welcome to my **0x00. Webpack** project! In this task, I'll dive into the world of Webpack, a powerful tool for bundling JavaScript applications. By the end of this project, I'll be able to set up and configure Webpack for my projects, making my development process smoother and more efficient.

## Resources

### Read or Watch:
- [Webpack documentation](https://webpack.js.org/concepts/)
- [Webpack beginner guide](https://webpack.js.org/guides/getting-started/)
- [npm-package.json](https://docs.npmjs.com/files/package.json)

## Learning Objectives

By the end of this project, I should be able to explain the following concepts to anyone, without the help of Google:

- How to set up Webpack for a basic project
- Entry points, output, and loaders
- How to add plugins
- How to split your code into chunks
- How to set up a dev server

![Webpack GIF](https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExMmFtMHBmZ2VraXNwdWV6ZWIydjJhbWo3eHZpYmp0Z3V3MHNlMWhubiZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/KiFerKr4AbbDW/giphy.gif)

## Definitions and Command Explanations

### How to Set Up Webpack for a Basic Project

Setting up Webpack involves installing Webpack and Webpack CLI as development dependencies and creating a configuration file.

1. **Install Webpack and Webpack CLI**:
    ```bash
    npm install --save-dev webpack webpack-cli
    ```

2. **Create `webpack.config.js`**:
    ```javascript
    const path = require('path');

    module.exports = {
      entry: './src/index.js',
      output: {
        filename: 'bundle.js',
        path: path.resolve(__dirname, 'dist'),
      },
    };
    ```

### Entry Points, Output, and Loaders

- **Entry Points**: The entry point is the file where Webpack starts building the dependency graph. In the config file above, the entry point is `./src/index.js`.

- **Output**: The output property specifies the location and name of the bundled file. Here, Webpack will output `bundle.js` in the `dist` directory.

- **Loaders**: Loaders allow Webpack to process files other than JavaScript (e.g., CSS, images). Loaders are defined in the configuration file under the `module` property.

    Example for handling CSS files:
    ```javascript
    module: {
      rules: [
        {
          test: /\.css$/,
          use: ['style-loader', 'css-loader'],
        },
      ],
    },
    ```

### How to Add Plugins

Plugins are used to perform a wider range of tasks like bundle optimization, asset management, and injection of environment variables. They are added to the `plugins` array in the configuration file.

Example of adding the `HtmlWebpackPlugin`:
```javascript
const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
  // ...other config
  plugins: [
    new HtmlWebpackPlugin({
      template: './src/index.html',
    }),
  ],
};
```

### How to Split Your Code into Chunks

Code splitting can improve the performance of your application by splitting the bundle into smaller chunks which can be loaded on demand.

Example configuration for code splitting:
```javascript
module.exports = {
  // ...other config
  optimization: {
    splitChunks: {
      chunks: 'all',
    },
  },
};
```

### How to Set Up a Dev Server

Webpack Dev Server provides a development server that live reloads your application as you make changes.

1. **Install Webpack Dev Server**:
    ```bash
    npm install --save-dev webpack-dev-server
    ```

2. **Add devServer property in `webpack.config.js`**:
    ```javascript
    module.exports = {
      // ...other config
      devServer: {
        contentBase: './dist',
        open: true,
      },
    };
    ```

3. **Add a start script in `package.json`**:
    ```json
    "scripts": {
      "start": "webpack serve --open"
    }
    ```

With these configurations, I can run `npm start` to fire up the development server and start developing with live reloading.

---

That's it! I've set up Webpack for a basic project and learned how to enhance my configuration with entry points, output, loaders, plugins, code splitting, and a dev server. Time to keep experimenting and mastering Webpack to boost my development workflow!

Happy coding! 🚀
