---
title: Using emacs shortcuts in Windows
tags: shortcuts Emacs Windows
category: tips&tricks
author: mastro35
share: true
layout: post
---

You have been working in Emacs for several hours, perhaps programming in Elisp, when an error message that you are unfamiliar with comes up.
Of course, you know that [there is an option to ask Emacs for help directly](https://emacsworld.com/help/2023/01/22/asking-for-help-in-emacs.html) in most cases, but in this particular case you decide to do a search on a search engine. 
In a moment you copy the error message that appeared via the `M-w` key combination and open your favorite browser trying to paste it in the *Bing* search bar pressing `C-y`, but nothing happens. 

Raise your hand if this has happened to you at least a thousand times! 

Wait... what? Anyone? Um, okay, okay... it also applies to those who use Google instead of Bing....

Okay, now here we go, you all have your hand up, right?

![Refresh Types](https://imgs.xkcd.com/comics/refresh_types.png){: .align-center}

## Muscle memory

In English this is called *muscle memory*, it happens when you have consolidated a movement for years and this movement has become so automatic that in fact you no longer have any need to think about it in order to repeat it. 
The muscle actually responds automatically to the input sent by the brain, almost as if it had a memory in itself, but in this case it is too hasty, it does not notice that we have changed scope and that in Windows the command for pasting text is not `C-y` but `C-v`. Hence the error and the resulting frustration (it usually takes me a few seconds before I figure out what went wrong and repeat the correct key combination).

How can you make sure that the muscle memory respond with the correct key combination depending on the active window? 
Simple... you can't!

But you can do something smarter, such as teaching Windows that when we press `C-y` we want to paste text and not press two random keys just for the sake of wasting time... ;)

## AutoHotkey

We are helped by a small Windows utility called [AutoHotkey](https://www.autohotkey.com/).
AutoHotkey is a free and open source scripting language for Windows that allows you to create automations for the Redmond operating system by assigning them to specific key combinations.

In our case, then, we will simply install AutoHotkey (the installation process is quite simple: download the program, double-click on the installer and then always click *Next*) and create a new script that remaps the desired key combinations. 

In my case, I remapped the commands to use the clipboard (cut, copy, and paste), the `C-k` command to remove the rest of a line of text and save it to the clipboard, and the default combination for undoing an edit with the following script:

```
#InstallKeybdHook
#UseHook

; The following line is a contribution of NTEmacs wiki http://www49.atwiki.jp/ntemacs/pages/20.html
SetKeyDelay 0


; Applications you want to disable emacs-like keybindings
; (Please comment out applications you don't use)
is_target()
{
   IfWinActive,ahk_class Emacs ; NTEmacs
     Return 1  
   IfWinActive,ahk_class Emacsclient ; emacsclient
     Return 1
  Return 0
}

kill_line()
{
  Send {ShiftDown}{END}{SHIFTUP}
  Sleep 50 ;[ms] this value depends on your environment
  Send ^x
  Return
}

kill_region()
{
  Send ^x
  Return
}

kill_ring_save()
{
  Send ^c
  Return
}

yank()
{
  Send ^v
  Return
}

undo()
{
  Send ^z
  Return
}

^k::
  If is_target()
    Send %A_ThisHotkey%
  Else
    kill_line()
  Return

^w::
  If is_target()
    Send %A_ThisHotkey%
  Else
    kill_region()
  Return

!w::
  If is_target()
    Send %A_ThisHotkey%
  Else
    kill_ring_save()
  Return

^y::
  If is_target()
    Send %A_ThisHotkey%
  Else
    yank()
  Return

^/::
  If is_target()
    Send %A_ThisHotkey%
  Else
    undo()
  Return
```

The script can be saved with any name you want but it is important that the extension be `.ahk`, so in my case I called it `Emacs.ahk`. 
You can also map many more Emacs shortcuts and in fact what I am presenting here on this blog today is actually my own shortened version of a script by [Naoki Ishikawa](http://ishikawa.cc) which you can find [here](https://github.com/usi3/emacs.ahk), 
and which contains many more shortcuts but my advice is to **remap only the most common ones** and those where actually muscle memory can create a problem. 
In Naoki's script, for example, it also remaps the `C-x C-c` key to close any window but it never occurred to me to try to close a window using this command...in short, in this case it's a matter of taste and finding the best fit for everyone, so if you want you can download the full version of Naoki and start playing with it to figure out what you want to remap and what you don't.

## Run the script at Windows startup.

If after trying the proposed script you, like me, can never live without it again, I urge you to install it so that it starts automatically with Windows. 
To do this, press the key combination `Start-r`, type `shell:startup` and click `OK`. 
You should see the folder containing the programs that run at Windows' startup, typically something like `C:\Users\%USERNAME\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup`.
Move your script to this path and you are done.

## To sum up

In this article we have seen how you can solve many of the problems dictated by the muscle memory associated with Windows clipboard shortcuts without needing to activate the `CUA` mode in Emacs (which I personally hate).
In a future article we will do something similar but this time for macOS users.

Ok, that`s all folks, see you soon and.... happy hacking with Emacs!
D.
