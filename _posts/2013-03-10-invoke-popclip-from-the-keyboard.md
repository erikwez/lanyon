---
layout: post
title: Invoke PopClip from the Keyboard
date: 2013-03-10
categories: Geeky
tags:
  - popclip
  - keyboardmaestro
  - osx
---

![Image of PopClip in action](/assets/img/20130310-PopClip.png " ")

[PopClip][1] from [Pilotmoon Software][0] is a handy utility for working with text. PopClip appears when you select text with your mouse, much the same way as you see on iOS.

Now a pop up with cut, copy and paste wouldn't be too much to be exited about, but PopClip can be customized with [extensions][4]. The selected text can be run through a plethora of services; text editing and transformation, web search, sending it to different applications, convert between html and Markdown and [many more][4].

PopClip has quickly become one of my favorite utilities, the only problem being that it would **only appear when you select text with your mouse**. When writing, my hands are mostly on the keyboard, and text selections are done using the keyboard. PopClip does not appear when selecting text this way.

Fortunately, PopClip has AppleScript support, and the [user guide][3] states you can activate PopClip using:

{% highlight applescript %}

    tell application "PopClip" to appear

{% endhighlight %}

There are many ways to trigger this AppleScript. [George Coghill][5] shows one option using Automator and Services. I chose to use the exellent [Keyboard Maestro][6]. Create a new macro with the AppleScript action, and assign it a keyboard shortcut.

![KeyboardMaestro macro for invoking PopClip](/assets/img/20130310-km-macro-show-pop-clip.png "")

Now whenever I select some text and press ⌃+⌥+P, PopClip appears, and I can use the arrow-keys and space/return to execute the action.

[0]: http://pilotmoon.com/ "Pilotmoon Software"
[1]: http://pilotmoon.com/popclip/ "PopClip for Mac"
[3]: http://pilotmoon.com/popclip/guide/ "PopClip User Guide"
[4]: http://pilotmoon.com/popclip/extensions/ "PopClip Extensions"
[5]: http://georgecoghill.wordpress.com/2012/11/04/invoke-popclip-via-keyboard-using-applescript-automator-and-os-x-services/ "Invoke PopClip Via Keyboard Using AppleScript, Automator and OS X Services"
[6]: http://www.keyboardmaestro.com/main/ "Keyboard Maestro 5.3.2: Work Faster with Macros for Mac OS X"
