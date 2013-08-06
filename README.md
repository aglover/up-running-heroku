# Up and Running with Heroku


[Heroku](http://www.heroku.com/) recently announced that 50% of all incoming web requests to their platform originate from a mobile app. And while Heroku will not publicly announce the number of applications hosted on their platform, without a doubt there are hundreds of thousands. 

Clearly, Heroku is hub for mobile backends and anyone who's familiar with the platform isn't surprised. Application deployment on Heroku couldn't be easier; moreover, while its roots are firmly established in the [Ruby](http://www.ruby-lang.org/en/) community, Heroku supports a plethora of other language platforms like [Node.js](http://nodejs.org/), [Java](http://www.java.com/en/), [Python](http://www.python.org/), and more. 

In this hands-on workshop, I'll show you how to get started with Heroku and I'll teach you everything you need to know for managing, monitoring, and supporting your Heroku app. You'll leave this session with a firm grasp of [Git](http://git-scm.com/), the Heroku platform, [Heroku's add-ons](https://addons.heroku.com/), and I'll go over some alternative options. 


## Let's get started! 

This workshop is organized into 3 labs. We don't have a lot of time, so I strongly suggest you pair with someone. People with OSX, please volunteer to be pairing partners as it'll reduce friction because I'm also on OSX. That is, if you have Windows or Linux and someone near you is on a MacBook, then you should probably ask to pair with that person as my directions are tailored to OSX. 

Keep in mind, at least one person will need access to email as creating an account in Heroku uses a two phased authorization for account creation. That is, you'll need to click on a link in an email Heroku sends to you.

### Lab #1

In Lab #1, you'll be setting up your environment so you can work with Heroku. Environment setup is easily done; all you need to do is first [sign up for a free account](https://id.heroku.com/signup). Once you've done that, you'll need to download [Heroku's Toolbelt](https://toolbelt.heroku.com/).  

Heroku Toolbelt gives you a few things:

 * [Heroku client](https://github.com/heroku/heroku) (aka `heroku`) - CLI tool for creating and managing Heroku apps
 * [Foreman](https://github.com/ddollar/foreman) - running your apps locally
 * [Git](http://git-scm.com/) - Heroku deployment

Once you've created an account & downloaded Toolbelt, you'll next need to fire up a terminal. The Heroku Toolbelt installs a nifty command line client dubbed `heroku` that you'll use quite a bit when working with Heroku. 

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

With that, you are done! You can now deploy your next killer app to the cloud using Git! 

### Lab #2

In lab #2, you'll be [cloning](https://www.kernel.org/pub/software/scm/git/docs/git-clone.html) a [sample Node.js application](https://github.com/aglover/whiskered-robot) and deploying that app to Heroku.


#### Installing Node.js

First and foremost, you'll need to install Node.js -- you can do this in [three steps](http://thediscoblog.com/blog/2013/03/12/node-in-3-commands/):

Step 1: Download and install nvm.

```
$> curl https://raw.github.com/creationix/nvm/master/install.sh | sh
```

Step 2: Reload your shell.

```
$> source .bash_profile
```

Step 2.5: Obtain a list of available node versions to install.

```
$> nvm ls-remote
```

Step 3: Install your desired version of node.

```
$> nvm install v0.10.0
```

#### Clone the sample repo

Next, clone the sample Node app from Github:

```
$> git clone git@github.com:aglover/whiskered-robot.git
```

You will need to change directories into the `whiskered-robot` directory.

##### Install dependencies

From within the `whiskered-robot` directory, type:

```
$> npm install
```

This command downloads and installs a series of libraries that the sample Node app depends on. 

##### Start the application locally

Next, you can see the app running locally by typing:

```
$> foreman start
```

Foreman runs processes as defined in a `Profile`. For example, if you take a look at the `Profile` defined in the project, it looks like this:

```
web: coffee App.coffee
```

Which tells node to run a web process with the `coffee` command. For now, don't worry much about what that `coffee` command is! 

##### Configure a remote repository

If you are still running the application via Foreman, please stop it by pressing CTRL-C. 

When you created your app instance in Heroku, you should have seen something like so:

```
Creating intense-savannah-8665... done, stack is cedar
http://intense-savannah-8665.herokuapp.com/ | git@heroku.com:intense-savannah-8665.git
```

See the last line second part that says `git@heroku.com:intense-savannah-8665.git`? That's your _remote_ Git repository. You will need to manually add this repository to your _local_ Git configuration to enable remote pushes. Follow the directions and it'll make sense. 

First, copy that `git@heroku.com:...` URL. 

Next, from within the root of the whiskered-robot project, type:

```
$> git remote add heroku <your remote git repo URL>
```

Finally, type:

```
$> git push heroku master
```

Boom! You are done! Your app is live in the cloud, baby! Wanna see it? No problem, type:

```
$> heroku open
```

You should see a nifty app! 

![your app is live!](/docs/imgs/liveapp.png)

If you don't see the above app, raise your hand! 

### Lab #3



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
