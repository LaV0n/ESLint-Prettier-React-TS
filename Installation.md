#Installation process with `yarn`

1. First step - install ESLint:
```
yarn add -D eslint
```
2. Create a config file:
```
yarn run eslint --init
```
Answers about our project:
```
- To check syntax and find problems
- JavaScript modules (import/export)
- React
- ? Does your project use TypeScript? ‣ Yes
- Browser
- JSON
- ? Would you like to install them now with npm? ‣ No
```
3. Install dependencies, TypeScript plugins and  Prettier:
```
yarn add -D eslint-plugin-react@latest @typescript-eslint/eslint-plugin@latest @typescript-eslint/parser@latest eslint-plugin-import @typescript-eslint/parser eslint-import-resolver-typescript prettier eslint-config-prettier eslint-plugin-prettier eslint-plugin-react-hooks
```
4. Create file `.prettierrc`
My basic configuration for prettierrc file is:
```
{
"semi": false,
"tabWidth": 3,
"printWidth": 100,
"bracketSpacing": true,
"arrowParens": "avoid",
"singleQuote": true,
"trailingComma": "es5",
"jsxBracketSameLine": false
}
```
5. Modify eslintrc.json file:
```
"extends": [
"eslint:recommended",
"plugin:react/recommended",
"plugin:@typescript-eslint/recommended",
"plugin:prettier/recommended" //Add this line
]
```
and add plugin update:
```
"plugins": ["react", "react-hooks", "@typescript-eslint", "prettier"],
```
6. Modify package.json:
```
{
...
"scripts": {
...
"lint": "eslint src/**/*.{js,jsx,ts,tsx,json}",
"lint:fix": "eslint --fix 'src/**/*.{js,jsx,ts,tsx,json}'",
"format": "prettier --write 'src/**/*.{js,jsx,ts,tsx,css,md,json}' --config ./.prettierrc"
},
...
}
```
##END.
