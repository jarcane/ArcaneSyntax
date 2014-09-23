    Title: Announcing try-racket.org
    Date: 2014-09-23T20:10:45
    Tags: announcements, Racket

It is my pleasure to announce that at long last, Racket has an online REPL. I've taken it upon myself to acquire a domain and a DigitalOcean droplet, and hosted the long-mothballed Try Racket code which you can find at <http://try-racket.org>. The PLT folks have also kindly offered an alternate URL at <http://try.racket-lang.org>.

I've also taken up the responsibility of maintaining the code: I had to fork it by necessity to modify some things necessary to get it to run without X, and as the original maintainer had no interest in pursuing it further than that, he asked me if I'd like to take over. You can thus find my fork of it [here](https://github.com/jarcane/try-racket), where future issues and development should take place.

The code's still a bit rough, with a number of issues to be resolved, and I welcome any and all contributions to the code; pull requests will be tested and then accepted so long as they don't appear to be breaking anything. In particular, it seems the memory constraints for the sandbox need revision to prevent a server crash, and there is some amount of demand for proper multi-line entry in the style of the offline Racket REPL. The tutorial is a bit tedious without it at present. 
