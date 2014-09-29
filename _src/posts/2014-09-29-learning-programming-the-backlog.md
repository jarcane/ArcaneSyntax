    Title: Learning Programming: the Backlog
    Date: 2014-09-29T23:08:19
    Tags: programming, learning

Thus far, I have been back to programming for a vanishingly small amount of time, roughly three months by Github commit reckoning (plus a bit of time spent in Codecademy). In that time it has seemed, to myself and even to others to a lesser extent, rather remarkable the amount of progress I've made. In just that three months and change I've written a roguelike game, an old-fashioned line editor, a text graphics wrapper, an esolang, a virtual machine, a basic weblog, and even taken over as chief maintainer of an open source project for the first time.

Thus by all appearances, it seems like I've already learned a lot, and in some ways that's true.

In other ways, it's not. 

<!-- more -->
What I have learned thus far, more than anything, is that in actuality for someone with a particular frame of mind and some grasp of logical thinking and problem solving, it is relatively easy to make a seemingly large amount of apparenty progress as a programmer in a very short span of time.

><J_Arcane>I've realized that it is very easy to get fairly far in programming with just a little bit of knowlege and some basic logic skills, but then when you start wanting to push just a bit farther than that, the whole sense of progress collapses like a house of cards ...

And the thing is, this can be a very dangerous trap, for learning anything. A crucial time, one I'm frankly wrestling with. When learning (or re-learning) a new skill, there's a point at which the "good start" you've made is actually a hindrance. You *can* become a programmer in 28 days.

You might even be decent at it, given some more practice, if you've the head for it and all you want to do is be a ["Blub"](http://www.paulgraham.com/avg.html) coder for life. In the old days this was how a lot of working programmers got started, and cubicle farms the world over are similarly filled with these. The local Java apprenticeship program I think lasts all of three months. Many so-called "hacker schools" and "bootcamps" more or less crash-course young minds through an easy language like Ruby or Python in a matter of weeks and send them off into the world $10,000 poorer and with all the coding knowledge of the average Codecademy user. 

To be a *good* one, though, even a *great* one, you need to be willing to set aside that "good start" and keep building back on the fundamentals again and again. And when you already have that start, when you already feel like you *are* "good enough," it's incredibly hard to force yourself to go back to feeling like you've no idea what you're doing all over again.

I programmed when I was younger, quite a lot in fact, and that skill never quite decays, so that plus some great re-introductory material seemed to be catapulting me into the stratosphere at a rate not dissimilar from my foray into book publishing. There was a window when I think I was even getting a bit cocky about it. Racket was good for breaking this. The basics of Racket are as easy to grasp as any other, probably the easiest Lisp to learn, with some pretty good intro books and guides. But those advanced topics, the language tools, the contracts, the dialects, all hang there in the Guide sidebar reminding you of just how much more there is to learn. And hanging out with the PLT crew, and the #esolang hackers, and other similarly smart folk (seriously the smartest people I've ever met in programming were either esolang nerds or Lispers or one flavor or another), is also hugely eye-opening for a cocky young sprat.

This is all one reason why I've picked up quite a bit of backlog of books to study, probably enough to fill a year's university curriculum at a minimum. Now that the rambling phase of the post is over, I thought it might be useful to someone or simply for posterity to catalog my current "learn stack". These are the books I want to tackle in the near-ish future, though in what order and which next is still the subject of some debate.

[How To Design Programs](http://www.ccs.neu.edu/home/matthias/HtDP2e/) - I've started this book twice. Both times I've got impatient or distracted and gone on to something that seemed to be leading me towards more direct progress; it has a very particular style of design it teaches that I found a bit odd, and the focus on "learning languages" was a bit frustrating when all I really wanted to do was learn more about Racket proper.

[Structure and Interpretation of Computer Programs](https://mitpress.mit.edu/sicp/full-text/book/book-Z-H-1.html) - Anyone who is reading this probably already is at least familiar with this name. It seems to be perhaps one of the most well-regarded books on programming and CS there is; almost no one I've ever spoken to about it had anything but glowing praise, even the ones who didn't even write Scheme or Lisp anymore. I'm definitely curious, especially as it covers a lot of systems programming stuff that seems to be where my mind wants to go as a programmer. (For similar reasons, I'm also really interested in [PLAI](http://cs.brown.edu/courses/cs173/2012/book/))

[Build Your Own Lisp](http://www.buildyourownlisp.com/) - An unusual approach for a new language introduction, this book aims to teach the reader C by walking them through the development of a dialect of Lisp. I'm a bit suspicious of some of the design decisions (it controversially avoids dealing with quote and macros by replacing them with something called "Q-expressions"), but C is a good language to know and this seems like a fun way to learn it. In a similar vein, there is [Write Yourself A Scheme in 48 Hours](https://en.wikibooks.org/wiki/Write_Yourself_a_Scheme_in_48_Hours), which aims to give a crash course in Haskell by teaching you how to build a basic Scheme interpreter with it. This leads to my next pick:

[Learn You a Haskel for Great Good](http://learnyouahaskell.com/) - I am deeply curious about Haskell, because I am deeply curious about functional programming and also by the unusual arcaneness of it. This book seems to be a fan favorite, as it were, and the tone is certainly inviting. There's also an [Erlang book](http://learnyousomeerlang.com/) inspired by it, which I'm more interested for professional reasons: it was invented next-door, as it were, so there's a fair number of jobs about in Erlang still. 

I think the next book I tackle will be one of these, I just haven't decided which yet. I'm very open to advice, so feel free to leave your thoughts in the comments, as opinionated as you like.
