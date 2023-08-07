# Creating a React App from Scratch

Welcome to the "Creating a React App from Scratch" repository! This repository serves as a guide and reference for building a basic React application from the ground up, without relying on create-react-app or other scaffolding tools. By following this guide, you'll gain a deeper understanding of how React applications are structured and how various tools like Babel and Webpack work together to create a functional application.

## Prerequisites

Before you begin, make sure you have the following installed on your machine:

- Node.js and npm (Node Package Manager)
- A code editor of your choice (e.g., Visual Studio Code, Sublime Text)

## Getting Started

To create a React app from scratch, follow these steps:

1. **Setup Project Directory:**

   Create a new project directory and navigate to it in your terminal.

   ```sh
   mkdir react-app-from-scratch
   cd react-app-from-scratch
   ```

2. **Initialize npm:**

   Initialize npm in your project directory to manage dependencies.

   ```sh
   npm init -y
   ```

3. **Install Dependencies:**

   Install the necessary dependencies for your React app:

   - React and React DOM for building UI components.
   - Babel for transpiling JSX and modern JavaScript.
   - Webpack for bundling your application.
   - webpack-dev-server for development server with hot-reloading.

   ```sh
   npm install react react-dom
   npm install --save-dev @babel/core @babel/preset-react babel-loader webpack webpack-cli webpack-dev-server
   ```

4. **Create Files:**

   Create the following files in your project directory:

   - `index.html`: Your main HTML file.
   - `index.js`: Entry point for your JavaScript.
   - `App.js`: Your main React component.

5. **Configure Babel:**

   Create a `.babelrc` file in your project directory and configure Babel to transpile JSX and modern JavaScript:

   ```json
   {
     "presets": ["@babel/preset-react"]
   }
   ```

6. **Configure Webpack:**

   Create a `webpack.config.js` file in your project directory and configure Webpack:

   ```javascript
   const path = require('path');

   module.exports = {
     entry: './index.js',
     output: {
       filename: 'bundle.js',
       path: path.resolve(__dirname, 'dist'),
     },
     module: {
       rules: [
         {
           test: /\.js$/,
           exclude: /node_modules/,
           use: {
             loader: 'babel-loader',
           },
         },
       ],
     },
     devServer: {
       contentBase: './dist',
     },
   };
   ```

7. **Build Your App:**

   In `index.js`, import React and ReactDOM, and render your main component in the root HTML element:

   ```javascript
   import React from 'react';
   import ReactDOM from 'react-dom';
   import App from './App';

   ReactDOM.render(<App />, document.getElementById('root'));
   ```

8. **Create Your Main Component:**

   In `App.js`, create your main React component:

   ```javascript
   import React from 'react';

   function App() {
     return <h1>Hello, React App!</h1>;
   }

   export default App;
   ```

9. **Run Development Server:**

   Start the development server using webpack-dev-server:

   ```sh
   npx webpack serve
   ```

   Your app should now be accessible at `http://localhost:8080`.

## Next Steps

Congratulations! You've successfully created a React app from scratch. This is just the beginning. From here, you can explore and expand your app by adding more components, setting up routing, integrating with APIs, and styling your app using CSS or other libraries like styled-components.

Happy coding! 🚀
