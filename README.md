weinre-heroku - heroku wrapper around weinre
============================================

If you'd like to run your very own weinre server on
the big ol' internets, this project is for you.

You'll need some
[basic familiarity](https://devcenter.heroku.com/articles/nodejs)
with
[heroku](http://www.heroku.com/).

Here are the basic instructions:

<pre>
<b>$ git clone git://github.com/pmuellr/weinre-heroku.git</b>
Cloning into 'weinre-heroku'...
remote: Counting objects: 11, done.
remote: Compressing objects: 100% (10/10), done.
remote: Total 11 (delta 0), reused 11 (delta 0)
Receiving objects: 100% (11/11), done.
                                             &nbsp;
<b>$ cd weinre-heroku</b>
                                             &nbsp;
<b>$ heroku login</b>
Enter your Heroku credentials.
Email: xxx@yyy.zzz
Password (typing will be hidden):
Authentication successful.
                                             &nbsp;
<b>$ heroku create</b>
Creating aaa-bbb-666... done, stack is cedar
http://aaa-bbb-666.herokuapp.com/ | git@heroku.com:aaa-bbb-666.git
Git remote heroku added
                                             &nbsp;
<b>$ git push heroku master</b>
Counting objects: 11, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (10/10), done.
Writing objects: 100% (11/11), 1.23 KiB, done.
Total 11 (delta 0), reused 11 (delta 0)
                                             &nbsp;
-----&gt; Heroku receiving push
-----&gt; Node.js app detected
-----&gt; Resolving engine versions
       Using Node.js version: 0.8.14
       Using npm version: 1.1.65
-----&gt; Fetching Node.js binaries
-----&gt; Vendoring node into slug
-----&gt; Installing dependencies with npm
       ... npm junk elided ...
       Dependencies installed
-----&gt; Building runtime environment
-----&gt; Discovering process types
       Procfile declares types -&gt; web
-----&gt; Compiled slug size: 8.6MB
-----&gt; Launching... done, v4
       http://aaa-bbb-666.herokuapp.com deployed to Heroku
                                             &nbsp;
To git@heroku.com:aaa-bbb-666.git
 * [new branch]      master -&gt; master
                                             &nbsp;
<b>$ heroku ps:scale web=1</b>
Scaling web processes... done, now running 1
                                             &nbsp;
<b>$ heroku ps</b>
=== web: `node node_modules/.bin/weinre --httpPort $PORT --boundHost -all- --verbose`
web.1: up 2012/11/28 11:52:45 (~ 10s ago)
                                             &nbsp;
<b>$ heroku open</b>
Opening aaa-bbb-666... done
</pre>

At this point, a browser has opened to your instance of weinre on the big ol'
internets.

Enjoy!
