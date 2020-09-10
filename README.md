# @lockerstock/react-ts-config

A TypeScript config basis. Includes, tsconfig, tslint, tslint.commit, and prettier configurations.

## Installation

```
npm install --save-dev @lockerstock/react-ts-config
```

```
yarn add @lockerstock/react-ts-config --dev
```

_This tool has peer dependencies and will download them as needed._

## Usage

Reference it in `package.json` using the `prettier` property:

```json
{
	"name": "my-projects-name",
	"prettier": "@lockerstock/react-ts-config",
	"devDependencies": {
		"@lockerstock/react-ts-config": "^1.0.0",
		"husky": "^4.3.0",
		"lint-staged": "^10.3.0",
		"prettier": "^2.1.1"
	},
	"scripts": {
		"lint": "tslint --project tsconfig.json -c tslint.commit.json --fix"
	},
	"lint-staged": {
		"src/**/*.{ts,tsx}": ["yarn lint", "prettier --write"]
	},
	"husky": {
		"hooks": {
			"pre-commit": "lint-staged"
		}
	}
}
```

Extend the config in `tsconfig.json`

```json
{
	"extends": "@lockerstock/react-ts-config/tslint.json"
}
```

Extend the config in `tslint.json`

```json
{
	"extends": "@alehechlockerstockka/react-ts-config/tslint.json"
}
```

Extend the config in `tslint.commit.json`

```json
{
	"extends": ["@lockerstock/react-ts-config/tslint.commit.json"]
}
```

If you're using [VS Code](https://code.visualstudio.com/), turn on the `formatOnSave` feature by adding `.vscode/settings.json`:

```json
{
	"editor.formatOnSave": true
}
```
