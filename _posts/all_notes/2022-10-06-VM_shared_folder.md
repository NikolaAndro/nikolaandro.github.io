---
layout: post
title:  "Create a shared folder in Linux"
date:   2022-10-06 09:29:20 +0700
categories: post
topic: linux
---
How to create a shared folder on Linux VM?

# 1

Create a folder on the host machine. Open VirtualBox Manager, select the guest machine, then settings, then shared folders. 

# 2

Click icon to add folder. Locate the folder you created in step 1. Select Auto-Mount. Click OK.

# 3 

Start the guest Linux machine. Execute following commands:

    sudo apt-get update
    sudo apt-get install virtualbox-guest-dkms
    sudo apt-get install virtualbox-guest-utils
    
# 4

Check your username and add it to the `vboxsf` group:

    $whoami
    [username result]
    $sudo adduser [username result] vboxsf

# 5 

Shut down the machine and turn it on again. Your shared files will be in `/media` folder and they will start with `sf_` prefix.
    
