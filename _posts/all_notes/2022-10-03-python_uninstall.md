  ---
layout: post
title:  "Uninstall Python - Linux"
date:   2022-10-03 09:29:20 +0700
categories: post
---

# Check what python verssion you have

``` 
cd /usr/bin
ls -l python*
```
# Uninstall 

To uninstall just `pythonx.x` package itself from Ubuntu execute on terminal:

```sudo apt-get remove pythonx.x```

where you need to replace `x.x` with the version you want to remove (e.g. 3.8).

# Dependent Packages

To uninstall the pythonx.x package **and any other dependant package** which are no longer needed on Ubuntu.

```sudo apt-get autoremove pythonX.X```

# Purging 

If you also want to delete configuration and/or data files of pythonX.X from Ubuntu then this will work:

```sudo apt-get purge pythonX.X```

# All together

To delete configuration and/or data files of pythonX.X and it's dependencies from Ubuntu then execute:

```sudo apt-get autoremove --purge pythonX.X```
