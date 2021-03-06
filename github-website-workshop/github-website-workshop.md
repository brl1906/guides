Creating a Website & Portfolio on GitHub
========================================

Bit.ly shortlink: https://bit.ly/2Ok8PTo

# Prerequisites

You will need the following for this workshop:

1. Sign up for a free GitHub account:  https://github.com/join
2. Download a git client:
    - Windows: https://git-scm.com/downloads or https://gitforwindows.org/
    - Mac OS: https://brew.sh/, and `brew install git`
    - Ubuntu: `apt-get install git`
    - Fedora: `dnf install git`
    - Arch: `pacman -S git`
3. Download Ruby:
    - Windows: https://rubyinstaller.org/
    - Mac OS: `brew install ruby`
    - Ubuntu: `apt-get install ruby`
    - Fedora: `dnf install ruby`
    - Arch: `pacman -S ruby`

Note:
* GitHub also offers a [desktop GUI client](https://desktop.github.com). However, this workshop will primarily use the git terminal commands.
* Windows 10 users may find it easier to install the Ubuntu Linux subsystem from the Windows store and use that to complete this workshop.

Don't know git? Check out this [simple startup guide](https://rogerdudler.github.io/git-guide/)!

# Workshop

## Configuring your git account

After your install git, run these preliminary commands (username = your GitHub username):

`git config --global user.name "username"`

`git config --global user.email "username@users.noreply.github.com"`

## Creating your repository

1.  Go to https://pages.github.com/ and follow the instructions for creating your repository. This is where your website will be hosted.

Click on 'User or organization site' and following the instructions for creating and committing to your repository.

a.  Create your repostiory on the GitHub website.

b.  Clone it to your local machine (username = your GitHub username):

`git clone https://github.com/username/username.github.io`

c.  Add an index.html:

```
cd username.github.io
echo "Hello World" > index.html
```
d.  Push it:

```
git add --all
git commit -m "Initial commit"
git push -u origin master
```

2.  In a browser, go to https://username.github.io (username = your GitHub username).

You've just created a website!

## Crafting your homepage

To create the actual content of your website, we can use Jekyll, a popular framework for building static web pages.

Technically, you could use any method for building out your website. However, GitHub has an [abundant amount of documentation for Jekyll](https://help.github.com/articles/using-jekyll-as-a-static-site-generator-with-github-pages). Therefore, we will use Jekyll in this workshop.

1.  Install Bundler and Jekyll:

    In the root website directory, create a file called 'Gemfile' and add the following:

    ```
    source "https://rubygems.org"
    gem "github-pages", group: :jekyll_plugins
    ```

    Save and exit the file.

    `gem install bundler jekyll`

2.  Make sure your pwd is in the root of your GitHub website, and create a new Jekyll site in that directory:

    `jekyll new .`

3.  Start your new Jekyll demo site:

    `bundle exec jekyll serve --watch`

You will find your newly created site being served at http://localhost:4000.

## Jekyll site basics

When you created a new Jekyll site, it automatically created some files and directories:

```
_config.yml     Main config settings for the site
Gemfile         List of Gem dependencies
_posts          Directory for blog posts
_site           Directory for writing files
index.md        Site home page
```

## Editing basic site info

You can edit `_config.yml` and change properties such as the site title, site URL, email, etc.

## Creating pages

### Creating a contact page

If you know Markdown, then you can start making pages immediately!

Lets create a simple contact page within your Jekyll site. In the root directory of your GitHub site (username.github.io/), create a file called 'contact.md'.

Fill the file with the following text:

```
---
layout: page
title: "Contact"
---
Name: Zach Blankinship
GitHub: [@ZachBlank](https://github.com/ZachBlank)
Twitter: [@ZachBlank_](https://twitter/ZachBlank_)
LinkedIn: [@zach-blankinship](https://www.linkedin.com/in/zach-blankinship-426b97104/)
```

Save and exit this file.

### Creating a resume page

You can either create your resume in Markdown and serve it directly on your site, or you can even have Jekyll serve pre-made document files for you!

In the root directory of your GitHub site, create a file called 'resume.md'

```
---
layout: page
title: "Resume"
---
View [my resume](./mydocs/resume.pdf)
```

Save and exit this file.

### Viewing local changes

Reload your local site at http://localhost:4000/. You should now have page headers for 'Contact' and 'Resume'.

## Committing your site changes to GitHub

When you are ready to commit your local changes to your site at username.github.io:

`git add --all`

`git commit -m "Creating my first site"`

`git push -u origin master`

In your browser, go to https://username.github.io to see the committed changes.

## To go even further beyond

There are always ways you can improve your website! Here are a couple suggestions:

1.  Use CloudFlare to speed up your website response times

    See: https://scotch.io/tutorials/jekyll-github-pages-and-cloudflare-for-pagespeed-win

2.  Add a custom domain to your website to personalize it even further

    See: https://help.github.com/articles/using-a-custom-domain-with-github-pages/

3.  Check out more Jekyll themes to create additional pages for your website (presentations, blogs, etc)

    See:
    * http://jekyllthemes.org/
    * https://github.com/jekyll/jekyll/wiki/Themes
