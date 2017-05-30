# How to Deploy a Static Site to Heroku

Uploaded on [Treehouse Blog](http://blog.teamtreehouse.com/deploy-static-site-heroku)

By *Andrew Chalkley*

Heroku is a hosting platform where you can deploy dynamic applications in Rails, PHP, Node.js and Python web applications.

---

## Prerequisites

&nbsp;

In order to deploy a site you need a couple of things:

&nbsp;

1. Have git installed
2. Heroku Account – sign up here
3. Download the Heroku Toolbelt – a command line application for managing your Heroku account
4. Run heroku login in your terminal or command prompt and fill in your Heroku credentials

---


## Deploying Your Site

First, you need to navigate to your project in the command prompt.

&nbsp;

`cd Projects/my-site`

&nbsp;

If you’re happy with the state of your application – create an `index.php` file. 
We can trick Heroku to deploy a static site by including 1 dynamic file.

&nbsp;

The `index.php` file will be served by Heroku before your `index.html`. 
We need to make the browser redirect from `index.php` to `index.html`. 
We only need to include one line of PHP code.

`<?php header( 'Location: /index.html' ) ;  ?>`

&nbsp;

**Pro Tip:** Make sure there’s no spaces before the `<?php` or else it won’t work!

Then we’ll use the command line tool called `git` to initialize or create 
a version of the site you want to deploy. To do that run the command:

&nbsp;

`git init`
`git add .`

&nbsp;

The `add .` means add all the files to the git repository.

Then you want to commit or save all the changes for your site. With a message describing what you’ve done.

&nbsp;

`git commit -m "My site ready for deployment."`

&nbsp;

Now you want to create your site on Heroku. 
If you’re already logged in (because you ran `heroku login` earlier), you can issue the following command:

&nbsp;

`heroku apps:create my-static-site-example`

&nbsp;

Insert your desired name instead of `my-static-site-example`.

If the name isn’t taken you can deploy your site using `git`.

&nbsp;

`git push heroku master`

&nbsp;

Once you see “remote: Verifying deploy…. done.”

You can now visit your site at `https://<whatever-name-you-selected>.herokuapp.com/` or 
[my example site](https://my-static-site-example.herokuapp.com/) 

If you want to add your own domain check out the [Heroku documentation](https://devcenter.heroku.com/articles/custom-domains).

If you need to, make changes to your site of the following 3 commands.

Add the changes…

&nbsp;

`git add .`

&nbsp;

Save the changes…

&nbsp;

`git commit -m "Add useful message"`

&nbsp;

Then deploy…

&nbsp;

`git push heroku master`

&nbsp;

If you’re new to `git` or want to get a better understanding check out the Treehouse course [Git Basics](https://teamtreehouse.com/library/git-basics). 
If you want to deploy a Node.js application we have [a workshop](https://teamtreehouse.com/library/deploy-a-node-application-to-heroku) for you too!



