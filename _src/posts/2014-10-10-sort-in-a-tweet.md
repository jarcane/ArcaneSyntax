    Title: Sort in a Tweet
    Date: 2014-10-10T23:00:29
    Tags: Racket

Sometimes I just can't leave well enough alone. After my last post I dove into further simplifying my Racket code, and as a fun way of [relaunching my Twitter](https://twitter.com/J_Arcane) I decided to take the lock back off with a bang by code-golfing the sort algorithm down to fit in a tweet.

With some extra pointers from Rosetta Code and Jens Axel Soegaard in the #racket channel, I boiled it down to [this tweet](https://twitter.com/J_Arcane/status/520664571858911232). 

<!-- more -->

```racket
#lang racket (define (s f l)(match l['() '()][`(,h .,t)`(,@(s f(filter(curry(negate f)h)t)),h,@(s f(filter(curry f h)t)))]));(sort fun list)
```

I also debuted a new personal logo, developed entirely in Racket using the Racket image libraries. I was inspired by the shape of the [lambda phage](http://en.wikipedia.org/wiki/Lambda_phage) and the Plague Inc. computer game to create a new lambda logo:

![The Lambdemic Logo](http://i.imgur.com/xHfZ0a2.png)

This can be helpfully generated with the following piece of Racket code:

```racket
#lang racket

(require pict
         images/icons/style
         images/icons/symbol
         images/icons/misc
         file/convertible)

(define lambda-phage
  (pict->bitmap
   (cc-superimpose
    (bitmap (regular-polygon-icon 6 
                                  (* -1/2 (- (/ pi 6) (* 1/2 pi)))
                                  #:color "darkred"
                                  #:height 256 
                                  #:material glass-icon-material))
    (bitmap (lambda-icon #:height (* 256 3/4) 
                         #:color "white"
                         #:material plastic-icon-material)))))

(send lambda-phage save-file "lambdemic-big.png" 'png)
```

And for that amusing little banner image:

```racket
#lang racket

(require pict
         pict/code
         file/convertible)

(define define-universe  
  (pict->bitmap
   (cc-superimpose 
    (colorize (filled-rounded-rectangle  1500 500) "Moccasin")
    (parameterize ([current-code-font "Envy Code R"]
                   [get-current-code-font-size (lambda () 48)])
      (code (begin
              (define universe
                (void))))))))

(send define-universe save-file "define-universe.png" 'png)
```
