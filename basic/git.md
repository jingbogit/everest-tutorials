# Git {#git-repository}

Please watch [this video](https://www.youtube.com/watch?v=HVsySz-h9r4) if you after not familiar with the command line git. Lacking knowledge of git will lead to nightmares to you and your team.

---

The following is not a tutorial. It is the git conventions of our team.

## Fork

This operation makes a copy of a repository.  [bitbucket fork](https://legacy.gitbook.com/book/jingbogit/everest-tutorial/edit#)

* We call the repository that your mentor assigns to you the **upstream**.

* Always edit on your forked repository instead of the upstream.

* You would not be able to create a pull request if you did not fork from the upstream.

* After forking, you may need to setup CI/Pipeline and input all the required env vars, such as the NPM_TOKEN.

## Clone

Clone a remote repository to your computer.

```
  git clone https://github.com/<YOUR_NAME>/<REPO_NAME>
```

## Sync with upstream

Your **upstream** repository may have changes during your development. To merge those changes into your repo, you first need to add the upstream as a remote \([ref](https://help.github.com/articles/adding-a-remote/)\):

```
git remote add upstream https://github.com/<UPSTREAM_NAME>/<REPO_NAME>
```

then pull the upstream code

```
git pull upstream <BRANCH_NAME>
```

If conflicts happens, fix them and commit again. The merge succeeds after all conflicts are eliminated.

## Pull Request {#git-pull-request}

When you are ready to submit your code to review, you [create a pull request](https://www.atlassian.com/git/tutorials/making-a-pull-request). In the request, you need to notify your code reviewer, including at least your mentor.

After getting comments, modify your code accordingly, sync with the upstream again. By pushing those changes to your forked repo, the pull request will automatically update.

It is strongly recommended to create a PR that is as small as possible as a logical unit.
For a big feature change, break it down into small logical sub-steps, create a PR and push each step into a feature branch separately.
Giving a very large PR would only make others difficult to review and reason about. 

# Ignore files

`.gitignore` will exclude certain files to be tracked by git. e.g.

```
build/
node_modules/
release/
```

---

## Large files

Do not add large files like picture, video, 3D model to the git repository.

