# @lockerstock/react-tsconfig

A TypeScript config basis. Includes, tsconfig, tslint, tslint.commit, and prettier configurations.

## Installation

```
npm install --save-dev @lockerstock/react-tsconfig
```

```
yarn add @lockerstock/react-tsconfig --dev
```

_This tool has peer dependencies and will download them as needed._

## Usage

Reference it in `package.json` using the `prettier` property:

```json
{
	"name": "my-projects-name",
	"prettier": "@lockerstock/react-tsconfig/.prettierrc.json",
	"devDependencies": {
		"@lockerstock/react-tsconfig": "^1.0.0",
		"husky": "^4.3.0",
		"lint-staged": "^10.3.0",
		"prettier": "^2.1.1",
		"tslint": "^6.1.3",
	},
	"scripts": {
		"lint": "tslint --project tsconfig.json -c tslint.commit.json --fix",
		"pregit": "git add *",
		"git": "git commit",
		"postgit": "git push"
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
	"extends": "@lockerstock/react-tsconfig/tsconfig.json",
	"compilerOptions": {
		"rootDir": "./src",
		"baseUrl": "./src"
	},
	"include": ["src"]
}
```

Extend the config in `tslint.json`

```json
{
	"extends": "@alehechlockerstockka/react-tsconfig/tslint.json"
}
```

Extend the config in `tslint.commit.json`

```json
{
	"extends": ["@lockerstock/react-tsconfig/tslint.commit.json"]
}
```

If you're using [VS Code](https://code.visualstudio.com/), turn on the `formatOnSave` feature by adding `.vscode/settings.json`:

```json
{
	"editor.formatOnSave": true
}
```
