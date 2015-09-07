---
layout: post
title: Create Yosemite USB-drive Installer
date: 2014-06-03
excerpt: How to create a bootable USB-drive with the Yosemite (OS X 10.9) installer.
categories: Geeky
tags:
  - yosemite
  - osx
---

## Update October 19, 2014

With the release version of OS X 10.10, `createinstallmedia` finally works. You can follow the same procedure as when [creating the USB installer for OS X 10.9][1] – just update the Terminal command to reflect the downloaded Yosemite Installer. If you prefer the GUI approach, have a look at [DiskMaker X][3]. I won't cover DiskMaker X here.

### The short version

1. USB-media. A USB-stick, 8GB or more. Format the media as Mac OS X Extended (Journaled) with GUID partition mapping. Name it `Untitled`
2. Download the Yosemite Installer for the App Store. It launches after the download is finished, but just quit the installer.
3. Use Terminal (/Applications/Utilities/Terminal) to create the USB-installer

In Terminal, enter:

    $ sudo /Applications/Install\ OS\ X\ Yosemite.app/Contents/Resources/createinstallmedia --volume /Volumes/Untitled --applicationpath /Applications/Install\ OS\ X\ Yosemite.app --nointeraction

Type in your administrative password.

Wait 15-20 minutes for the process to finish. You can now boot from the newly created USB installer holding down the option-key during startup.

#### Tip for Homebrew users (and others with a lot of content in /usr/local)

If you have lots of non-Apple files in `/usr`, the Yosemite upgrade might take may hours. Use this tip from [Jim Lindley][2] on moving the content in `/usr/local` *before* upgrading.

*End update 2014-10-19*
***


In OS X 10.9 Mavericks, Apple introduced a new way of [creating a USB installer][1] with the `createinstallmedia` executable.

The executable is present also in OS X 10.10 Yosemite Developer Preview, but there seems to be a bug which prevents the process to carry through.

In the meantime you can create a Yosemite boot stick much in the same way as early Maverics builds worked.


Mount the InstallESD.dmg image that's under the installer /Contents/SharedSupport.

Mount BaseSystem.dmg using the Terminal

    $ open "/Volumes/OS X Install ESD/BaseSystem.dmg"

Using Disk Utility, Restore the "OS X Base System" volume to your USB stick.

Not necessary, but to make things easier, rename the USB stick something else. I use "yosemiteDP1"

On the USB stick, in the folder System/Installation, delete the symlink named "Packages"

Copy the "Packages" folder from "OS X Install ESD" to the System/Installation folder on your USB stick.

Using Terminal, copy BaseSystem.dmg and BaseSystem.chunklist (they are both hidden from the Finder) from OS X Install ESD to your USB stick

    $ cp "/Volumes/OS X Install ESD/BaseSystem.* /Volumes/yosemiteDP1"

Unmount the stick, boot away.

Let’s hope this bug is fixed before Yosemite DP2

**Update I** 2014-07-08: Still broken in DP3

**Update II** 2014-07-08: The new installer downloaded from App Store is still DP1, so I can’t verify the statement in Update I.



[1]: http://erikwb.net/create-mavericks-usb-drive-installer/ "Create Mavericks USB-drive Installer"
[2]: https://jimlindley.com/blog/yosemite-upgrade-homebrew-tips/ "Faster Mac OS X 10.10 Yosemite Upgrades for Developers – Jim Lindley"
[3]: http://diskmakerx.com/ "DiskMaker X (formerly Lion DiskMaker)"
[4]: http://support.apple.com/kb/HT5856 "Creating a bootable OS X installer in OS X Mavericks"
