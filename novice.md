# Enhanced skills

This chapter introduces more advanced development tools which are used in our workflow.
At the end of this stage,  you should be capable of managing a git repo independently.

---

The creation of a git repo:

1. You are assigned to implement a feature. e.g. a sorting library. After discussing with your mentor, the repo is named as `altizure.sort` . Create an empty project with this name under **altizure** bitbucket account. **Your personal account** will be granted with **write** permission.
2. Fork this project under your own account. Clone it down.
3. Write a readme.md file to describe the project.
4. Initialize the project as a npm module using `npm init`.
5. Create these folders under `./altizure.sort/`
   1. `src` : source files
   2. `release` : the publishing folder for npm
   3. `docs` : documentation
   4. `test` : test files
   5. `build` \[optional\]: temporary build files for development
   6. `example` \[optional\]: html files that uses this feature as demos
6. Write these configuration files \(if needed\) under `./altizure.sort` :
   1. `.gitignore` : git ignore file
   2. `.npmignore` : npm ignore file
   3. `.babelrc` : babel config
   4. `.eslint.json` : eslint config
   5. `.eslintignore` : eslint ignore file
   6. `webpack.config.js` : webpack config
   7. `CHANGELOG.md` : change log for project's previous versions
   8. `gitlab-ci.yml` : CI for gitlab
7. Implement, test, and document.
8. Webpack your output to `./release/` folder.
9. Update  change log, publish the module.
