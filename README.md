# Heroku Buildpack: git-lfs

This is a forked Heroku buildpack which installs Git LFS and downloads your Git LFS data during deployment (which Heroku does not do by default).  
It is based on [infinitly/heroku-buildpack-git-lfs](https://github.com/infinitly/heroku-buildpack-git-lfs).

---

## 🚀 Usage

Add the buildpack to your Heroku app:

```sh
heroku buildpacks:add --index 1 https://github.com/FinProd-AI/heroku-buildpack-git-lfs
```

### Required Environment Variables

- **`GIT_LFS_REPOSITORY`**  
  The clone URL of the repository from which to download Git LFS data.  
  This should include any username, password, or personal access token necessary to clone noninteractively.  
  - For SSH:  
    `git@github.com:<username>/<repository>.git`
  - For HTTPS with token:  
    `https://<token>@github.com/<username>/<repository>.git`  
  See [this Stack Overflow answer](https://stackoverflow.com/a/50193010/3538165) for details on the syntax.

- **`GIT_LFS_SSH_KEY`**  
  Your private SSH key if you don't want to use a password or personal access token.

---

## 🛠️ What Happens After Deployment?

- On your next deploy, Git LFS assets will be downloaded and checked out automatically.
- Git LFS will be available on the `PATH` for your app.

---

## 📚 Reference

- [Heroku Buildpacks Documentation](https://devcenter.heroku.com/articles/buildpacks)
