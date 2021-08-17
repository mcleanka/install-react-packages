# Creating react app start kit without using npm
- Create package.json file
```bash
npm init -y
```
- install node modules
```bash
npm i webpack webpack-cli --save-dev
```
- install babel modules
```bash
npm i @babel/core babel-loader @babel/preset-env @babel/preset-react --save-dev
npm install @babel/plugin-proposal-class-properties
```
- install react modules
```bash
npm i react react-dom --save-dev
```

- Include styling module [material-ui] (optional)
```bash
npm install @material-ui/core 
npm install @material-ui/icons
```
- install react routering module
```bash
npm install react-router-dom
```
- Create babel.config.json file paste
```json
{
	"presets": [
		"@babel/preset-react",
		"@babel/preset-env"
		/* {
			"targets": {
				"node": "10"
			}
		} */
	],
	"plugins": ["@babel/plugin-proposal-class-properties"]
}

```
- Create webpack.config.js file paste
```js
const path = require("path");
const webpack = require("webpack");

module.exports = {
	entry: "./src/index.js",
	output: {
		path: path.resolve(__dirname, "./static/frontend"),
		filename: "[name].js",
	},
	module: {
		rules: [
			{
				test: /\.js$/,
				exclude: /node_modules/,
				use: {
					loader: "babel-loader",
				},
			},
		],
	},
	optimization: {
		minimize: true,
	},
	plugins: [
		new webpack.DefinePlugin({
			"process.env": {
				// This has effect on the react lib size
				NODE_ENV: JSON.stringify("development"),
			},
		}),
	],
};
```
- Copy paste below code in package.json file under "scripts"
```json
"scripts": {
	"dev": "webpack --mode development --watch",
	"build": "webpack --mode production"
},
```
- Create 
```
/path/to/my-app/src/index.js
```
- Run
```bash
npm run dev
```
