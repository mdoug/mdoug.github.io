---
layout:     post
title:      "Tcl/Tk, the Boehm Garbage Collector, and a Text Editor"
categories: blog
---

Ok, it's early, I have a bunch of big plans!  These mostly revolve
around projects involving FIAL, my new embeddable scripting language.  

# Tcl/Tk

I haven't really done much with tcl before, except look at it like it
was funny looking, but I have taken a gander at it lately, and it
actually looks pretty cool.

One aspect of FIAL has always been that it would be easily embeddable,
and a general purpose scripting language is an example *par
excellance* of an embedding application.  But, the downside of this
has always been that writing bindings to these types of languages is
generally somewhat involved.  But with tcl, it seems very simple,
almost trivial.  Of course, I could be wrong, I have precisely zero
experience doing this.  I might have to beef up my string classes
somewhat, but nothing major.

This would essentially expose everything in Tcl to FIAL, which is a
big win!  The most obvious win is Tk, a cross platform gui toolkit is
hardly something I could provide on my own.  Also, it's my
understanding that Tcl has excellent string support, which is good,
because the 'A' in FIAL stands for "algorithmic", which is a big word
that means, "lackluster string support."

# Boehm Garbage Collector

Another thing I want to think about is writing something that uses the
[Boehm Garbage Collector](http://www.hboehm.info/gc/).  Now, a main
point of FIAL is that it avoids the need for garbage collection, or
for reference counting.  This is done to avoid placing design
constraints on the embedding application.

But this does not mean that the types provided by the embedding
application cannot be references, and that the objects that these
types point to, cannot be garbage collected.  And, in fact, these
usage cases are an anticipated use case.  

Reference counting schemes should be relatively straight forward --
just provide a finalizer on the type, that decreases the reference
count, and provide a copier, which makes a new reference, and
increases the reference count.  I do plan on demonstrating this
technique as I use FIAL for OpenGL rendering.  

Garbage collection, should still be possible.  Of course, writing a
garbage collector is a great deal more work than implementing a
reference counting scheme.  However, this is only true when reference
counting doesn't result in cycles, since cycle breaking is itself a
rather involved task.  Furthermore, in a multithreaded environment,
reference counts implemented with locks could be a bottleneck.  Atomic
operation are generally available, but I honestly have never done
this, it seems like the kind of thing that has a bunch of nasty
gotchas lying around.

In any event, the purpose of FIAL is to leave design decisions to the
people designing the embedding application, wherever possible.  This
includes the decision to use garbage collection on custom types.  But,
since I am not going to write a garbage collector, a demonstration
using the Boehm collector really is the best I can do.

# Text Editor

A programmer talking about text editors.  Thrilling.  But, I think the
point here is that I will write my own text editor!  So there!  That's
exciting, amirite?

## Unhappy with Emacs

I am not happy with Emacs.  Not really sure how else to put it, but my
relationship with emacs has always been one of "I think is slightly
better than the alternatives, but I really hate it."  Then my hatred
kind of mellowed, and now I have just gotten to the point where I have
decided, deep down that I will get away from Emacs as far as I can.  

Now, I won't delete it, there are some things it does really well -- I
have no problem keeping it around to use as a gdb front end.  But for
my main text editing, I have to get away from it, because I just hate
it.

## Need Something For FIAL

Since I am getting away from Emacs, hopefully sooner rather than
later, but in a gradual sort of way (one thing at a time!), and I have
to write a lot of tool chain stuff for FIAL at some point -- not only
a basic syntax highlighter, but I will probably need something that
can work as a debugger, connecting into an app through a socket.

Now, I can't find the motivation to write this stuff in elisp -- a
truly loathsome language -- when I am trying to get away from Emacs.
It just does not make sense.  But, at the same time, I don't like vim,
and I'm not sure it has the functionality I need anyway to deal with
the debugger aspects, so I think a stand alone editor might be just
what the doctor ordered.





