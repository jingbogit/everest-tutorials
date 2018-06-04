# Advanced npm

---

### Private module

If the project is not expected to be used outside our team, it should be published to @altizure private domain. You will need to joint npm @altizure domain to perform this action.

[Publish packages to the private domain](https://docs.npmjs.com/private-modules/intro)

---

### npm scripts

npm supports the "scripts" property of the _package.json_ file. They make it easier to run the commonly used long commands. More scripts can be found from [the official website](https://docs.npmjs.com/misc/scripts).

A sample:

```
  "scripts": {
    "lint": "eslint ./src/",
    "test": "jest --runInBand",
    "release": "rm ./release/* -r && webpack --config webpack.config.release.js",
    "debug": "rm ./build/* -r && webpack --config webpack.config.debug.js",
    "build": "npm run debug",
    "doc": "jsdoc -c ./docs/jsdoc.tui.dev.json -r ./src/",
    "prepublishOnly": "yarn && gulp release && npm version patch",
    "postpublish": "git push origin master",
    "push": "git push bitbucket beta && git push github beta && git push gitlab beta"
  },
```



