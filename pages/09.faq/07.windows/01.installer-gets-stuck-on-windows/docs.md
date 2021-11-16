---
title: 'Installer gets stuck on Windows'
date: '16:04 16-11-2021'
taxonomy:
    category:
        - docs
---

The installer may get stuck if the app was not uninstalled correctly. To fix the issue you will need to clean up the left-over entry from the Registry. To do so please follow these steps:

- Press Win + R (Windows Key + R)
- Type "regedit.exe"
- Navigate to `HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Uninstall`
- In there, you will see one or more folders. Open them one by one to find the one for Joplin. One of the entries in there should be "DisplayName" with value "Joplin x.x.x".
- Once found, delete that folder.

Now try to install again and it should work.

More info there: https://github.com/electron-userland/electron-builder/issues/4057