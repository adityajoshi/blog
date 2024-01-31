---
title: "git commands to manage work"
date: 2024-01-31T08:26:21+05:30
draft: false
---

It's very important when you are workin on big feature (which takes more than a day to complete) to take out latest code from target branch ( the one where I wish to merge my code eventually ) and merge in current working branch at-least once a day. 
For past few years I have been used to IntelliJ/PyCharm IDE which has spoiled me with it's UI options so much that at times I find it hard to re-collect underlying git command.

This note is to remind myself about those commands just in-case I have to work in environment where these IDEs are not available.

My usually workflow :
1. I would first take out latest of my target branch in local -> ```sh git checkout target-branch```
2. Then I would create a work branch out of it. -> ```sh git checkout -b feature/branch-1```
3. I would do frequent commits in this to save my work. -> ``` git add file_name/s && git commit -m "commit_message" ```
4. Generally for every commit or maybe for once or twice a day would push it to upstream origin with -> ```git push origin feature/branch-1```
5. To make sure I have latest of target branch -> ```git checkout target-branch```
6. Then pull latest of it -> ```git pull origin target-branch```
7. Switch back to working branch -> ```git checkout feature/branch-1```
8. And merge latest changes of target in my work -> ```git merge target-branch```


