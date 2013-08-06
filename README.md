# Up and Running with Heroku


[Heroku](http://www.heroku.com/) recently announced that 50% of all incoming web requests to their platform originate from a mobile app. And while Heroku will not publicly announce the number of applications hosted on their platform, without a doubt there are hundreds of thousands. 

Clearly, Heroku is hub for mobile backends and anyone who's familiar with the platform isn't surprised. Application deployment on Heroku couldn't be easier; moreover, while its roots are firmly established in the [Ruby](http://www.ruby-lang.org/en/) community, Heroku supports a plethora of other language platforms like [Node.js](http://nodejs.org/), [Java](http://www.java.com/en/), [Python](http://www.python.org/), and more. 

In this hands-on workshop, I'll show you how to get started with Heroku and I'll teach you everything you need to know for managing, monitoring, and supporting your Heroku app. You'll leave this session with a firm grasp of [Git](http://git-scm.com/), the Heroku platform, [Heroku's add-ons](https://addons.heroku.com/), and I'll go over some alternative options. 


## Let's get started! 

This workshop is organized into 3 labs. We don't have a lot of time, so I strongly suggest you pair with someone. People with OSX, please volunteer to be pairing partners as it'll reduce friction because I'm also on OSX. That is, if you have Windows or Linux and someone near you is on a MacBook, then you should probably ask to pair with that person as my directions are tailored to OSX. 

Keep in mind, at least one person will need access to email as creating an account in Heroku uses a two phased authorization for account creation. That is, you'll need to click on a link in an email Heroku sends to you.

### Lab #1

In [Lab #1](/labs/lab_1/README.md), you'll be setting up your environment. You'll create a free Heroku account and download Heroku Toolbelt. Finally, you'll create a Heroku app. 


### Lab #2

In [Lab #2](/labs/lab_2/README.md), you'll deploy a sample app to Heroku. 

### Lab #3

In Lab #3, you'll get to know the `heroku` command line client a bit better. 

#### Logging 

First and foremost, it helps to see what your app is doing up in the cloud. Logs help here and the `heroku` command line client easily allows you to see logs in real-time with the following command: 

```
$> heroku logs -t
```

The `-t` flag is for tail. You can also specify how many lines of logs you'd like to see via the `-n` flag. Go ahead and type 

```
$> heroku help logs
```

to see more options w/r to logs in Heroku. 

#### Scaling

Naturally, the cloud rocks because you can easily scale your apps. And, of course, you can do this on-demand. You pay for what you use -- scale things up, you pay more, scale things down, you pay less. Easy. 

Scaling in Heroku is done via the `ps` command. Go ahead and type:  

```
$> heroku ps
=== web (1X): `coffee App.coffee`
web.1: up 2013/08/06 15:09:24 (~ 10m ago)
```

You should see some basic information on your app -- in this case, you have 1 web dyno running your app. In Heroku, you get one dyno for free -- this dyno has 512MB of memory allocated to it. Heroku offers 1GB dynos as well, however, they are not free. 

If you'd like to add more dynos (i.e. scale up your app), you specify how many dynos you'd like. For example, if I'd like 2 dynos, I'd type:

```
$> heroku ps:scale web=2
```

Feel free to do this yourself, but be aware: adding more than 1 dyno incurs a charge! You won't break the bank, however. 


## Helpful Resources
  
  * [Heroku.com](http://www.heroku.com/)
  * [Heroku development center](https://devcenter.heroku.com/)
  * [Java development 2.0: Git-commit your Java apps with Heroku's PaaS](http://www.ibm.com/developerworks/library/j-javadev2-21/)
  * [The Disco Blog Heroku entries](http://thediscoblog.com/blog/categories/heroku/)
  * [@heroku](https://twitter.com/heroku)
  * [Heroku Toolbelt](https://toolbelt.heroku.com/)
  * Git:
    * [Official Git tutorial](http://git-scm.com/docs/gittutorial)
    * [vogella.com Git Tutorial](http://vogella.com/articles/Git/)
