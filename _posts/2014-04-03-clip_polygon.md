---
layout: post
title:  "Polygon Clip Looks Hard, Didn't Start"
date:   2014-04-03 15:00:00
categories: blog
---

# Sigh

This clip polygon thing looks really hard.  I have it in C++, but that
code is really terrible.  But I don't really remember all the edge
cases, so I am just going to copy it, and then later on maybe refactor
it, if I figure out why I did it that way.

And my reward for doing this is to get to write some more
documentation for FIAL.

# Refocus

I think maybe I am going about this all wrong.  Yes, I made a
language.  Yes, it's awesome.  No, the point was never to make an
awesome language, I made it, because I needed something that did what
it does.  So I think it is best to get on with that stuff, even using
a langauge that isn't perfect.

Now, I'm not saying that what I am talking about isn't a good idea.  I
just think it will be a much better, if I have examples of real
programs that use it, rather than a couple samples, and a tutorial on
the wiki.

So, I do think I want to clip this damn polygon, after all this.  But
then, after that, I am going to get using it, and stop pretending that
making a programming language was somehow my goal all along.

# Comic Book Viewer

The next order of business in the comic book viewer is to get it so I
can write the rendering pipeline in FIAL.

Then, buttons and a bsic menu.  Then, maybe add background loading,
and threads, since that would be a good test.

# Game

Once I have a rendering pipeline, I can start working on my game.
Though, I think maybe I should hold off until I have a basic menuing
library, since maybe some of my design stuff will be the same for the
game input and output handling.

I have looked at the C++ code, I am not using any of that.  Complete
rewrite.  Since I won't have the FIAL compiler in time, most stuff
will have to be in C, or C++ if I need it to use a library.  But, I am
a better coder now than I was then, and since I already know what I'm
writing, I will hopefully be able to make relatively short work of it.
