---
title: "Openbox Power menu setup"
date: 2025-02-23T16:45:28+05:30
tags: ["openbox", "fedora"]
draft: false
---

---

## Adding Shutdown, Restart, Suspend, and Hibernate Options in Openbox Menu

If you're using Openbox as your window manager and want quick access to power options like **Shutdown, Restart, Suspend, and Hibernate**, modifying the `menu.xml` file is a simple and effective approach.

### 📌 Steps to Add Power Options

1. **Locate your `menu.xml` file**  
   Typically found at:  
   ```
   ~/.config/openbox/menu.xml
   ```
   If it's not there, check in `/etc/xdg/openbox/menu.xml`.

2. **Edit the File**  
   Open it in your favorite text editor:
   ```
   vim ~/.config/openbox/menu.xml
   ```
   Or use nano:
   ```
   nano ~/.config/openbox/menu.xml
   ```

3. **Add the Power Options**  
   Inside the `<menu>` section, add the following entries:

   ```xml
   <item label="Suspend">
       <action name="Execute"><execute>systemctl suspend</execute></action>
   </item>
   <item label="Hibernate">
       <action name="Execute"><execute>systemctl hibernate</execute></action>
   </item>
   <item label="Reboot">
       <action name="Execute"><execute>systemctl reboot</execute></action>
   </item>
   <item label="Shutdown">
       <action name="Execute"><execute>systemctl poweroff</execute></action>
   </item>
   ```

4. **Apply Changes**  
   After saving the file, refresh Openbox to apply the new menu options:  
   ```
   openbox --reconfigure
   ```

### 🛠️ Troubleshooting

- If the commands don’t work, ensure you have the necessary permissions. You may need to allow non-root users to execute `systemctl` commands by modifying `/etc/sudoers`:
  ```
  sudo visudo
  ```
  Add:
  ```
  your_username ALL=(ALL) NOPASSWD: /bin/systemctl suspend, /bin/systemctl hibernate, /bin/systemctl reboot, /bin/systemctl poweroff
  ```
  Then modify `menu.xml` to use:
  ```xml
  <execute>sudo systemctl poweroff</execute>
  ```

### 🎯 Why This is Useful

- Eliminates the need for a terminal to execute power commands.
- Provides a graphical way to shut down, restart, or suspend your system.
- Enhances workflow efficiency when using Openbox as a lightweight window manager.

With this setup, you now have a streamlined way to manage power options directly from your Openbox menu. 🚀