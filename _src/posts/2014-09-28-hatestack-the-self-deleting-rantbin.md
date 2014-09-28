    Title: HateStack: The self-deleting rantbin
    Date: 2014-09-28T23:13:13
    Tags: announcements, Racket

Inspired by a tweet that Zoe Quinn made the other day, I knocked out a little web app over the weekend for a self-deleting public blogthing. The original spec was a social network that worked like a SnapChat for text, in which the user could post an angry rant with the assurance that it would be automatically deleted in 30 minutes' time.

Taking that a step further, in part to limit its utility for nefarious purposes and also in part to keep the project simple, I adapted this to a single-page stack model, with post contents dwelling entirely within memory to ensure maximum privacy. Gone is gone, here, no database remnants or temporary files.

The result is [HateStack](https://t.co/bX5kiqZSm7), a simple Racket web application in a single 172-line file, with layout assistance from Bootstrap (helpfully imported by BootstrapCDN). It's not yet hosted anywhere; to be honest I'm not in a great hurry to go wrestling with yet another server when I've still probably got work to do on [Try Racket](http://try-racket.org). But it was an interesting little project that gave me a chance to tinker a bit more with my HTML/CSS skills, and thus be reminded why most of the time I play around with almost anything else besides web applications ...
