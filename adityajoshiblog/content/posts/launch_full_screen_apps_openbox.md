---
title: "How I Launch Applications in Fullscreen with Openbox"
date: 2025-05-04T00:49:41+05:30
tags: ["openbox", "fedora"]
---


--- 

The Goal to have specific applications—like Firefox, VLC, or others—to **always start in fullscreen** when launched in Openbox. 
I don’t want to press keys or click buttons every time. I want it automated, clean, declarative. 

--- 

### Step 1: Find the Window Class

Before Openbox can apply rules to an app, it needs to know how to identify the app’s window. 

To discover this, I use `xprop`: 

```bash 
xprop | grep WM_CLASS
```

I click the app window. This command returns something like:

```bash
WM_CLASS(STRING) = "urxvt", "URxvt"
```

In this case, "urxvt" and "URxvt" is the window’s class name. That’s the identifier Openbox needs. 
Important: It’s usually the first string (here, "urxvt") that Openbox uses in rc.xml. Write this name down.

### Step 2: Configure Openbox

I edit the Openbox configuration file: 

```bash
vim ~/.config/openbox/rc.xml
```

Inside the *applications* tag, I add this:

```xml
<application name="urxvt">   
  <fullscreen>yes</fullscreen> 
</application>
```

Replace "urxvt" with the name you got from xprop. 

### Step 3: Reload Openbox

After saving the file, I apply the new config: 

```bash
openbox --reconfigure
```

Now, every time I launch urxvt (or whatever app I configured), it will automatically open in fullscreen. 
No more manual toggling.




