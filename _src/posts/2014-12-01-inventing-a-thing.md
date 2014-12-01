    Title: Inventing a Thing
    Date: 2014-12-01T20:39:05
    Tags: Heresy

One of the more ambitious features I decided to attempt for Heresy was to create a new kind of struct-like syntax that would be easier and faster to use in-place in a functional style. Racket has a very robust struct system which I was initially quite enamored of, but which I soon discovered could get quickly cumbersome to deal with. For Heresy, I wanted something simpler.

So, some days ago I wrote myself [a spec](https://github.com/jarcane/heresy/issues/5) for something called "Things," but set it aside because I was largely convinced it would take a considerable amount of wizardry to pull it off. The spec contained a considerable amount of functionality, from pattern-matching syntax to inheritance and on.

I was wrong. It took me half a day. And [only 29 lines of code.](https://github.com/jarcane/heresy/commit/7dd1456cbeae767be786cbeb94d40c5ea645f325) 

<!-- more -->
Part of the secret of course to this was actually in the reading and studying I did trying to learn more about combinators and other such lambda-based wizardry. It took me about a week of gestating, but what I realized is that what I needed wasn't a static data structure with some macrology attached to various names, but actually, all that syntax needed to live in the data structure itself. Then inheritance and renaming and copying and all that fun stuff comes for free.

The result is Things. We can define a new kind of Thing:

```racket
(describe Cthulhu (size 'Immense) (type 'Winged) (status 'sleeping))
```

We can call values from Cthulhu:

```racket
> (Cthulhu 'size)
'Immense
```

We can copy Cthulhu with new values:

```racket
> ((Cthulhu * * 'awake) 'status)
'awake
```

We can give a new name to Cthulhu:

```racket
> (def Dreamer Cthulhu)
> (Dreamer 'type)
'Winged
```

And we can make children of Cthulhu:

```racket
> (def Star-Spawn (Cthulhu 'Medium * 'awake))
> (Star-Spawn 'size)
'Medium
```

So how does it work? It's all just a lambda. (describe ...) is a simple macro wrapper that defines a name and seeds it with a call to (thing ...), which is a helper function that returns a lambda containing a closure that holds the actual alist that holds our values as well as the argument handling code for calling and copying it. Indeed, copying Things is just a recursive call to Thing with new values, and (thing ...) can potentially be called anonymously just like lambdas can. And because functions are first-class values, inheritence and value-passing just come with the territory.

There is one weakness though:

```racket
> Cthulhu
#<procedure:Cthulhu>
``` 
Because Things are just lambdas underneath, they read naked as procedures, so they are not immediately transparent.

Instead, we have to do this:

```racket
> (Cthulhu)
'((size 'Immense) (type 'Winged) (status 'sleeping))
```

Though on the upside, this is not merely a print routine: It actually returns the naked alist underneath the snytax sugar, so you can mangle it with assoc and subst or whatever other unspeakable horror you wish to do to the Great Dreamer in the Deep.
