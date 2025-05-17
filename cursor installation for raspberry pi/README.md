# Creating a Desktop Cursor App for Raspberry Pi (ARM64) Based Linux Distributions

This guide explains how to set up the **Cursor AI Code Editor** as a desktop application on **ARM64-based Raspberry Pi systems running Ubuntu/Linux**.

---

## 📦 Step 1: Download AppImage

Download the **ARM64 AppImage** from the [official Cursor website](https://www.cursor.com/downloads).

---

## ▶️ Step 2: Run the AppImage with `--no-sandbox`

Due to Chromium sandbox limitations on ARM64, use this command to launch:

```bash
./Cursor-0.50.4-aarch64.AppImage --no-sandbox
```

## 🖥️ Step 3: Create a Desktop App Entry

1. Create a Local Binary Folder
```bash
mkdir -p ~/.local/bin
```
2. Move and Prepare the AppImage
```bash
mv ~/Downloads/Cursor-0.50.4-aarch64.AppImage ~/.local/bin/cursor.AppImage
chmod +x ~/.local/bin/cursor.AppImage
```
3. Create a Launcher Script
```bash
nano ~/.local/bin/launch-cursor.sh
```
Paste the following:
```bash
#!/bin/bash
~/.local/bin/cursor.AppImage --no-sandbox
```
Make the script executable:
```bash
chmod +x ~/.local/bin/launch-cursor.sh
```

## 🗂️ Step 4: Add to Applications Menu

```bash
nano ~/.local/share/applications/cursor.desktop
```

Paste the following:

```bash
[Desktop Entry]
Name=Cursor
Comment=AI Code Editor
Exec=/home/roamio42/.local/bin/launch-cursor.sh
Icon=cursor
Terminal=false
Type=Application
Categories=Development;IDE;
```

## 🖼️ Step 5: Add an Icon (Optional)

if the Cursor icon doesn't show:

1. Search and download a cursor.png icon.

2. Save it to:

```bash
~/.local/share/icons/cursor.png
```
3. Update your .desktop file's Icon line:

```bash
Icon=/home/roamio42/.local/share/icons/cursor.png
```

## 🔄 Step 6: Refresh Desktop Entries

```bash
update-desktop-database ~/.local/share/applications
```

✅ Done!
Cursor should now appear in your app launcher and run properly on ARM64 with the --no-sandbox flag.

