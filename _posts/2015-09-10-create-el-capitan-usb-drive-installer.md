---
layout: post
title: Create El Capitan USB-drive Installer
date: 2015-09-10
excerpt: How to create a bootable USB-drive with the El Capitan (OS X 10.11) installer.
categories: Geeky
tags:
  - el capitan
  - osx
---

![Creating USB-installer in the Terminal](/assets/img/20150910-el-capitan.jpg " ")


This time of year again. A new version of OS X, this time OS X version 10.11, also known as _El Capitan_. If you have multiple computers to upgrade, you don't want to download the 6 GB installer on every Mac – you'd want to create some sort of install media.

El Capitan is the third OS X version where the installer ships with the executable `createinstallmedia`. I've covered the procedure of creating a USB-drive installer for both [OS X 10.9 Maverics][1] and [OS X 10.10 Yosemite][2]. The procedure for OS X 10.11 El Capitan is the same as for the previous versions, so I won't go into detail.

### The steps

1. Find a USB-drive of some sort. A USB-stick is probably most convenient. You'll need an 8 GB or larger drive. Format the media as Mac OS X Extended (Journaled) with GUID partition mapping. Name it `Untitled`.
2. Download the El Capitan installer from the Mac App Store. Don't run it after the download finishes.
3. Open the Terminal (/Applications/Utilities/Terminal) and enter:

{% highlight bash %}
sudo /Applications/Install\ OS\ X\ El\ Capitan\ GM\ Candidate.app/Contents/Resources/createinstallmedia --volume /Volumes/Untitled --applicationpath /Applications/Install\ OS\ X\ El\ Capitan\ GM\ Candidate.app --nointeraction
{% endhighlight %}


Type in your administrative password, and wait 15-20 minutes for the process to finish. Hold down ⌥ during startup to boot from the newly created USB installer.

The command is for the El Capitan GM (Golden Master), so you probably need to correct the "El Capitan Install App"-name. Remember [tab completion][3]. Start typing the path `/Appl`and press ⇥. Terminal will expand this to `/Applications/`. Continue with `Inst`and press ⇥ to expand this to the full name of the installer. In my case `Install\ OS\ X\ El\ Capitan\ GM\ Candidate.app/`. The backslashes escapes the spaces in the file name. Continue this process all the way down to `createinstallmedia`.

### Homebrew and /usr/local

If you are a [Homebrew][3] user, or use other packages that puts stuff into `/usr/local/`, use the tip from [Jim Lindley][4] for clearing out `/usr/local/` before upgrading. If you don't, you're in for a looong wait.

Happy upgrading!

[1]: /2013/create-mavericks-usb-drive-installer
[2]: /2014/create-yosemite-usb-drive-installer
[3]: https://en.wikipedia.org/wiki/Command-line_completion
[4]: http://brew.sh
[5]: https://jimlindley.com/blog/yosemite-upgrade-homebrew-tips/
