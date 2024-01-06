---
title: Splitting Windows in Emacs With *Golden Ratio*
tags: Emacs Windows Split
category: packages
author: mastro35
share: true
layout: post
---

The splitting of a single window into two or more windows is one of the Emacs features I use most and today we're going to use a super simple package to take this feature's usefulness even further.

![Golden Ratio](https://imgs.xkcd.com/comics/iso_paper_size_golden_spiral.png){: .align-left}

## A little digression on Windows and Frames

Okay, you will probably already know that but... bear with me, I can't write an article like this without explaining a little bit about Windows and Frames!

Emacs was born *before* the graphical user interface, so the terminology that we are used to in the modern operating system is slightly different from the Emacs one.
In Emacs, a *frame* is what we are used calling *windows*, which is the window that is opened when we click on the Emacs icon or the terminal window we start emacs in. This is an *Emacs frame*, that contains a single *Emacs window*, which is the portion of the screen that shows the current buffer content. Within Emacs, you can decide to split a single frame into multiple *Emacs windows*. By pressing `C-x 2` you will see that the current windows will split horizontally and with `C-x 3` you can decide to split the current window vertically. `C-x 0` will kill the current window (that won't kill the related buffer tough), reducing the number of windows you have on the frame.

## And the golden ratio?

Emacs users usually use this feature a lot. Especially if you are a developer like me you will find yourself opening a lot of windows during the day, one for the shell, one for the code, one for the log file, and so on, but when you split a window automatically Emacs split it into two identical parts so that the single window is equally divided in two. 

Now, I know it doesn't seems logical but... usually this is not what we want. Usually, we need the current window to be bigger than the other ones opened on the screen. When I'm coding I want to have a bigger window for the code and a smaller one for the log file I'm producing and that's true until I need to have a deep look at the log file, because when I need to inspect it I want a bigger window for the log file and a smaller one for the code. 

That's where [golden ratio](https://github.com/roman/golden-ratio.el) comes in help, it manages this for you automatically, splitting the window with a smaller size and resizing them all as we move across our windows. 
Isn't that cool?

Here you can see it in action:

![golden ratio screenshot](/assets/img/golden_ratio_screenshot.gif)

## Usage

To install the Golden Ratio package just use the `M-x install-package` command followed by the name `golden-ratio` and then enable the `golden-ratio-mode`:

```
(golden-ratio-mode t)
```

So simple.

In the [github page](https://github.com/roman/golden-ratio.el) there is also some information if you need to specify a fixed-max-width when you split a window and if you have big monitors and need to tweak it up. 

And if you want to know a little more about the mathematical idea behind the golden ratio have a look [here](https://en.wikipedia.org/wiki/Golden_ratio).

## To sum up

Sometimes a super simple package like this, based on a super simple idea could really be a game changer and for me, the golden-ratio package did the trick. 

Try yourself, you won't be disappointed.






