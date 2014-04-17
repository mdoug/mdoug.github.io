---
layout:     post
title:	    "Tried Secret World, Crossroads"
categories: blog
---

I have one nagging thing to add in to FIAL, the omni.put/take/dupe
methods.  (No need to duplicate in, since the copy operator can be
used.)

Then, my language is fully ready to go.  I think the next logical
place to take this, is to create an OpenGL api, that allows the
rendering pipeline to be written in FIAL, like Ogre's compositor's
scripts, only Turing complete, and with access to game state if so
desired.

Another place to go with this, is in fixing up some buttons for the
stuff I have already in bcve, which would be the next logical step
there.  But -- since a lot of stuff has to be rewritten for that, I
think I might as well just "start over" as far as the source code is
concerned.  I.e., I think a complete rewrite at this point is
appropriate.

# Secret World

I got started playing the Secret World, I think MMO's just aren't my
thing, they just take too long.  I mean, not like dark souls too long,
i.e. they take forever because you suck but some body out there can
speed run the whole game in 2 hours, just too long in the minimum
amount of hours required to complete the content.  

I think this is called "grinding," and its very important to the
makers of these games that you can't grind too quickly, because some
of the draw to it, is that some people like to have a bunch of stuff
that takes a lot of grinding to get, and they don't want other people
to have it, because they want other people to be jealous of them.
Obviously, whenever psychological motivations are described, they have
the tendency to seem like they are belittling the people who possess
them, and that is not really my intent.  Rather, I am just trying to
say that MMO's are designed to provide appeal to people who have
motivations that I don't have, and that in doing so, they intentionally
produce a game that causes me inconvenience, in order to appeal to
other gamers who gain psychological satisfaction precisely from that
inconvenience.

Obviously, no one cares how shiny someone's sword is in an MMO, or to
be more precise, the vast majority don't.  But due to the nature of
MMO's social interaction, whether or not other players actually feel
jealous of players who have achieved something through grinding is not
relevant, what is relevant is whether or not, on a psychological
level, the player who has achieved it believes that other players are
jealous.  These "hardcore" MMO players are desirable customers,
however, as more casual gamers will simply pay money until they get
bored, and then switch to something else.  They have to be constantly
convinced that the game is worth their continued time, whereas the
hardcore player doesn't, because he has already invested time, energy,
and money into his character in this game, making continued investment
predictable.

# Secret World Seems Pretty Ok Though

I played the demo of defiance a while back, and this is somewhat
similar in that it feels somewhat like a single player game, that is
also an MMO, as opposed to a game in which MMO features predominate.
In other words, I more or less can play it as a single player game,
with just the occasional interaction with people.

I don't know what anything does, or if I'm playing it right, and it
seems like I am going to have to re-roll at some point pretty soon.
The main thing I didn't realize is that cosmetic features are actually
really expensive to change, since armor is talisman's, and talisman's
are invisible, there is no game play need to look different, other
than you are tired of looking at the hoodie you threw on in character
creation just because it looked ok and you wanted to get the game
started.  But because of this, clothing is expensive in in-game
currency, because they offer clothes through the real money shop,
which people view as acceptable because they aren't paying for an in game
advantage, just customization.

# Ok, Now What

Ok, I just have to finish that last thing in FIAL, and then I have to
sink my teeth into something.  I am leaning towards making a simple
OpenGL game using Box2D.  This would be relatively doable, pretty fun
to make, and the code would hopefully be reusable. 

