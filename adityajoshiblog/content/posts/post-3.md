---
title: "Change Git Remote URL via terminal"
date: 2022-09-18T12:42:54+05:30
draft: false
---

I used to clone github repositories with https link. We could use our github credentials with Git command line.

However as of August 21, [Github has removed support](https://github.blog/2020-12-15-token-authentication-requirements-for-git-operations/) for using your account password from Git command line.

That means you either need to generate Personal Access Tokens or configure repo with ssh keys.

I prefer 2nd option and that would mean that I need to change remote url in my checkout repo.

This is how to do it. 

```bash
git remote set-url {remote_name} {ssh_url}
```

You need to pass remote name (without braces. Usually it's "origin") and ssh_url. (again without braces and can be found on your github repo)

Along with this you will have to setup your ssh keys. Steps to setup that on github can be found [here](https://docs.github.com/en/authentication/connecting-to-github-with-ssh).
