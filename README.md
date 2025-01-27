# Instructions for Installing JetBrains IDEs on Fedora Linux

This guide provides step-by-step instructions to install JetBrains IDEs or any Linux `.tar.gz`/executable files on Fedora Linux. Additionally, it explains how to set up desktop entries for easy access.

---

## 1. Update Your System
Keep your system up-to-date before installing any new software:
```bash
sudo dnf update
```

---

## 2. Install Java (Just in Case)
Some JetBrains IDEs require Java. Install it using:
```bash
sudo dnf install java-latest-openjdk
```

---

## 3. Navigate to Your Downloads Folder
Move to the directory where your IDE `.tar.gz` files are downloaded:
```bash
cd ~/Downloads
```

---

## 4. Extract the Files
Unpack the `.tar.gz` archives for each IDE:
```bash
tar -xzf WebStorm-xxx.tar.gz
tar -xzf RustRover-xxx.tar.gz
tar -xzf pycharm-professional-xxx.tar.gz
```
Replace `xxx` with the actual version numbers of the downloaded files.

---

## 5. Move the IDEs to `/opt`
Move the extracted folders to `/opt` for system-wide access:
```bash
sudo mv WebStorm-xxx /opt/webstorm
sudo mv RustRover-xxx /opt/rustrover
sudo mv pycharm-xxx /opt/pycharm
```

---

## 6. Make the Launch Scripts Executable
Ensure the main executable scripts have the proper permissions:
```bash
sudo chmod +x /opt/webstorm/bin/webstorm.sh
sudo chmod +x /opt/rustrover/bin/rustrover.sh
sudo chmod +x /opt/pycharm/bin/pycharm.sh
```
If the executable doesn't have a `.sh` extension, use the provided name instead.

---

## 7. Create Desktop Entries
To launch IDEs from the application menu, create `.desktop` files:

### Example for WebStorm
```bash
sudo nano ~/.local/share/applications/webstorm.desktop
```

Add the following content:
```
[Desktop Entry]
Version=1.0
Type=Application
Name=WebStorm
Exec=/opt/webstorm/bin/webstorm.sh
Icon=/opt/webstorm/bin/webstorm.png
Comment=JavaScript IDE
Categories=Development;IDE;
Terminal=false
```

Repeat the process for other IDEs (RustRover, PyCharm) by changing the `Exec` and `Icon` paths appropriately.

---

## 8. Update Desktop Database
Update the application database to reflect the new entries:
```bash
update-desktop-database ~/.local/share/applications
```

---

## 9. Launch the IDEs
You can now launch the IDEs:

### From the Application Menu
Look for the IDEs in your application menu.

### From the Terminal
Run the following commands to start the IDEs:
```bash
/opt/webstorm/bin/webstorm.sh
/opt/rustrover/bin/rustrover.sh
/opt/pycharm/bin/pycharm.sh
```

---

## 10. (Optional) Create Desktop Shortcuts
To add shortcuts to your desktop:

- Right-click on your desktop.
- Select **Create New Launcher**.
- Use the information from the `.desktop` files to fill out the details.

---

You’re all set! Enjoy using JetBrains IDEs on Fedora Linux.
