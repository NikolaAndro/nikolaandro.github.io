---
layout: post
title:  "Syncthing on PC and phone"
date:   2025-04-28 09:29:20 +0700
categories: post
topic: Personal Cyber Security
---

# Syncthing

Syncthing is a great software for sharing your files peer to peer while still encrypted.

### Benefits over cloud solutions:

1. Your data is yours only - no other company can have your data
2. You do not depent on other company's servers (shutdowns, hacks, etc.)
3. You can connect as many devices as you like
4. You do not need internet to access already synced files

# KeePass Database Sync via Syncthing

Keepass is an offline password manager that stores passwords in a secure database file.

Let us see how can we share this database files accross multiple devices using Syncthing.

## Prerequisites
- A KeePass database file (`.kdbx`) on both PC and Keepassium app installed on your phone 
- Syncthing installed on your PC and on your phone  (Synctrain on iPhone)

## 1. Install & Enable Syncthing on PC


1. **Install Syncthing**  
   Update the package list and install Syncthing using the following commands:
   ```bash
   sudo apt update
   sudo apt install syncthing
   ```

   - `sudo apt update`: Updates the list of available packages and their versions.
   - `sudo apt install syncthing`: Installs the Syncthing application on your system.

2. **Download the Syncthing systemd service file**  
   Use the `wget` command to download the Syncthing systemd service file to the appropriate location:
   ```bash
   wget -O ~/.config/systemd/user/syncthing.service https://raw.githubusercontent.com/syncthing/syncthing/master/etc/linux-systemd/user/syncthing.service
   ```

   - `wget -O ~/.config/systemd/user/syncthing.service`: Downloads the Syncthing systemd service file and saves it to the `~/.config/systemd/user/` directory.
   - The URL points to the official Syncthing repository, ensuring you get the latest service file.

3. **Verify Syncthing installation**  
   Confirm that Syncthing is installed and accessible:
   ```bash
   command -v syncthing
   ```

   - `command -v syncthing`: Checks if the `syncthing` command is available in your system's PATH, verifying the installation.


4. Edit your user unit directly

```nano ~/.config/systemd/user/syncthing.service```

Find the `ExecStart=` line and update it to the path you found. For example, if `command -v syncthing` returned `/usr/local/bin/syncthing`, change:

```ExecStart=/usr/bin/syncthing serve --no-browser --no-restart --logflags=0```
to ```ExecStart=/usr/local/bin/syncthing serve --no-browser --no-restart --logflags=0```

Save & exit.


5. **Reload systemd and enable Syncthing to run in the background**  
   Execute the following commands to configure and start Syncthing as a background service:
   ```bash
   systemctl --user daemon-reload
   systemctl --user enable --now syncthing.service
   systemctl --user status syncthing.service
   ```

   - `systemctl --user daemon-reload`: Reloads the systemd manager configuration to recognize the new Syncthing service file.
   - `systemctl --user enable --now syncthing.service`: Enables the Syncthing service to start automatically when the user logs in and starts it immediately.
   - `systemctl --user status syncthing.service`: Displays the current status of the Syncthing service to confirm it is running correctly.


Now the deamon is running in the background and whenever you drop files in a shared directory (~/Sync/ by default) the files will be automatically synced with other devices.