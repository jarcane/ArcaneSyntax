    Title: A Quickstart Guide to Frog and GitHub Pages
    Date: 2014-10-18T12:34:28
    Tags: Racket, Frog

It was discussed recently on the #racket freenode channel that getting going with Frog might actually be a bit tricky for someone not coming from the Racket ecosystem or unfamiliar with Github Pages. The process is actually pretty straightforward, but the steps involved aren't exactly documented anywhere in one place, and I promised to look into remedying that. Arcane Syntax itself is hosted on GHP, and generated with Frog, so I had some experience in getting it all working and thought I could help.

Read on past the jump for a quick guide to building a blog in Frog and hosting it on Github Pages. 

<!-- more -->

### Step 1: Install Racket ###

Frog is powered by the Racket programming language, and is currently available primarily as a package for Racket, so we'll need that. You can download Racket for your platform, be it *nix, Mac, or Windows, from their [web site](http://download.racket-lang.org/). If you're on a Linux or BSD, you might also check your package repo for it, but be sure it's up-to-date: Frog needs Racket 6, and I know at least Debian is still only hosting 5.x.

Crucially here, you also need to make sure that Racket's root directory is available in your command-line path. Unixen should take care of this automatically, but Windows will need it added to the $PATH if we want this to be a painless process. You'll need to go to the System Control Panel, Advanced System Settings, Environment Variables, and edit Path to include "C:\Program Files\Racket" for 64-bit Racket or "C:\Program Files (x86)\Racket" for 32-bit.

### Step 2: Install Frog ###

As long as Step 1 has gone fine, this part is easy. Go to your command line and do ``raco pkg install frog``. 

raco is the Racket command-line swiss army knife, used for everything from compiling executables to installing packages; it'll also be your interface for Frog commands too, now that it's installed.

### Step 3: Make a Github Account ###

