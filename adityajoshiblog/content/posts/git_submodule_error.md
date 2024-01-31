---
title: "Solve Git submodule Update Error"
date: 2022-09-19T23:14:34+05:30
tags: ["git"]
draft: false
---

At times you will maintain or use a git repo which contains another repo as a submodule. 
Sometimes when you update or add this submodule again you may end up error like this.

```
'main_repo/sub_repo' already exists in the index.
```

To fix this run below command and try adding submodule again.

```
git rm -r --cached main_repo/sub_repo
git submodule add --force -b main {repo_url} {folder_to_use_for_sub_repo}
```

