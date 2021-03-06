---
layout: post
title: Tuesday, March 29th
date: 2016-03-30
---

Using VIM without arrow keys and reliance on insert mode slows me down
quite a bit. A lot the work I was doing this morning was pretty
repetitive so it was a good  opportunity to observe what commands I
could benefit from. I made mental note of a lot of the things I found
frustrating or particularly slow, but I never really consulted the docs
or web to try and figure out a more efficient way, rather I relied on
more of the basic commands I happened to remember. VIM also isn't ideal
in Intellij despite my efforts there is still quite a bit of mouse work
and it's hard not to fall back into old habits.

Several vim commands I found myself leaning on:

> y, Y, yy = all variations of yank aka. copy
>
> D, dd, x = several variations of delete
>
> p, P = paste of course
>
> ciw = change delete one word and automatically go into insert mode to
> type another

The Zagaku today was on working remote effectively. Even though it was
on a "softer" subject I found it helpful since It emphasized
communication, which is something I think I can improve quite a bit on.
Considering, most of the interaction with my mentors is remote
communicating effectively is key to getting all-important feedback. So I
think moving forward it would make sense to share more with my mentors,
even if I think it might be too much. I'm sure they will tell me if it
is. In the same vain, I think I could make my workflow more
communicative as well by committing more.

As I work towards 100% test coverage, I'm learning more and more about
what it does and doesn't make sense to write unit tests for. In almost
all my classes I neglected to write tests for exceptions i.e. in a
try-catch block I have no tests that validate the behavior in the catch.
Since this is a potential "end-condition" for many of my methods it
makes sense to test it. I also learned that instead printing to
System.out as I normally might, it's better and more conventional to log
errors using a logger. Potentially, more on that tomorrow, as I dig into
the implementation details.
