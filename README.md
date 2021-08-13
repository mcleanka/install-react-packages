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
		"@babel/preset-env",
		{
			"targets": {
				"node": "10"
			}
		}
	],
	"plugins": ["@babel/plugin-proposal-class-properties"]
}
```
