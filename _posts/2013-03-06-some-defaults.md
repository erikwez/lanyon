---
layout: post
title: Some Defaults
date: 2013-03-06
categories: Geeky
tags:
  - defaults
  - osx
---

Some settings I just like to apply on my Macs. There are lots of resources for finding these "hidden" preferences. A good place to start is [Secrets][1]. You can download a Preference Pane for easy access to tweaking your settings. An application like [MacPilot][2] can also be used.

[The Pragmatic Programmers][3] has also published [Mac Kung Fu][4] which contain a lot of `defaults write` tips.

### Expanding the Save Dialog​

I just hate the collapsed Save dialog box. Enter this in the Terminal to make the expanded view default

{% highlight bash %}
    defaults write -g NSNavPanelExpandedStateForSaveMode -bool TRUE
{% endhighlight %}

### Expanding the Print Dialog

The same goes for the collapsed Print Dialog Box

{% highlight bash %}
    defaults write -g PMPrintingExpandedStateForPrint -bool TRUE
{% endhighlight %}
### The iCloud default

Apple's iCloud is great for a number of things, and not so great for others. I don't like saving my documents to iCloud (I use Dropbox instead), so making the default save location to not beeing iCloud, type

{% highlight bash %}
    defaults write NSGlobalDomain NSDocumentSaveNewDocumentsToCloud -bool false
{% endhighlight %}
### UTF-8 in Mail.app

I use Apple's Mail.app. Back in the days I was a Eudora user, but I took the plunge to Mail.app in 2002. I've tried a number of other applications (Thunderbird, Entourage, Outlook, Postbox, MailMate), but I always return to Mail.app. As I often write in Norwegian (with æ, ø and å) to recipients on Windows, I tend to set the default text encoding in Mail.app to UTF-8.

{% highlight bash %}
    defaults write com.apple.mail NSPreferredMailCharset "UTF-8"
{% endhighlight %}
[1]: http://secrets.blacktree.com
[2]: http://www.koingosw.com/products/macpilot.php
[3]: http://www.pragprog.com
[4]: http://pragprog.com/book/ktmack2/mac-kung-fu
