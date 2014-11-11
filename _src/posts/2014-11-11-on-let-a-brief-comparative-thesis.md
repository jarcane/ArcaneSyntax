    Title: On LET: a brief comparative thesis
    Date: 2014-11-11T08:56:05
    Tags: Racket, programming

I started programming, as many people my age did, as a kid, with a computer running Microsoft BASIC. Disk Extended Color Basic on a Tandy Color Computer 3, to be precise. I wrote quite a few programs, large and small, as well as modding a few others that came on various Rainbow disks I'd cobbled together mostly from either the Internet or an uncle who was far more invested in the scene.

Thus, when I at last discovered the introduction to macros and language definitions in _Realm of Racket_, it struck me that it might be interesting to practice those tools by experimenting with defining a BASIC-Lisp hybrid which I am tentatively tempted to entitle "Heresy".

I'm still in the research stages right now, though I'm putting code to file today, and in researching how to map keywords from one to the other I discovered a very important clash: LET.

<!-- more -->
Besides the obvious math operators and so forth, LET is one of the few standard keywords that exists in both BASIC and Lisp languages, but both could not possibly seem to describe more polar opposite functions.

LET in BASIC is the somewhat deprecated global variable declarator and assigner. Ie.:

``LET X = 5``

LET in old-school BASIC is probably closer in function to the old Lisp keyword SETQ, in that it is used both to explicitly declare a new variable, but also to set that variable to a new value. It's also distinct from DIM in that DIM was primarily used to declare arrays until much later dialects like QBasic and Visual Basic, and also because it must explicitly assign a value.

LET in Lisp and Scheme however exist to provide temporary names for local values, usually within a function or a macro. They almost provide for variables what lambdas do for functions, and even allow the definition of new functions as well (either through explicit syntax for this, or by taking advantage of lambdas).

And yet ... look back at that syntax for the BASIC version again. Both of these terms are coming from the same place: algebra. I am willing to bet that nearly everyone reading this write now has done at least one problem, probably thousands, that started with some statement of 'let x equal ....' Wiktionary even cites this in the definition of the word as an example: "Let P be the point where AB and OX intersect."

There is of course a reason for this. Lisp is famously based on Church's lambda calculus, and its mathematical pedegree is hardly a secret. Dartmouth BASIC meanwhile was originally made mainly to help students do calculations for their homework assignments, the terminology springing directly from the pages of their algebra and trigonometry assignments.

And it's in this historical meeting point that we can ask ourselves a question, and answer it.

Question: how did these two uses of LET evolve into such polar opposites?
Answer: They didn't. They both mean the same thing; it's their approach to problem solving that's different.

Wait, what?

It's true. If you go back and look at the exercises and code samples and tools offered in the original Dartmouth BASIC, you realize something about what BASIC programs are meant to be, vs. how Lisp programs are generally approached. Dartmouth BASIC was written for tiny problems, word problems. The domain of a BASIC program was expected to be a single problem, and so the syntax and semantics both were constructed with that goal in mind.

Lisp on the other hand, while it has diverged over the years into many approaches from the purely functional Clojure to the 'basically just rewritten C' of some Emacs-Lisp code, still fundamentally it comes instead from a logic that was about breaking down one big program into many littler problems, each of which may potentially need to define it's own local variables.

It's not that LET necessarily means something different etymologically here, both creators were ultimately seeking to define the same tool, but the difference in how they actually work on a practical level and how they came to act as keywords in two very different ways, has more to do with how they approach problems as discrete pieces.

In the past I've often defended BASIC, in part on the strength of the revisions made in more purely proceduraly dialects like QBasic, and in part because we BASIC 'hobbyists', shunned away as we were by the C coders and the elite ASM hackers of the day and since, really often could write code just as procedural and well thought out as any. It's just that the dirty secret, what those sneering outsiders could see that we couldn't, was just how much we were working *against* the language to do it. BASIC was asked, and somehow managed, to do things and solve problems far in advance of the scope for which it was ever designed.

There is actually tail-call-optimization and code for writing recursive macros in *FreeBASIC* now (there are, amusingly enough, even a couple simple Lisp interpreters, even an embedded scripting language in Lisp for FB). Of course, this is in FB, a modern dialect of the QBasic branch with at least something more resembling a modern approach, but it still illustrates the fierce devotion that BASIC fans were almost *driven to* by their reputation in the wider community.

These days of course, I look at even QBasic code and shudder to think, but then I also feel the same way looking at Java. And while Heresy kinda started as a joke esolang idea and may stay that way, it interests me to wonder if a "Lisp-flavored BASIC" might be a genuinely useful dialect for introducing those die-hard BASIC coders to the flexibility of a language that is not still fighting attempts to use it for more than solving simple algebraic equations.

Of course, I still haven't decided which definition of LET to stick to.
