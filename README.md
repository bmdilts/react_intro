# # Introduction to React

## Text editor set up for Atom
In this tutorial I will be using atom as my text-editor of choice you can use whatever text-editor you would like but for those of you who like to follow along exactly as I do use atom. Below are all the packages you will want to install with atom. Basically what we are doing is adding linters and different packages that make atom easier and better to use.
Here is the [list](https://medium.com/productivity-freak/my-atom-editor-setup-for-js-react-9726cd69ad20
 "Atom Packages") of what each of these packages are and what they do.

### For Mac & windows Run in Terminal/Command Prompt:
```
apm install atom-beautify prettier-atom atom-spotify2 atom-transpose case-keep-replace change-case copy-path duplicate-line-or-selection editorconfig file-icons git-plus highlight-selected local-history project-manager related set-syntax atom-reveal-file-in-finder sort-lines sublime-style-column-selection tab-foldername-index sync-settings toggle-quotes atom-wrap-in-tag atom-ternjs autoclose-html autocomplete-modules color-picker docblockr emmet emmet-jsx-css-modules es6-javascript js-hyperclick hyperclick pigments linter-eslint tree-view-copy-relative-path lodash-snippets language-babel react-es7-snippets atom-jest-snippets one-dark-ui dracula-theme
```

### For Windows: your life may have just gotten harder :/
If you have gotten an error that says apm or atom are not recognized as commands. You have to install chocolately and reinstall atom using [chocolately](https://chocolatey.org/install "Install Chocolately") then rerun the commands above. Then for each package that fails to install you will have to install manually :/ Sorry!

## Getting Started
So before we get started this tutorial assumes you already have [node.js](https://nodejs.org/en/ "Install Node") installed if not you will want to install that now.

### Creating a New React Project
You will want to install [create-react-app](https://facebook.github.io/react/docs/installation.html "React Installation Documentation") which will create a react project for you and come already prepared with babel, es6, and webpack straight out of the box which will make it easier for production use

```
npm install -g create-react-app
create-react-app my-first-react-app

cd my-first-react-app
npm start
```

### Adding React to an Existing Project
We will need to add 3 things to our project in order to get up and running for adding react to an existing project.

- A package manager, such as Yarn or [npm](https://nodejs.org/en/ "Install Node"). It lets you take advantage of a vast ecosystem of third-party packages, and easily install or update them.
- A bundler, such as [webpack](https://webpack.js.org/guides/installation/ "Install Webpack") or Browserify. It lets you write modular code and bundle it together into small packages to optimize load time.

```
npm install --save-dev webpack
```
package.json
```javascript
"scripts": {
    "start": "webpack --config webpack.config.js"
}
```

webkit.config.js
```javascript
var path = require('path');

module.exports = {
  entry: './src/index.js',
  output: {
    filename: 'bundle.js',
    path: path.resolve(__dirname, 'dist')
  }
};
```

- A compiler such as [Babel]( "Install Babel"). It lets you write modern JavaScript code that still works in older browsers.
```
npm install babel-core babel-loader babel-preset-es2015 babel-preset-react --save
```
package.json
```javascript
  "babel": {
    "presets": [
      "es2015",
      "react"
    ]
  }
 ```
 
Next we will want to install React, again we will be using npm as our package manager throughout this tutorial
```
npm init -y
npm install --save react react-dom
```

npm init is going to allow us to build a package.json file which will keep track of our dependencies. running npm init on its own will walk you through a bunch of steps and ask you to fill out as best you can a bunch of information about your application. Adding the -y at the end of this command will let our package manager to guess as best as it can what each field should be named

## Components
In React basic components can be written in regular javascript. 

```

function Welcome(props){
  return ( <h1>Welcome {props.name}!</h1> )
}

```

They can be rendered to the DOM by calling the render() method.

```

ReactDom.render(
  <Welcome name="James"/>,
  document.getElementById('root')
);

```

Components can accessed once their function is written components should be written with capital letters "Welcome" 
Then they can be written like normal html elements and that will access the Welcome function. 

Props work by passing attributes from an html component element. By calling an attribute called name and setting it equal to James

I can now access props.name to return whatever name was passed to that component.
