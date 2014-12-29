    Title: A resume and a code example in one
    Date: 2014-12-29T18:04:20
    Tags: Heresy, programming

Recently I asked on Twitter about whether it was possible to find work in functional programming without a degree, seeing as I'm a functional programmer and I don't have a degree, and was pleasantly surprised to be contacted by a recruiter who provided some very useful advice on which languages to look into.

They also asked for a resume, which suddenly brought me to the realization that I hadn't actually yet written a programming-oriented resume yet.

So I started thinking of how I could write a resume that would actually highlight my skills thus far as a programmer in an immediately obvious way, and I think I found an interesting solution.

<!-- more -->
It's pretty common for UI or graphics designers to hand design their own resumes; it's a very clear and direct way of showing off your own design skills in an obvious way. Sadly, other than that there's little in the way of options for the rest of us: there's loads of templates out there for making an interesting *looking* resume, but that's not really the same effect for programmers as it is for a designer.

What's needed is a way to show off what one is capable of as a programmer through the medium of the resume itself.

I'm not sure I've quite got that far yet, but I have done what I think is a close-by solution: showing off one's basic capabilities as a programmer through the medium of how the resume is *generated*.

Thus, [resume.hsy](https://github.com/jarcane/resume.hsy).

`resume.hsy` is a straightforward Heresy program with one goal: to generate my resume in Markdown format. After just a half-day's effort, it succeeds at it.

It's not particularly impressive code (and the contortions involved in generating the output strings are a little ugly), and the output result is by design, not especially beautiful. The point here isn't to make a beautiful design object, but to present my skills in a clear format through the lens of a clear example of how I code. The fact that I designed the language it's written in is also part of the point of the demonstration, inspired by [the reaction of one commenter](https://twitter.com/boothead/status/545886788196507648) to my original post on Twitter.

Admittedly, that last bit is probably also a weakness: nobody codes in Heresy yet except me. But the Markdown output is readily available, and the code is mostly readable to anyone familiar with Lisp, and I'm also very proud of having written the first example of useful code in Heresy. 
