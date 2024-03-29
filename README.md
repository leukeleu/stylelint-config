# Leukeleu Stylelint configuration

## Installing this package

If you already had Stylelint installed in your project you can delete this first with `npm uninstall stylelint`. Also look for plugins to uninstall like `stylelint-config-standard` or `stylelint-config-prettier`

Then install this package as a development dependency `npm i -D @leukeleu/stylelint-config`.

## Adding the config

In your `stylelint.config.js` add:

```js
module.exports = {
  extends: '@leukeleu/stylelint-config',
}
```

## Add script commands to package.json

For example, to lint all .pcss files inside the /pages/styles/ directory:

```
"scripts": {
  "lint:stylelint": "stylelint './pages/styles/*.pcss'",
  "lintfix:stylelint": "npm run lint:stylelint -- --fix"
}
```

## Adding an ignore file

If you don't want to lint certain files you can create a file named .stylelintignore in the root and add ignored file(types) to it.

## Running the check

You can now run stylelint check by calling `npm run lint:stylelint` or auto-fix by calling `npm run lintfix:stylelint`

## Extending/ changing config

This is not recommended as the goal is have similar settings in all projects, but if for some reason you need to add or change the config it's possible. The config is in JavaScript, so you can make use of the spread operator to extend the config.

```js
module.exports = {
  extends: '@leukeleu/stylelint-config',
  rules: {
    'selector-class-pattern': null,
  },
}
```

## Contributing

To learn how to local test and publish this package, please refer to the instructions in the `CONTRIBUTORS.md` file.
