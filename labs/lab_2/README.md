# Introduction

In lab #2, you'll be [cloning](https://www.kernel.org/pub/software/scm/git/docs/git-clone.html) a [sample Node.js application](https://github.com/aglover/whiskered-robot) and deploying that app to Heroku.

## Let's get started! 

Here we go...

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