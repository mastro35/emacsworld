---
title: Asking for help in Emacs
tags: help documentation Emacs
category: help
author: mastro35
share: true
layout: post
---

One of the most interesting aspects of Emacs is the fact that it is completely self-documented. Whether you are a beginner or not, asking for help on functionality, key chords, variables or functions will be one of the things you will need sooner or later, and having an editor in front of you who can help you solve your problem will prove very useful. 

![Manual Override](https://imgs.xkcd.com/comics/manual_override.png){: .align-left}

This is precisely why it is important to be familiar with Emacs and its self-documentiong feature.

## The tutorial

If you are an Emacs beginner or have never used Emacs before, the first thing you will probably want is a *tutorial*, that is a guide that quickly and easily introduces you to the world of Emacs without requiring you to read hundreds of pages of manuals before you can open a file, edit it and save it.

In 2023 probably when you hear the word *tutorial* the first thing that comes to your mind is YouTube, but in fact there is already a fully functional, interactive tutorial within Emacs that will get you familiar with the tool and in no time at all will get you started with Emacs.

To access the tutorial, just press `C-h t` and you're done. Upon exiting the tutorial, you can also choose to save the position you have reached so that you can complete it at a different time.

Generally speaking, everyone should take a tour of the tutorial at least once, if only to learn the standard Emacs terminology, which as you will notice is quite different from what you are probably used to. 

You will rarely hear of *cursor*, much more often you will find yourself talking about *point*. Likewise you will find that a *window* in Emacs is called *frame* and that the term *window* is instead used for a slightly different concept (it is a portion of the screen within a single *frame*). The reason why concepts known to most people by one name are found in Emacs by different terms may appear to be an odd quirk of programmers but in fact it is not, it has much deeper reasons which have to do with the fact that Emacs was born in 1976, well before the well-known concepts we are talking about had equally well-known names. And so, some of these concepts were born in Emacs and then spread under different names to other areas.

Finally, you will get to know some concepts that are almost unique within Emacs, such as the concept of *buffer* on which Emacs is forcibly based and which is profoundly different from the concept of *file* on which traditional editors are based. 

## Standard documentation

Think of any object, something like a household appliance or perhaps the latest Swedish piece of furniture you brought home and have to assemble yourself. Inside the package you have probably found a manual, more or less detailed depending on what is required, right?

Well, the same thing happens with Emacs. A manual is available within the software itself. 

To access the official manual from within Emacs, just type the key combination `C-h r` and the official manual will appear in a dedicated buffer.

Beautiful, isn't it?

In the manual you will find almost everything you may need and even more. The same manual can be accessed also online, in the form of a [657 pages pdf](https://www.gnu.org/software/emacs/manual/pdf/emacs.pdf).

## Three indispensable aids

Once you become familiar with Emacs you will no longer need the tutorial and will perhaps access the manual only rarely. But the situations in which you will need to ask for help will always be there, perhaps just to know what a certain command does or to look at the definition of a function. And it is precisely in these moments that there will be three commands that will be your allies and get you out of trouble quickly. 

The first of the three commands is the `describe-key` command, which will let you know what a specific key combination is for. To execute the command, just type `C-h k`, and Emacs will ask you to type the key combination you want help with, and will give you the information about that specific function. 

For example, if after typing `C-h k` you press `C-h r` Emacs will show you a description of the command which calls up the Emacs manual (as we mentioned earlier).

```
C-h r runs the command info-emacs-manual (found in global-map), which
is an autoloaded interactive byte-compiled Lisp function in 'info.el'.

It is bound to C-h r, <f1> r, <help> r, <menu-bar> <help-menu>.
<emacs-manual>.

(info-emacs-manual)

Display the Emacs manual in Info mode.

[back].
```

Another really handy and helpful command is the `describe-function` command, which lets you know what a specific function is for. This command, too, can be invoked through a convenient key combination, `C-h f`, and after invoking this command, you simply type in the name of the function you want to know how it works. 

For example, try calling the command and then entering the name of the function `info-emacs-manual`, which is the function for calling the Emacs manual we discussed before, and you'll get this response:

```
info-emacs-manual is an autoloaded interactive byte-compiled Lisp
function in 'info.el'.

It is bound to C-h r, <f1> r, <help> r, <menu-bar> <help-menu>.
<emacs-manual>.

(info-emacs-manual)

Display the Emacs manual in Info mode.

[back].

```

As you can see, Emacs will give you information about the function and also the key combination associated with it (very useful when you remember the name of the function but not the combination that calls it up).

Finally, the last function you need to know about is the `describe-variable`, which at this point it's easy to imagine what it might be used for. Given a variable name, the function shows you the meaning of that variable and its use.

For example, try calling this command and entering the variable name `command-line-functions` to find out what this particular variable is for:

```
command-line-functions is a variable defined in 'startup.el'.

Its value is nil

List of functions to process unrecognised command-line arguments.
Each function should access the dynamically bound variables
'argi' (the current argument) and 'command-line-args-left' (the remaining
arguments).  The function should return non-nil only if it recognises and
processes 'argi'.  If it does so, it may consume subsequent arguments by
altering 'command-line-args-left' to remove them.

  This variable may be risky if used as a file-local variable.
  Probably introduced at or before Emacs version 19.23.

[back]
```

There are other similar and interesting keys, like the `describe-mode` which gives you information about the *major* and *minor modes* active in the current buffer, or the `describe-symbol` which accepts the name of a symbol and gives you its meaning, but those are the three most used.

## Apropos

For *fuzzier* request, the command which comes to our aid is `apropos`. This command, invoked through `M-x apropos` shows all the Lisp symbols whose names match a given input, which can be a list of words or a regular expression. 

For example, if you don't know how to see the list buffers, try calling `apropos` and entering `list buffers` as input. You'll get several results in which you'll find the solution to your need.

## Other resources on the net

In addition to the numerous resources offered by Emacs itself, there is of course an infinite amount of documentation on the net as well. Listing them all seems to me to be of little use, but surely a list of the main ones cannot be missing from an article like this.

First of all, one cannot leave out the [official site](https://www.gnu.org/software/emacs/), which is obviously the first source of information to always keep in mind. Within this site you will also find links to the [introductory manual to programming in Elisp](https://www.gnu.org/software/emacs/manual/html_node/eintr/index.html), which is essential reading if you want to go further and start getting serious about Elisp. 
Also related to Elisp is the [reference manual](https://www.gnu.org/software/emacs/manual/html_node/elisp/index.html), also a must-read.

Moving on to the sites of enthusiasts, we must not forget the site of [Sacha Chua](https://sachachua.com/blog/), which is a veritable mine of information, and the [Xah Emacs Blog](http://xahlee.info/emacs/emacs/blog.html), which, despite its appearance, is a site with excellent content.

Last mention for a real book: [Mastering Emacs](https://www.masteringemacs.org_) a practical and simple book that will guide you through the world of Emacs, also explaining the motivations and philosophy behind this fantastic editor.

## In conclusion

The learning curve of Emacs may initially seem a little steep but I don't think I can put into words how worthwhile it really is. 

Learning Emacs is a journey where the destination is secondary, because the real magic lies in the journey.

