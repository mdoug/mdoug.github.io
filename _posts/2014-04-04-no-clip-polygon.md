---
layout: post
title: No Clip Polygon
categories: blog
---
# Not Gonna Do It

Writing something that clips a polygon as an exercise is just nutty,
so I'm going to skip it.  I have a proc that determines if a point is
within a polygon, another that gets you the intersection of two lines,
they are both quite ok as examples.  

The main difficulty with this type of coding is that creating custom
types from within FIAL is a bit cumbersome.  This could be cleaned up
slightly, and probably would be made a fair bit easier with the map
initializers that I am thinking of adding.  But the important thing to
remember, is that FIAL is generally meant to work with types provided
via the C api, built-in types are more or less provided for the purpose
of allowing interaction with those types, and as a convenience.  

# Gonna Do This Instead

Instead, I am going to clip a polygon using boost::geometry.  It will
be a fairly straight forward exercise, which will do a much better job
of demonstrating FIAL's capabilities.  

It will demonstrate:

1. How to add C++ classes as types to FIAL.  
2. How to add C++ functions as C funcs to FIAL
3. How to inject the type value of a pseudo-type (a map with a
   registered type value mapped to the symbol $type) into a FIAL C
   library.
4. How to allow manipulation of a custom type via a FIAL interface,
   though of course, maps and sequences probably also count as
   examples of this.  But this is somewhat different, so it has value
   as an example.
   
Anyhow, this will also be a chance to test drive the boost::geometry
library, which is good for this example due to the ubiquitous nature
of boost (though, perhaps not so universal that I would consider it an
acceptable dependency for the core.  

# Bugger Got a Bit Drunk

Bought some beer and drank it.  But, I have been thinking about making
a dynamic link library as loadable from FIAL.  That would be
convenient, even though it isn't exactly fitting the vision of an
embedded language. 


