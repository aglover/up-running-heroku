# Up and Running with Heroku


[Heroku](http://www.heroku.com/) recently announced that 50% of all incoming web requests to their platform originate from a mobile app. And while Heroku will not publicly announce the number of applications hosted on their platform, without a doubt there are hundreds of thousands. 

Clearly, Heroku is hub for mobile backends and anyone who's familiar with the platform isn't surprised. Application deployment on Heroku couldn't be easier; moreover, while its roots are firmly established in the [Ruby](http://www.ruby-lang.org/en/) community, Heroku supports a plethora of other language platforms like [Node.js](http://nodejs.org/), [Java](http://www.java.com/en/), [Python](http://www.python.org/), and more. 

In this hands-on workshop, I'll show you how to get started with Heroku and I'll teach you everything you need to know for managing, monitoring, and supporting your Heroku app. You'll leave this session with a firm grasp of [Git](http://git-scm.com/), the Heroku platform, [Heroku's add-ons](https://addons.heroku.com/), and I'll go over some alternative options. 


## Let's get started! 

This workshop is organized into 3 labs. We don't have a lot of time, so I strongly suggest you pair with someone. People with OSX, please volunteer to be pairing partners as it'll reduce friction because I'm also on OSX. That is, if you have Windows or Linux and someone near you is on a MacBook, then you should probably ask to pair with that person as my directions are tailored to OSX. 

### Lab #1

In Lab #1, you'll be setting up your environment so you can work with Heroku. Environment setup is easily done; all you need to do is first [sign up for a free account](https://id.heroku.com/signup). Once you've done that, you'll need to download [Heroku's Toolbelt](https://toolbelt.heroku.com/).  

Once those two steps are complete, you'll next need to fire up a terminal. The Heroku Toolbelt installs a nifty command line client dubbed `heroku` that you'll use quite a bit when working with Heroku. 

With a terminal fired up, type:

```
$> heroku login
```

And follow the prompts -- you'll need to use your email address and password that you configured when you signed up for the service. Don't forget to allow this operation to create you an SSH key as Heroku deployments leverage Git, which uses SSH for data transfer.

Next, you'll use the `heroku` command to create an app -- keep in mind that this command merely creates a place holder for a legitimate app. That is, creating a Heroku app doesn't result in any code, just a place to _deploy_ your code. Accordingly, type:

```
$> heroku create
```

This will result in the creation of a placeholder for your app and it'll be randomly named. 

You can optionally provide a name to your app as well:

```
$> heroku create your_name
```

### Lab #2



### Lab #3



## Helpful Resources
  
  * [Heroku.com](http://www.heroku.com/)
  * [Heroku development center](https://devcenter.heroku.com/)
  * [Java development 2.0: Git-commit your Java apps with Heroku's PaaS](http://www.ibm.com/developerworks/library/j-javadev2-21/)
  * [The Disco Blog Heroku entries](http://thediscoblog.com/blog/categories/heroku/)
  * [@heroku](https://twitter.com/heroku)
  * [Heroku Toolbelt](https://toolbelt.heroku.com/)
