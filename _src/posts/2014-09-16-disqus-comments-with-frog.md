    Title: Disqus comments with Frog
    Date: 2014-09-16T10:15:18
    Tags: Racket, Frog

I had a slightly tricky time setting up a numbered comment link with Disqus, so I thought it might be helpful to write up a quick post on how I did it.

The standard Frog templates of course include a widget for embedding a Disqus comment thread in a page, which is quite handy, however without configuration Disqus defaults to an obnoxious thing full of Yahoo ads. To fix this, you need to register an account with Disqus, and create a new site with it, which you can do [here](https://disqus.com/admin/create/). Give it a name and a unique URL, which will provide the "shortname" you'll use with the Disqus widget and scripts.

From here, you'll go to the install page, from which you can select from a number of options from which we want to choose the one called *Universal Code*. This page contains instructions for manually embedding the necessary JavaScript files for Disqus to work. Leave this open for now, we actually don't need it for step 1, which has already been helpfully provided via Frog's Disqus widget.

Instead, we want to open up the ``post-template.html`` in our Frog project's _src directory, and look for the ``@disqus-comments["shortname"]`` line and replace "shortname" with the shortname you chose for your Disqus account. If you're not sure what that is, look in the template code on the *Universal Code* guide for ``var disqus_shortname =`` at the top of the code box in step 1.

This is enough to get us comments pages that should now be blissfully free of annoying Yahoo Ads, and also gives us moderation tools and other handy settings for configuring how Disqus works, but there's one other useful step you might want (I did), and that's one of those nice little numbered "comments" links at the bottom of our posts when looking at the main blog page.

To do that, we need to make some modifications to ``index-template.html`` and create a footer that contains what we want. We want to add a set of <footer> tags after ``@|content|`` to contain a link that the Disqus software will then modify to contain a comments count. This looks like this:

```html
  <footer>
    <br>
    <a href='@|uri-path|#disqus_thread'>Comments</a>
    ** Disqus javascript goes here**
  </footer>
```
Then, after the ``a href`` line we can just paste in the code from the second box in the *Universal Code* guide, under "How to display comment count."

And voila, numbered comments links in our Frog posts! 
