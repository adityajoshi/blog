---
title: "Reduce Thinkpad's trackpoint sluggishness on Linux"
date: 2022-09-17T22:58:11+05:30
draft: false
---

If you have installed Linux on a Thinkpad with X11 and feel trackpoint is sluggish to work with then give below config a try.
Ideally this should work on any debian based linux distro.

Open a terminal and copy below snippet.

```shell
id=`xinput | grep -ie "TrackPoint" | awk '{ print $6 }' | awk 'BEGIN{FS="="} {print $2}'`
xinput set-prop $id "Coordinate Transformation Matrix" 6 0 0 0 6 0 0 0 1
```

What we are doing here is chaning X and Y sensitivities (set to 6) where both are 1 by default.

You can use xinput list-props [id] command to check value.


You may want to run this snippet every time X starts. 
For this create .desktop file like below.

```
[Desktop Entry]
Type=Application
Name=USER autostart
Comment=my commands after X startup
Exec=<your command>
```

and save it as $HOME/.config/autostart/trackpoint.desktop

PS - You might want to create a shell script for whatever command you finally make for yourself.

Hope this helps! 
