# npm

The default package manager for nodejs.

---

# yarn

yarn fixed a few issues of npm, so we use it more often.

### installation

[install yarn globally](https://yarnpkg.com/en/docs/install) \(only for the first time using yarn\)

### install dependencies

The repository contains a \`yarn.lock\` file. It keeps a list of dependencies . To install these dependencies, simply run

```
yarn
```

### add new dependency

```
yarn add <package-name>@1.2.3
```

Do not add new dependencies without your mentor's approval.

---

### node\_modules

All dependencies will be installed under `.\node_modules\`. Very occasionally, npm and yarn will have mysterious bug that they cannot correctly install the dependencies. By deleting this folder, and run yarn again to re-generate this folder and its content, may fix the problem.


