    Title: So I made a programming language. Now what?
    Date: 2014-11-18T12:32:32
    Tags: Heresy, Racket

About a week ago, I had a ridiculous idea. I was in the process of learning some basic Racket macros, and also still following the progress of a couple vintage Lisp dialects for the Tandy Color Computer. Even played around a bit with XLISP in OS-9. And then someone asked me what a Lambda was.

Somehow, in the fog of all that (plus a week with a hell of a lot of stress, mostly irrational), came a mad idea. What if someone mashed up BASIC with Lisp? Stranger still, a functionally-oriented BASIC Lisp. 

Then I went and wrote one.

I called it [Heresy](https://github.com/jarcane/heresy), because that seemed like the right name for it.

<!-- more -->
With help from a few helpful Racketeers in IRC, I now have a functional dialect of Lisp that borrows heavily from BASIC syntax; a kind of "Nutrasweet" syntax married with immutable variables and some (I'd like to think) vaguely clever use of seemingly imperative constructs executed with functional code.

It is also now the most well-recieved project I've ever released, netting 18 stars on Github, almost 3,000 vistors to the repo, and a whole day near the top of Hacker News' front page.

Now, don't get me wrong or think I'm letting it get to my head (well, I probably am a little). I fully expect that many of those clicks were more at the very novelty and silliness of the idea. But as ideas go, I've seen dumber ones succeed, and it's been a useful learning project that fits nicely into my current schedule. The question is though, what do I do with it? Where do I want to go? Is Heresy a way to ease BASIC programmers Lisp? A playground for weird ideas about functional programming?

Time to establish some ground rules.

1. *Heresy is BASIC* - Heresy is an heir to BASIC, and aims to be at least somewhat easy for BASIC programmers to learn. Mostly this means we prefer BASIC names over the Lisp name, and naming conventions like the $ for string functions.

2. *Heresy is a Lisp* - Heresy is still a Lisp, and loves simple syntax and s-expressions. While it makes use of some sugaring like literal keywords for certain common primitives, these are best used sparingly. Heresy is the Diet Coke of Evil, just one calorie, not quite evil enough.

3. *Heresy is functional* - Functional, but not Haskell. It is not intended solely as a vehicle for absolute functional purity. I love Haskell. You love Haskell. We don't need to write another Haskell. Think more in terms of a lower-calorie, more intelligible Clojure. 

4. *Heresy is for learning* - Heresy started as a learning project for me, a chance to learn how Lisp and functional programming really work on a practical level. I hope that, in time, it can be that for others as well, especially those who grew up with BASIC like me and still sometimes struggle to get their head on this brave new FP world we live in now. 

5. *Heresy is an experiment* - Heresy is an experimental language. It's very DNA is as a mad idea that came to life, and it's development should be ready and willing to embrace new mad ideas and run with them. This is where *carry* came from, and I hope to have more mad ideas in the future. 

Those are my thoughts for now though. I would like to point your attention to #5 in particular, because one of it's side effects is that any or all of these rules probably will change or be ignored as necessary over time. It also leaves out some things I haven't decided yet, like how much of Heresy should be self-hosted (probably as much as can be borne), or a more specific syntax standard for function names (because ? for preds still looks wrong and un-BASIC to me).

Heresy is the projection of a fevered imagination still buzzing away with strange new ideas. Think of me less as a BDFL and more of a Mad King gibbering in the dark, still sometimes speaking truth in between the deranged quartos and evocations of elder things from beyond time and space ...