[GitHub](http://github.com) is a service for hosting source repositories managed by the Git version control system. You can create a new account right from the main page, picking a username, email, and password. It'll ask you what plan you wish to use, with Free as an option so long as you don't mind all your repos being public. It will also send an email to whatever account you gave it, to verify that email for future use for things like password recovery.

*NOTE:* By default, the email address you give Github will be publicly posted on your account profile. If you don't want this to happen, once you've verified your email address, you can tell it to 'keep my email address private' on the email settings page.

### Step 4: Install Git ###

You'll also need to install Git, because as the previous step alluded to, it's what we're going to use to manage and sync our changes to the blog whenever we generate a new post and so forth.

If you're on Windows, the path of least resistance here is just to install the [Github for Windows](http://windows.github.com) client. Ditto for Macs, which have their [own client](https://mac.github.com/). It's not without it's wrinkles, but for our purposes it is dead easy. Otherwise, if we're on Unixen, we'll probably need to install it from our package repo of choice.

You'll also need to do some additional setup things as well, like creating an SSH key for using Git and stuff, which I am going to pass along to the absolutely excellent [Github Tutorial page](https://help.github.com/articles/set-up-git/) on setting up Git.

### Step 5: Make a Repo for your page ###

If you're logged in to Github, you can just click on the little + symbol on the top bar of the site and choose "New Repository".

For the name, we want to name it after the URL we're going to use to get to our new blog. Github does a really cool thing where a *username*.github.com repo will be automatically uploaded and hosted at that URL. So that's what we'll name our repo, using the username we chose in Step 3.

It's up to you whether you want it to be public or private, but the latter option is only available if you pay for hosting. You can also provide a description. Don't worry about the .gitignore and license stuff, and we don't really need to make a README either. We actually want our new repo completely empty.

### Step 6: Make the local mirror of our Blog ###

Guess what! See that page that just appeared when we started an empty repo? It happens to be a complete set of instructions to link our online repository to a local folder on our computer. We just have to know a little bit more on what to do with them.

If you're on Windows or Mac, and you've installed the Github client, this is easy as can be: click that green button. If you've followed the set up instructions I linked in Step 4, that should open it up in our Github client and let us create a local "clone" of our online repo.

If you're on Unixen, we want to do the thing it says there under "or create a new repository on the command line", save that it's left out an important step: we need to make a folder for all this to happen in! So we revise the instructions too:

```
mkdir [username].github.com
cd [username].github.com
touch README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/frogtutorial/frogtutorial.github.com.git
git push -u origin master
```
Substitute ``[username]`` for the name you used on Github.

### Step 7: Build our new blog ###

Navigate to the directory you created in the previous step in your favorite command-line shell, and do ``raco frog --init``.

Frog will now build all the requisite template files to generate your new blog! These will all be on defaults, of course, but you can even run ``raco frog -bp`` and it will build and open your blog in your web browser running on a local webserver. Neat! Hit Ctrl-C to stop the server if you don't want it to stay running.

### Step 8: Customize our Blog ###

Right now though, our blog is pretty generic. It's all on defaults! We can change some of the most common settings and details from the ``.frogrc`` file that lives in the root of our site folder. Open it up in your favorite text editor.

Crucially, we really need to change the URL, to match the URL of our Github page: ``http://[username].github.com``

You can also change the title and author here, as well as some settings about how Frog generates pages, which are all helpfully described right there in the file. We don't really need to mess with any of them for now though.

We can also tell it which text editor we use, by giving it the name of the executable. This is useful because we can follow up with some helpful frog command to open the editor to the last new post we told it to make.

The default templates that Frog uses to generate pages are also tweakable, if you know some HTML and so forth, and it uses Bootstrap for making a pretty site; so you can use Bootstrap templates like those on [Bootswatch](http://bootswatch.com/) to jazz it up from the basic template. I've also written a short little guide for setting up [Disqus comments](http://jarcane.github.io/blog/2014/09/16/disqus-comments-with-frog.html) properly.

### Step 9: Generate a new post ###

So let's make a post to our new blog! Once more from our blog's home folder, we can do ``raco frog -n "[post title]"``. It will helpfully display the name of the Markdown file it just generated to be the template of our new post.

You can open up this .md file in your favorite text editor or run ``raco frog --edit`` if we've set that up.

Frog files are in the form of Markdown, which is a handy little markup language invented by John Gruber that makes pretty looking text files that also parse semi-easily to equally pretty HTML. Mr. Gruber has a helpful guide for the basics on his page defining [Markdown syntax](http://daringfireball.net/projects/markdown/syntax).

A new Frog post already includes some boilerplate stuff: a block at the top with title, date/time, and tags, some filler text, and a ``more`` tag for marking a break in the text between what's shown in your main blog page and what's only shown by clicking through to individual posts.

The filler text can be replaced, the more tag removed or placed where you like, but crucially, you *MUST* change the DRAFT tag to something else, or else Frog will skip it when you build the blog!

### Step 10: Build your blog ###

Save your text file, and now we can rebuild the blog to include it. Do the following on the command line:

```
raco frog -c  *clears any old cached files, don't forget this!*
*then*
raco frog -bp  *if you want to see a preview*
*or just*
raco frog -b  *if you don't*
```

If everything looks satisfactory, proceed to step 11. Otherwise, tweak things as needed and redo the build.

### Step 11: Sync your changes with Github ###

Now we need to commit and upload our newly built blog to Github to host.

If you're on Windows or Mac and using the Github client, this can be done by clicking on our repo, adding a summary and description under "Uncommitted Changes", clicking "Commit to master", then finally clicking the Sync button on the upper right.

If we're on Unixen, we do this:
```
git add -A
git commit -m "Some kind of short description"
git push
```

Once everything is uploaded, and accounting for a bit of time for Github itself to recognize that stuff lives there now, we should be able to see our new blog online at ``http://[username].github.com``!

If you want any more help with Frog, be sure to check out the [Frog repo](https://github.com/greghendershott/frog), and if you've any questions about Git or Github, their help files are surprisingly helpful and informative. Enjoy!
