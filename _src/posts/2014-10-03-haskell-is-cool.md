    Title: Haskell is Cool
    Date: 2014-10-03T23:25:10
    Tags: Haskell, Racket

After my last post and some thinking, I ultimately settled on *Learn You a Haskell* as my next book to work through, and after some initial hassles trying to get a decent working environment set up, I must say that I'm quite enjoying the language itself. It was running across [Try Haskell](http://tryhaskell.org/) that actually spurred me to finally take the leap in that direction (seriously, online REPLs are the best language demos period), and I was quickly impressed by the power hiding in that seemingly obtuse syntax.

And of course, like everyone else ever (so many that *Learn You a Haskell* actually makes a bit of a joke out of it), I was impressed as hell with the Haskell quicksort solution.

But after some tinkering in Racket, not for precisely the same reasons as the book uses it.

<!-- more -->
For reference, the Haskell recursive quicksort looks like this:

```haskell
quicksort :: (Ord a) => [a] -> [a]
quicksort [] = []
quicksort (x:xs) =
    let smallerSorted = quicksort [a | a <- xs, a <= x]
        biggerSorted = quicksort [a | a <- xs, a > x]
    in smallerSorted ++ [x] ++ biggerSorted
```
I know, right? It's short and sweet, and using multiple recursion and list filtering to solve it takes a hell of a lot of the work out of it. Hell, this is actually the first version of quicksort I've ever understood; though in my defense the last time I tried to write a quicksort was some 15 years ago as a teenage BASIC hacker (I failed. Repeatedly.)

The book of course uses it as an example of the power of recursion, and it is indeed a good example of where clever use of that can do a lot in very little space (though personally I think the lazy factorial method is a cooler example), but the thing is that any language that implements good recursion can do the same algorithm and just as fast.

For instance, Racket can do the exact same algorithm in just a few more lines (most of them in this case for clarity and convenience, semantically it's *almost* identical [but not quite, and I'll get to why]).

```racket
(define (qs lst)
  (if (empty? lst)
      lst
      (let* ((hd (car lst))
             (tl (cdr lst))
             (smaller (qs (for/list ((i tl) #:when (<= i hd)) i)))
             (larger (qs (for/list ((i tl) #:when (> i hd)) i))))
		 (flatten (cons smaller (cons hd larger))))))
```

So clearly, it's not exactly the *recursion* that makes the example so cool. No, what makes the Haskell version cool is when you realize what it can do that our Racket port can't: anything but numbers. The Haskell quicksort can readily handle numbers, strings, or lists of chars, all thanks to the power of this line right here:

``quicksort :: (Ord a) => [a] -> [a]``

*Especially* the ``(Ord a)`` bit: that's the Ord typeclass, which imports types that Haskell knows how to put in order, thus allowing a statically typed language to still nonetheless use the same <= operator regardless of what type is actually being fed it (the other part of that feat is the ``[a]`` bit, the generics).

To be able to get a similarly powerful, if not as convenient function, we have to upgrade our Racket version a bit:

```racket
(define (qs-2 fun lst)
  (if (empty? lst)
      lst
      (let* ((hd (car lst))
             (tl (cdr lst))
             (smaller (qs (for/list ((i tl) #:when (fun i hd)) i)))
             (larger (qs (for/list ((i tl) #:when ((negate fun) i hd)) i))))
        (flatten (cons smaller (cons hd larger))))))
```
Now our Racket quicksort has become a higher-order function, and must be passed the less-than function it will use to find *smaller* as well as negate to find *larger*. But it's still not exactly replicated the feat that Haskell's version would, and doing so directly would mean a whole range of type checks. It is almost certainly possible, but not in so concise a manner.

And of course, some of this difference comes from Haskell's special little rules, like lists being mono-typed elements (as opposed to Racket's free-wheeling ones); this is more limiting but also means that functions like quicksort can largely be written to assume a list will behave with it. If we pass it a list from elsewhere in our program, it will still work as long as its members are members of Ord.

The amusing footnote to this is that the easy solution for Racket is to make it a higher-order function (and in fact, this is even what Racket's built-in [sort](http://docs.racket-lang.org/reference/pairs.html#%28def._%28%28lib._racket%2Fprivate%2Flist..rkt%29._sort%29%29) does), whereas in *Learn You a Haskell* the author doesn't even get to higher-order functions until the chapter after the quicksort example.
