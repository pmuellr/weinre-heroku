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


running on Cloud Foundry
============================================

It's even easier to run weinre on Cloud Foundry than it is on Heroku!

Assumes you have an account on a Cloud Foundry-based PaaS, and have the 
[`cf` tool](https://github.com/cloudfoundry/cli/releases) installed.

If you're not currently using Cloud Foundry, you can try out
[IBM's BlueMix](https://ace.ng.bluemix.net/) for free.

Here are the basic instructions:

* note that you should substitute your own desired hostname in the `-n` option of 
  the `cf push weinre` invocation below.

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
<b>$ cf push weinre -n some-name-here</b>
                                             &nbsp;
Creating app weinre in org [your-id-here] / space dev as [your-id-here]...
OK
                                             &nbsp;
Creating route some-name-here.ng.bluemix.net...
OK
                                             &nbsp;
Binding some-name-here.ng.bluemix.net to weinre...
OK
                                             &nbsp;
Uploading weinre...
Uploading from: ~/Projects/bluemix/weinre-heroku
27.2K, 26 files
OK
                                             &nbsp;
Starting app weinre in org [your-id-here] / space dev as [your-id-here]...
OK
    [staging messages elided]
1 of 1 instances running
                                             &nbsp;
App started
                                             &nbsp;
Showing health and status for app weinre in org [your-id-here] / space dev as [your-id-here]...
OK
                                             &nbsp;
requested state: started
instances: 1/1
usage: 1G x 1 instances
urls: some-name-here.ng.bluemix.net
                                             &nbsp;
     state     since                    cpu    memory        disk          
#0   running   2014-03-14 05:44:56 PM   0.0%   30.7M of 1G   42.7M of 1G 
</pre>

At this point, you can open your browser on your new site at `http://some-name-here.ng.bluemix.net`
running on the big ol' internets.

Enjoy!

