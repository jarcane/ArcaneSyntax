    Title: Choosing a Lisp
    Date: 2014-09-15T23:22:25
    Tags: Lisp, Racket

I began my adventure back into the world of programming with Python. My last book had started to peter out in sales, and I began seriously re-evaluating my career potential, and it was at this point that a friend introduced me to [Codecademy](http://codecademy.com). I was immediately taken with the interactive approach to programming instruction, and in particular gravitated to Python, because it was a language I'd tinkered with before and whose power, especially in strings and lists, I'd always been impressed with.

I devoured the Python course greedily and soon moved on to my first "big" project, [handhRL](https://github.com/jarcane/handhRL) a roguelike based on one of my tabletop rulesets. However, as I grappled with the tedium of building random object generators with massive elseif-based constructor patterns, and the poor performance and gaming potential, I also was acutely aware I'd need to branch out into other languages.

And then another friend recommended I try Lisp. I consider it a fateful day. I'm not honestly certain whether to curse him for it or thank him. I tried a number of entryways into the world, and indeed, choosing which Lisp to focus on has consumed much of the last two months of my time. I fall more in love with Lisp the more I learn of it, but choosing a flavor of it has tormented me more than perhaps it should. 

Here's what I have learned.

<!-- more -->
There are a dizzying array of Lisps out there, but by and large the main options boil down to the following:

* Common Lisp
* Scheme
* Clojure
* Racket

There's more of course, Paul Graham has Arc which powers Hacker News, there's the venerable Emacs Lisp that powers the very editor I write these posts on, but those four are probably the most prominent and feasible for at least some practical amount of actual work.

I started with Common Lisp. Or at least, attempting it. I suspect many people do, those that don't instead get exposed to Scheme in college. I suspect now I understand why so many come away with a bad impression. Common Lisp is far easier to learn now than it was 10 years ago, but it's still a dialect built on compromises and mired in ancient and cthonian syntax. I found myself stymied by having to learn 12 different ways of doing any given thing, and by chapter-long exercises done entirely in a REPL that then crashed or fell victim to an error somewhere back on page 2.

So, from there I cast around and found Racket. And lo, the heavens did open, and mine eyes did see the light. While I did catch glimpses of the power of Lisp with my initial toolings, it was in the purity and clarity of Racket, in its wonderful documentation, in the easy power of the Lisp-1, that I found the full breadth of what I'd seen as I stumbled through the CL wilderness. I played and tinkered and hacked. I wrote an [8-bit VM](https://github.com/jarcane/MicroMini) in just 206 lines of code. 206!

But I stumbled as well. I ran into problems implementing terminal i/o with my virtual machine, so it would only run in Linux. I found myself frustrated by the lack of mature development for pretty common "getting work done" tasks, at least for the kind of work I wanted to do. As well, I found myself stymied by the books and documentation; put off by the beginner material, but utterly baffled by the advanced features.

I made another run at Common Lisp, getting pretty far in Peter Seibel's excellent [Practical Common Lisp](http://www.gigamonkeys.com/book/). Ultimately though, more exposure to the many-splendored weirdness of CL ultimately lead me to think perhaps it just wasn't the flavor for me.

Another friend had mentioned Clojure. I was put off by Clojure up until now, because it reeked of startup culture and I frankly have a long-standing grudge against Java. But Java is practically the reigning Lord and Master of the mobile-heavy Finnish scene, and it seemed to be driving a lot of new adoption locally and even a few actual jobs.

So, I discussed it with my wife and we mutually agreed I should give it a shot. I meditated upon the [ClojureScript Koans](http://clojurescriptkoans.com/), and was initially quite intrigued by its #() and its funcional purity, if a bit baffled by the sheer number of different data types, and put off by the ugly syntax. I code-golfed a FizzBuzz in a tweet done in CS. I then thought I should meditate upon the full [Clojure Koans](https://github.com/functional-koans/clojure-koans) in order to learn those things which CS had by necessity neglected.

By the end, the only "enlightenment" I found there was the cold burning focus of pure fury. I hated its clunky implementation, it's utter violation of the purity I so loved in a Lisp. I hated how utterly inconsistent everything was. I hated how any error could spell utter doom to your entire system, as typo'd recursions led to full CPUs and runaway threads. I hate hate hated the threading macro with the fire of a thousand incandescent supernovas.

However, it also gave me a sense of perspective, and so I meditated on the [Common Lisp Koans](https://github.com/google/lisp-koans). There I faced a an anticlimax. The final meditation was on SBCL threads, and SBCL threads were like grasping a stream of water. I had recieved all the enlightenment that Common Lisp seemed ready to offer.

And in the end, all I wanted was my Racket back. The prodigal son wanted to come home.

I am sure that in the cold light of reason I could find work in Clojure or Common Lisp. I do indeed envy their library support, and have come to respect a number of those features that they offer, and may even seek to reimplement some of them in my own Racket set up.

It is true as well that Racket is not well represented in the world of working programmers. But it is well represented in the world of computer science, a world I increasingly suspect I might like to enter if I should prove worthy. While there is something of a gap between the "beginner" and "advanced" levels of the Racket world, the flipside to this is that it is stuffed with incredibly brilliant people who are almost to a one the most polite and helpful people I've met since returning to programming.

So, with at least a year of language courses before I can even think about a job or university, why not hang around and contribute and learn in a place where I feel most at home? It was Python being this for me that made me a programmer again, and I think it could be Racket doing so that makes me a *good* one. 
