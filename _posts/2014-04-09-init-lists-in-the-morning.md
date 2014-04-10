---
layout:     post
title:      Init Lists in the Morning, OpenGL after
categories: blog
---

Ok, starting out my day with a blog entry, as I've been trying out for
the last week or so.

Big plans today.  Again.  These never quite seem to get finished
properly, but I am pretty sure I can get the first item done in the
morning here, and it will be good.

Today:

1.  Initializer lists for FIAL
2.  OpenGL rendering pipeline

More Stuff (probably not today) :

1. Switch from bison to byacc
2. Box2D bindings.  After this is done, I will already have something
   of a 2D engine, along with the OpenGL stuff.

# Init Lists --

I've already tested out the grammer by running it through bison.  Ran
without errors.  But, now I have to hook in the rules, add the AST
nodes, and add code to interpret the assignments.  

Sounds like a fair bit, but I hope it'll be straightforward.

Oh bugger.  I just thought of an ambiguity now, I know I knew this at
one time, I think it was in relation to arguments (which is why I
decided to only allow variables, and not expressions, as
arguments). Well, I guess it's not ambiguous, the problem is that I
want it to mean two things, when in fact it doesn't, it just means one
of them.  Hopefully this illustrates it --

     var value
     
     set_value(value)
     seq = {12 + value}  /* this could be an expression error */
     seq = {value}   /* see, here value, by itself,
                        could be either an expression,
			or this newfangled "lookup id and then 
			move the results" thing.  */
     seq = {::value}

For sequences I could probably fix this just by requiring a ":" --

    seq = {  value}   /* expression evaluation of value */
    seq = { :value}   /* omni.move(value) */
    seq = {::value}   /* omni.copy(value) */

For Maps I could introduce an '='

    map = {sym =  value}  /* expression evaluation of value */
    map = {sym :  value}  /* omni.move(value) */
    map = {sym :: value} /* omni.copy(value) */

My main problem with all of this, is that at some point I may want to
apply this type of thing to proc arguments, but they certainly don't
seem applicable, because pass by reference is denoted by a naked
identifier.

    proc( arg1, arg2 ) /* arg1 and arg2 are passed by reference */

So there is no easy translation between these two things.  There are
currently plans to provide for "extra" arguments to be passed via copy
or more, by a declaration in the proc def --

    proc ( arg1, arg2 : extra_args ) {} /* arg that essentially deletes
    	   	                           everything but arg1 and
                                           arg2 */

But this notation is also not really set in stone.  

In short, I think I am back to the thinking stages on this.  I will
probably just put it in as indicated, and hope that some clearer
syntax presents itself for dealing with proc arguments.  I am quite
happy with the way it is, but still, more options could be convenient.  

Oh, closing thought:

    proc_call (reference, {evaluation}, :move, ::copy)  /* maybe? */

# OpenGL stuff

Well, it is becoming apparent that there will be some movement on the
FIAL front, but I don't know that anything that is currently in the
language will be readily changed, and besides, I still just
constructing types.

So, OpenGL stuff is a go for the day.  Will think about the language
additions for another day, before getting started.  

