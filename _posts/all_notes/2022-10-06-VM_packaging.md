  ---
layout: post
title:  "Virtual Machine Export and Import"
date:   2022-10-06 09:29:20 +0700
categories: post
---

How to export your already created VM and import it on another machine?

# 1: Export

After you closed your VM, wait for about 30 min. Then, Click on `Tools` and then `Export`.  Select your machine and follow the default settings.

# 2: Upload

You will result with an .ova  (Open Virtual Appliance) file. Upload it a shared online storage.

# 3: Download and Extract

When you get on another machine, download the .ova file from the shared storage. 

Then, extract it. On Linux, you can do

      tar -xvf [name_of_your_vm].ova
      
This will result in 3 new files. You care about .vmdk file.

# 4 Import

Open the VM manager. Click `New`. Name your machine and select OS. Click `Next`. Give it RAM (I did 20Gb out of 32GB since the VM will be the only one running). On the 
next step select `Use an existing virtual hard disk file`. Click `Add` and locate the .vmdk file that you extracted in the step 3. Click `Choose` and then `Create`.

# 5 Run

Select your machine and run it.
