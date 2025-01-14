---
layout: post
title:  "SSH Key Setup - GitHub"
date:   2021-10-27 09:29:20 +0700
categories: post
topic: github
---

# SSH key setup

    1. Enter the following command with your GitHub email:

       ssh-keygen -t rsa -b 4096 -C "joe@example.com"
  
    2.Press Enter to accept the default file location (home/username/.ssh/id_rsa).

    3.Enter a secure phrase that you will remember.

    4.Copy the public key.

       cat .ssh/id_rsa.pub
  
    5.In GitHub settings go to SSH keys, generate a new key. 

    6.Name it so you know to which machine the key is related.

    7.Paste the public key from the clipboard. 

    8.Generate.
