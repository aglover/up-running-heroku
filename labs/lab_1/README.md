# Lab #1

## Introduction 

In Lab #1, you'll be setting up your environment so you can work with Heroku. Environment setup is easily done; all you need to do is first [sign up for a free account](https://id.heroku.com/signup). Once you've done that, you'll need to download [Heroku's Toolbelt](https://toolbelt.heroku.com/).  

Heroku Toolbelt gives you a few things:

 * [Heroku client](https://github.com/heroku/heroku) (aka `heroku`) - CLI tool for creating and managing Heroku apps
 * [Foreman](https://github.com/ddollar/foreman) - running your apps locally
 * [Git](http://git-scm.com/) - Heroku deployment

Once you've created an account & downloaded Toolbelt, you'll next need to fire up a terminal. The Heroku Toolbelt installs a nifty command line client dubbed `heroku` that you'll use quite a bit when working with Heroku. 

## Let's do this thing!

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