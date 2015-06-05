    Title: First week on the job
    Date: 2015-06-05T15:10:15
    Tags: Clojure

It has begun.

In accordance with my education in the Finnish language, a portion of time, about two months, has been set aside over the summer for the students to take a "work trial" at a Finnish workplace. Owing to my powerful disinterest in winding up spending my summer stocking shelves at a supermarket, I naturally was quite on top of attempting to find some more suitable environment for a budding programmer, which I'm delighted to say I did.

The work place in question is a firm called [Metosin](http://metosin.fi), a Clojure consulting firm stationed right in the heart of the city, and this week was my very first week on the job. It had, as it was, been a little while since I dove into Clojure (which anyone who's actually read any of this blog, ie. no one, is likely to remember), so prior to starting the job I dove into a couple web apps in anticipation of my arrival and future employment.

For starters, I did Ludum Dare this year, banging out a spiffy little Pokémon themed idler game in Hoplon, which you can find [here](https://github.com/jarcane/trainers-progress). Hoplon is an interesting framework, whose concept I was initially quite excited by, an excitement whose dwindling you can perhaps most likely best glean from the fact that when for my try-out task for Metosin it was suggested I use Reagent instead, I was actually more than a bit relieved.

This task took the form of a full-stack weather look-up application, which I in my infinite nerditude decided to call [wunderprojectj](https://github.com/jarcane/wunderprojectj), a reference so unutterably obscure than I'm pretty sure no one even noticed, and if you did, perhaps I shall consider buying you a beer (and then backing slowly away into the night).

Since my official start date, I've been at work on a simple CRUD sort of a web app for managing members of a matrikkeli organization (a term which I am obliged to indicate I'm not entirely sure there's a direct translation for, but that doesn't really matter for the purposes of this blog anyway).

It's been suggested I keep some kind of log of how the work is going and what I've been learning, so after the jump, I'll get on with how my week's been going.

<!-- more -->
The app is, by the description of my fellow co-workers, quite simple, which is to say, by the standards of anything I'd had a personal hand in previously, it is enormously complicated. Or at least, that's how I felt for the first two days on the job, especially as initially my suggested task was first porting the entire front-end from Om to Reagent. I spent the bulk of the first few days just trying to get my head 'round the organization of the code base, and reading reams and reams of documentation on various libraries trying to come to grips with the moving parts and how such a task might even be approached. I had a hell of a time finding a whole lot of anything from anyone who's actually made such a transition, and Om and Reagent do things in very different ways; besides which I had trouble even finding many examples of an application of this scope written in Reagent. I actually wound up banging up an incredibly primitive toy Reagent app just to figure out how to refer to a single state atom across multiple files. You can see that [here](https://github.com/jarcane/multipage-reagent) for what it's worth.

In the process, I did manage to fix a couple of bugs with the user profile image display and upload, one of which (with help) was discovered to be the result of an API refactor that'd never been translated to the actual front end calls, and the other of which was a failure in the image validation which more or less turned the image upload into an accidental file hosting service. 

Eventually after some discussions mid-week with the rest of the crew, the scope of my responsibility was narrowed down instead to new feature implementation, which has gone a bit better, and given me a bit more opportunity to really get used to the project organization and so forth. I managed to implement a user status flag and interest tags on the back-end, and search for the latter on the front-end. Sadly I've so far not yet found a way to making those user tags user-editable yet, partly I suspect because I'm having a bit of trouble following the libraries used for the user profile form. My intent is to keep at it though, at least to get some kind of rough working prototype.

At this point it's difficult to pin down exactly how much I've learned from all this, but I've certainly been exposed to quite a lot of new technology, and I'd like to think I'm getting a bit more comfortable with the work at least so far. On the whole, not totally unproductive for a first week. 
