# Documentation Guideline

We use [JsDoc3](http://usejsdoc.org/) as the documentation standard. Document your code comprehensively is essential for team work.

---

## installation

* install dependencies
  ```
  yarn add -D jsdoc tui-jsdoc-template
  ```

## Format

* At the beginning of each file specify `@fileoverview`, `@author`, `@copyright`.

  ```js
  /**
  * @fileoverview A kind of sprite that displays text.
  * @author Jingbo Liu <jingbo@connect.ust.hk>
  * @author Shenglai Gao <sgaoae@gmail.com>
  * @copyright Everest Innovation Technology
  */
  ```

* Before each class specify \(`@public` for user-docs, `@protected` / `@private` for dev-docs\), `@async`, `@exports`, `@extends` \(if applicable\), `@param`, `@example`

  ```js
  /**
  * @exports TextTagMarker
  * @public
  * @class
  * @extends {SpriteMarker}
  * @param {object} markerOptions
  * @param {string} markerOptions.textOptions.text - textContent
  * ...
  * 
  * @example <caption> construction </caption>
  *  let textTagMarker = new altizure.TextTagMarker({
  *    // text string
  *    text: 'Altizure'
  *  })
  */
  ```

* Before each member, specify `@public` if accessible to user. Also specify `async`, `@readonly`, `@param`, `@returns`, `@static`, `@memberof` whenever applicable. `@example` generally should be provided for `@public` members/methods.

  ```js
  /**
   * Get the text.
   * @protected
   * @readonly
   * @returns {string}
   * @memberof TextTagMarker
   */
  get text () { return this._text }

  /**
   * Change the text in tag.
   * @public
   * @param {string} str
   * @memberof TextTagMarker
   * 
   * @example <caption> Change text. </caption>
   * textTagMarker.text = 'Altizure is great'
   */
  set text (str) {
  ```

* Use `@private` if the member/method is only used in the class domain; use `@protected` if used outside the class, but not exposed to sdk users. Those two will not appear in `user-docs`, but will be in `dev-docs`. `user-docs` only has `@public` memeber/methods.

  ```js
  /**
   * Creates the text texture and call super setter texture to set it
   * @private
   * @memberof TextTagMarker
   */
  _createTextTexture () {...}
  ```

* Refer to [JSDoc standard](http://usejsdoc.org/) for the usage of tags.

## Tools

* Document This \(0.6.0\) for VS Code. It provides simple templates. But usually incomplete. Requires mannually add other necessary tags.

* Let us know if there are better tools.

---

## Developer documentation

This documents the source code. It is for developer-selves who work on the source.

#### generation

```
yarn
node_modules/.bin/jsdoc -c ./docs/jsdoc.tui.dev.json -r ./src/
```

#### config file

Generate the documentation website under `./docs/dev_docs/web` , which is specified in the config file.

Put the config file under `./docs/` . e.g.

* ```
  {
    "tags": {
      "allowUnknownTags": true
    },
    "plugins": ["plugins/markdown"],
    "templates": {
        "name": "Altizure Engine",
        "footerText": "Everest Innovation Technology",
        "logo": {
          "url": "https://cdn-china.altizure.cn/public/images/apple-touch-icon-180.png",
          "width": "20px",
          "height": "20px",
          "link": "https://www.altizure.com"
        }
    },
    "opts": {
      "access": "all",
      "package": "./package.json",
      "destination": "./docs/dev_docs/web",
      "template": "./node_modules/tui-jsdoc-template"
    }
  }
  ```

---

### learning material

[**learn-jsdoc**](https://github.com/dwyl/learn-jsdoc)

