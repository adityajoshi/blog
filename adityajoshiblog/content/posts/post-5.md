---
title: "Configure xdg-open for a File or URL"
date: 2022-10-25T08:45:13+05:30
draft: false
---


If you are using linux machine chances are that you are already using `xdg-open`.

`xdg-open` is a utility used by system to open a file or URL in the user's preferred application.

To run a specific program for a given type of file or URL all you have to do is create a .dekstop file and configure so that `xdg-open` can run mentioned program for you. 

To do that create first a desktop file.

Here is a example of bombadillo.desktop file to execute [bombadillo](https://bombadillo.colorfield.space/) program for any URL starting with gopher/gemini/finger protocol.

```
[Desktop Entry]
Type=Application
Name=Bombadillo
GenericName=Non-Web Browser
Comment=View gopher, gemini, finger, telnet, http(s) sites over the internet
Terminal=true
Categories=Network;WebBrowser;ConsoleOnly;
Exec=bombadillo -t %u
Icon=bombadillo-icon
MimeType=x-scheme-handler/gopher;x-scheme-handler/gemini;x-scheme-handler/finger;
```

Note - Terminal=true is needed so that `xdg-open` can spawn a terminal and execute program in it.

Copy file in .local/share/applications in your home directory.

Run below command to configure this desktop file to gemini URL.

```xdg-mime default bombadillo.desktop x-scheme-handler/gemini```

This should work whenever next time you try to open any URL starting with "gemini://".
