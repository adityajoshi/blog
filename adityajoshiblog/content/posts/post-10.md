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

2. To install ncurses lib on fedora 
    ```
    sudo dnf install ncurses-devel-6.4-7.20230520.fc39.x86_64
    ```
    Note - Hit tab after nucrses-devel. It will pick up available version.
