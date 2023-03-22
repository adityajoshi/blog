---
title: "Useful docker commands"
date: 2023-03-18T20:30:14+05:30
draft: false
---

* Fetch and run docker image

```python
docker run -it python:3.9
```

* Build docker image using Dockerfile in current directory.

```shell
docker build -t test:pandas .
```

* This will make image based on your docker file and tag it with name test:pandas
So that you can run same as

```shell
docker run -it test:pandas
```
