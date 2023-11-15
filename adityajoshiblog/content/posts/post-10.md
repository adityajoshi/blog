---
title: "Useful commands and scripts"
date: 2023-11-15T08:36:08+05:30
draft: false
---

1. TAR Command to archive just the given folder ( no absolute paths )
    ```
    tar -cvf file_name.tar -C ~/ folder_to_be_archived
    ```

    **-C** option will make tar command to change it's directory from whereever it is to ~/ (home path)
