---
title: "Importance of brackets around variables in Makefile"
date: 2023-12-22T00:35:57+05:30
tags: ["make", "env"]
draft: false
---

Brackets make it possible for make command to identify defined variable.
Without brackets ( round or curly )  make command will only consider the very next character after "$" sign as variable, leaving remainting characters of the actual word.

Consider below Makefile. Remember it's Makefile so indentation is TAB.

```sh
all: 
	@echo "Building all targets..."

target1: VAR = Value_for_target1
target1:
	@echo "Building target1 with VAR set to $(VAR)"

target2: VAR = Value_for_target2
target2:
	@echo "Building target2 with VAR set to $(VAR)"

```
and if you run... 
```sh
make target1
Output => Building target1 with VAR set to Value_for_target1
```

Make is able to successfully replace VAR variable with it's value.

However...

```sh
make target2
Output => Building target2 with VAR set to AR
```

Not here. For target2 it tried to find a variable "V" but couldn't so printed blank and rest of the characters got printed as is!!! 
