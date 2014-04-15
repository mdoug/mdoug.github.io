---
layout:     post
title:	    "FIAL Improvements, Alice Returns, Bought Secret World"
categories: blog
---

Why won't this post display?

# FIAL Harder!

I have done a ton of stuff with FIAL.  I added initializers for
sequences and maps, copy operators for proc arguments, and
initializers, assignments in variable declarations, and the ability to
use initializers as arguments in proc calls.

Some examples of new stuff:

    var new_var = {some_map_item = 10, another_map_item = {nested_map = $booya}},
    another_new_var = {$sequence, $are, $initialized, $too}

    new_var.another_map_item.awesome = {yet_another_map = "oh yeah!"}

    omni.print(::new_var.another_map_item.awesome.yet_another_map) /* prints a copy */

    var v
    omni.move(v, :new_var.another_map.awesome) /* retrieve nested map */

    some_proc({{$seq, $nested}, $in, $argument})

Anyway, as can be seen, the language is just a lot less inconvenient,
without losing its short, choppy, feel.  Still a couple of additions I
want, namely to deal with nested sequences and maps, something like an
omni take that allows a sequence of accessors:

    var compound = {1, 2, {map_item = {$seq, 2, 3, {map = {4, 5}}}}, 7, 8}, ret
    omni.take(ret, compound, {3, $map_item, 4, 2})
    if(not ret == 5) {
	"Well I'll be darned."
    }

So that is that.  Should be awesome, and it's the last thing that is
on my mind as a good idea, then it is time to put this theory in
motion.

# Alice: Madness Returns

This game is awesome by the way.  It's the perfect "whelp, I've got an
hour or so" type game.  The levels are neat, the story is, well rather
nonexistent, but sufficient to set good *atmosphere*.  Alice looks
good, the game plays really well.

I was kind of surprised that the reviews for it were only mid 70's on
metacritic, just goes to show I guess.  It probably got knocked down a
good 10 - 15 points just for being a platformer, when that is actually
something of an under served game genre.  The combat I feel like was
unfairly criticized, often called repetitive.  But honestly, I am
halfway through the game, and I am still fairly frequently challenged
-- different kinds of enemy combinations always seem to make things a
little bit different.

I guess I get it somewhat, it's not an "OMG I am going to dedicate my
life to the pursuit of mastering the combat in this video game" type
thing, but it certainly seems to provide enough challenge to keep
things interesting, and I'm only playing on medium.

# Good Games are Repetitive

But I would also just like to mention, that good video games are
repetitive.  They are ridiculously repetitive.  They should force the
player to fully understand every possible permutation of every game
mechanic, and they should be forced to demonstrate this knowledge, by
being able to perform tasks with them repeatedly.

The original FEAR was 15 hours of walking down hallways shooting the
same enemies, with the same guns.  Super Mario involved a lot of
running and jumping.  The original Ninja Gaiden on NES involved
playing the same level, over and over, for months at a time, while
your NES remained on, and was in retrospect probably a fire hazard.
Doom?  Tetris? WoW?  I could go on I suppose, but I'll consider the
point roughly established.

The habit of new games, is to introduce new mechanics, and then before
you get through the tutorial levels for them, discard them in favor of
different ones.  There often isn't any "game" to them at all, as soon
as a game is established, it is taken away in favor of establishing a
new one.

Maybe this makes for good entertainment, but in no way does it make
for a good game.  Games have rules, the rules stay the same.  The
levels change, the challenges change, the player gets better.

But the game stays the same, and for any good game, it can be
criticized as being "repetitive."  But this is exactly the point, the
different variations in how the game "plays out" in different
circumstances is what make the game interesting.  But, of course, as
soon as you grow bored, the game feels repetitive.

Well, maybe another way to look at it, is that calling a game
"repetitive" just means it is trying to be a consistent game, but one
which the reviewer finds boring.  And I suppose this is fine, as long
as it is kept in mind that calling a game repetitive, is not really
any more objective than calling it boring, since so many other great
games are repetitive, and great games precisely because of it.

In other words, "repetitive" is not, in and of itself, a criticism of
a game.  "The game feels unduly repetitive, because it's boring, and I
just want my cheevos already," might be one, but it is not an
objective one.  That a work of art, or entertainment, invokes boredom
in a viewer is of course a damning criticism, but I know of nothing
that is objectively *interesting*.

# Secret World

Well, I got the Secret World on sale, I think I'll give it a go.  I
don't think I will socialize much, because, well, fuck people.  But it
seems pretty interesting.  It was on sale for $10 so I decided to snap
it up.
