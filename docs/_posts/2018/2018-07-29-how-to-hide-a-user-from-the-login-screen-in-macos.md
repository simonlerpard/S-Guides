---
layout: post
title:  "How to hide a user from the login screen in MacOS"
author: Simon
categories: [ tutorial, MacOS ]
image: assets/images/how-to-hide-a-user-from-the-login-screen-in-macos.jpg
toc: false
---

This guide will show you how to hide a user from the login screen in MacOS and unhide them again. It’s a pretty short straight forward guide and takes just a few minutes to follow through.

1. Create a user with optional name, .e.g. User1
2. Create a directory with root somewhere using the terminal (replace <username> with your user)
```
sudo mkdir /var/<username>
```
3. Open System Settings and choose Users and Groups
4. Right click on the user you are trying to hide (e.g. User1) and choose Advanced settings
5. Change the home directory to the one you created in step 2. (e.g. /var/User1)
6. Run the following in the terminal to hide the user from the login screen (replace <username> with your user):
```
sudo defaults write /Library/Preferences/com.apple.loginwindow HiddenUsersList -array-add <username>
```

To show all hidden users again, run the following command in the terminal:

```
sudo defaults delete /Library/Preferences/com.apple.loginwindow HiddenUsersList
```
