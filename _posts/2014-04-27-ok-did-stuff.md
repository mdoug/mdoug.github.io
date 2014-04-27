---
layout: post
title:  "Trials and Tribulations"
categories: blog 
---

Ok, been a while.  I have done some things.  I also made some changes to my
workflow.  

# Switched to Vim

I switched to vim, but I am not entirely sure I am keeping it.  What
I can say, is that I don't miss emacs.  At all.  But I am also not necessarily
sold on vim, for the simple reason that it behaves wildly differently in certain
circumstances depending on whether or not your capslock is on.  Naturally, my
capslock key gets a fair amount of use, since I need it for
STUPIDLY_LONG_DEFINES.  So not using it is not an option for me, so I might
consider other alternatives.  

# Switched to msvc on windows

I have come to terms with the fact that the mingw toolchain is of unacceptably
low quality.  My system was held together with twine, and I was trying out new
text editors, one of which (Komodo Edit) edited my path, leaving it in a broken
state. (It had appended a %PATH% to the end of the user path variable, where I
keep things that I install by hand, which naturally broke it.) 

So, I calmly and cooly diagnosed the problem, and continued forward with what I
had, while considering other options as I move forward.  Hah, just kidding.  I
went nuts.  I uninstalled everything and put it back in, and only realized the
path broke when I went to edit it for the new install.  And then, I got it all
in, but gcc was apparently hardlinked to a file in the I: drive of one of the
packagers, so it didn't work.  So I installed TDM-GCC (which, I think, stands
for Team Deathmatch GCC), which is a different package.  This gcc ran, but the
program that compiled didn't. 

Clang worked, as it did before, so I was going to just call it a day, and move
forward with that.  But then I realized I would be needing Box2D fairly soon, so
I needed a C++ compiler, and I haven't had any luck with clang++ on windows, so
I decided not to go that route.  

Instead, I switched to msvc.  Not Visual Studio Express 2013, since I have tried
the 2012 one, and came to the conclusion that without plugins, it is unusable as
a way to push text.  Furthermore, while I have had reasonable success with it
before using it just to manage a project, and not edit files (good old ALT-TAB),
I wasn't particularly looking forward to doing that here, since I have a fair
number of custom build steps (python code generator scripts, plus yacc and
flex.)  

Naturally, setting that up would probably have taken less long than one I
actually did do, which was to rewrite my makefile for nmake (the little talked
about MS version of make).   Which took pretty much my whole day today, along
with fixing up the code to work with a compiler that is ANSI, except for
anonymous unions.  I was always intending to port to msvc, so I was trying to
stick to ANSI features, but it is one thing to try, and another thing to do.
But fixing this didn't take like, just a few instances where the variable
declaration occurred somewhere other than the start of the block.  I fixed the
lack of inline, by defining inline to be empty.  Since I only use static inline
functions, I'm not sure the inlining was really doing much anyway.  

# Got OpenGL Stuff Written

So, not sure where I was last time, but I actually have written bindings for a
rudimentary opengl rendering pipeline, that I am experimenting with in a new
project, I've been calling "blue_rect".  It is mostly just a FIAL demo.
Unfortunately, however, I hadn't gotten the chance to test the bindings before
all this wierdness happened, but having gotten FIAL back up and running, it
should now be a relatively simple matter to finish up with the next project.
But, that one requires external libraries, which will of course be different for
the different compiler.  So I have to track some stuff down, which should be
quite fun!

In all seriousness though, I am quite happy with how this has turned out.  I had
known that I no longer assessed mingw as being a production quality toolchain,
so the switch was somewhat inevitable.  

I am also going to give vim about a week to grow on me, if it doesn't drive me
bonkers and make me switch to notepad then I think I will keep it.  The main
problem with C programming is you have to push a lot text, so switching to
notepad or something like that would obviously result in a big productiviy hit.   



  
 

