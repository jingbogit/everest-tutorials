# ESLint

eslint is a tool to check your code style.

### installation

```
yarn add -D babel-eslint eslint eslint-config-standard eslint-plugin-import eslint-plugin-node eslint-plugin-promise eslint-plugin-standard
```

### configuration

Create a file named ".eslintrc.json" under the repo. Usually this file is already provided by your mentor.

```
{
  "extends": ["standard"],
  "parser": "babel-eslint",
  "globals": {
  },
  "env": {
    "browser": true,
    "commonjs": true,
    "es6": true
  },
  "rules": {
    "camelcase": "warn",
    "linebreak-style": [
        "error",
        "unix"
    ]
  }
}
```

### ignore

create a file named ".eslintignore" under the repo, to ignore center files being linted. e.g.

```
# Ignore built files
build/*
docs/
examples/
release/
test/
```



