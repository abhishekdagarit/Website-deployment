# How to Deploy a Static Site to Heroku

Uploaded on [Treehouse Blog](http://blog.teamtreehouse.com/deploy-static-site-heroku)

By *Andrew Chalkley*

Heroku is a hosting platform where you can deploy dynamic applications in Rails, PHP, Node.js and Python web applications.

---

### Prerequisites

In order to deploy a site you need a couple of things:

1. Have git installed
2. Heroku Account – sign up here
3. Download the Heroku Toolbelt – a command line application for managing your Heroku account
4. Run heroku login in your terminal or command prompt and fill in your Heroku credentials

### Deploying Your Site

First, you need to navigate to your project in the command prompt.

`cd Projects/my-site`

If you’re happy with the state of your application – create an `index.php` file. 
We can trick Heroku to deploy a static site by including 1 dynamic file.

The `index.php` file will be served by Heroku before your `index.html`. 
We need to make the browser redirect from `index.php` to `index.html`. 
We only need to include one line of PHP code.

`<?php header( 'Location: /index.html' ) ;  ?>`

**Pro Tip:** Make sure there’s no spaces before the `<?php` or else it won’t work!

Then we’ll use the command line tool called `git` to initialize or create 
a version of the site you want to deploy. To do that run the command:

`git init`
`git add .`

The `add .` means add all the files to the git repository.

Then you want to commit or save all the changes for your site. With a message describing what you’ve done.

`git commit -m "My site ready for deployment."`

Now you want to create your site on Heroku. 
If you’re already logged in (because you ran `heroku login` earlier), you can issue the following command:

`heroku apps:create my-static-site-example`

Insert your desired name instead of `my-static-site-example`.

If the name isn’t taken you can deploy your site using `git`.

`git push heroku master`

Once you see “remote: Verifying deploy…. done.”

You can now visit your site at `https://<whatever-name-you-selected>.herokuapp.com/` or 
[my example site](https://my-static-site-example.herokuapp.com/) 

If you want to add your own domain check out the [Heroku documentation](https://devcenter.heroku.com/articles/custom-domains).

If you need to, make changes to your site of the following 3 commands.

Add the changes…

`git add .`

Save the changes…

`git commit -m "Add useful message"`

Then deploy…

`git push heroku master`

If you’re new to `git` or want to get a better understanding check out the Treehouse course [Git Basics](https://teamtreehouse.com/library/git-basics). 
If you want to deploy a Node.js application we have [a workshop](https://teamtreehouse.com/library/deploy-a-node-application-to-heroku) for you too!



