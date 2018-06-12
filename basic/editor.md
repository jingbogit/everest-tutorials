# Editor

You may use any editor you feel comfortable with. Nevertheless, we strongly recommend **VS Code**.

### installation

[https://code.visualstudio.com/docs/setup/setup-overview](https://code.visualstudio.com/docs/setup/setup-overview)

### Settings

open `File -> Preferences -> settings`

```js
{
  "editor.tabSize": 2,
  "editor.insertSpaces": true,
  "editor.detectIndentation": false,
  "eslint.enable": true,
  "eslint.autoFixOnSave": true,
  "editor.wordWrap": "on",
  "workbench.iconTheme": null,
  "editor.fontFamily": "monospace"
}
```

### Editor config

```editorconfig
root = true

[*]
indent_style = space
indent_size = 2
end_of_line = lf
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true

[*.md]
trim_trailing_whitespace = false
```

As different languages (JS, Go, Python) have its own styles.

It is better to setup your editor to respect the `.editorconfig` file, which is commited in git.
So that it could switch into different settings based on different projects or different type of files.

### recommended plugins

* Docuemnt This
* Eslint
* Jest
* Numbered Bookmarks



