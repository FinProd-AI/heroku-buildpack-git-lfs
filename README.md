# Heroku Buildpack: git-lfs

This is a Heroku buildpack which installs Git LFS and downloads your Git LFS data during deployment (which Heroku does not do by default).

## Usage

```
heroku buildpacks:add --index 1 https://github.com/FinProd-AI/heroku-buildpack-git-lfs
```

Set the following environment variable for your app:

`GIT_LFS_REPOSITORY` to the clone URL of the repository from which to download Git LFS data. This should include any username, password, or personal access token which is necessary to clone noninteractively. See [here](https://stackoverflow.com/a/50193010/3538165) for details on the syntax. It must be something like `git@github.com:<username>/<repository>` or `https://<token>@github.com/<username>/<repository>.git`
`GIT_LFS_SSH_KEY` your private key if you don't want to use your password or personal access


After the next time you deploy your app, Git LFS assets will be downloaded and checked out automatically, and Git LFS will be available on PATH for your app.

## Reference

[Heroku Buildpacks](https://devcenter.heroku.com/articles/buildpacks)
