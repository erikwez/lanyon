---
layout: post
title: Create Mavericks USB-drive Installer
date: 2013-10-06
categories: Geeky
tags:
  - mavericks
  - osx
---

![Creating USB-installer in the Terminal](/assets/img/20131006-installUSB.png " ")

*This was written for the Mavericks GM-version. Unless Apple changes things, it should be valid for the final version*.

OK, so you want to create a USB-drive to install OS X 10.9 "Mavericks". In previous versions of OS X, you could [create an USB-installer][installML] by restoring the InstallESD.dmg found in the OS-package downloaded from the Mac App Store (MAS). This is no longer an option.

In Developer Preview 4, Apple introduced a *createinstallmedia* executable. You'l find it inside the downloaded OS X Mavericks in `/Contents/Resources/createinstallmedia`. We'll use this to create a USB installer.

## Download Mavericks

After you download OSX Mavericks from MAS, the installer will launch. Just quit to halt the installation process. This will retain *OS X Mavericks.app* in your applications folder.

## Ready USB media

Now ready the media you want to use for the installer. You'll need at least 8GB, but you can of course use larger media.

Format the media as Mac OS X Extended (Journaled) with GUID partition mapping. Name it *Untitled*[^1].

## Create the installer

Now launch the Terminal and enter

{% highlight bash %}
    sudo /Applications/Install\ OS\ X\ Mavericks.app/Contents/Resources/createinstallmedia --volume /Volumes/Untitled --applicationpath /Applications/Install\ OS\ X\ Mavericks.app --nointeraction
{% endhighlight %}

The command must be run as admin, so type in your admin-password. Now wait 15-20 minutes for the process to finish.

Restart and hold down the option-key to boot from the newly created USB installer.

[^1]: You can, of course, name the volume whatever you like. Just make sure to specify the correct volume-name in the createinstallmedia command `--volume /Volumes/"volume-name"`

[installML]: http://osxdaily.com/2012/02/17/make-bootable-os-x-10-8-mountain-lion-usb-install-drive/
