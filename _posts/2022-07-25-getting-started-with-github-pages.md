---
title: Getting Started with Github Pages
categories:
- Git
- Github Pages
- Jekyll
---

# Making a Website

This site is built with Jekyll and hosted via Github Pages.

Jekyll is a static-site generator. You specify aspects of the website you want Jekyll to build for you in structures and syntax that Jekyll understands, and then invoke Jekyll to create an HTML website to your specifications. CSS, or Sass (CSS' older, cooler, more theme-friendly sibling), JavaScript, and many plugins are available to enhance functionality and provide more building blocks with which to assemble a site.

[Github Pages](https://pages.github.com/) is a way to host a website on Github from a repository. It's free, and seems well-suited to a personal website such as a blog, portfolio, or showcase.

## Why Github Pages?

Many website creator tools and traditional web hosting is steeply priced and easily starts at around  $20USD/month, or around $240 USD/year -- even without counting the price of leasing a domain.

"If the product is free, you're the product."

For a personal website, that's often the goal.

I've worked with web technologies especially frequently over the last 3 years, since joining Southern New Hampshire University; much of my exposure to web development has been in the .NET/C#/ASP technology family. Jekyll is very different, focusing on HTML, Liquid, Sass, and with the help of Github Pages, git. Jekyll is new to me; Git is not. Combining what I know with what I don't offers an environment of challenge with support. Building this site has deepened my understanding of a host of technologies, including Git and Jekyll as well as HTML, Sass, and Github.

I welcome more tools to the toolbox.

## Searching for Themes

Especially when choosing a website, look and feel matter. Moreover, Jekyll is analagous to a workbench with many tools available to build a website. After performing the [official Jekyll Step-by-Step tutorial](https://jekyllrb.com/docs/step-by-step/01-setup/), I realized I wouldn't mind a bit of a jumping-off point. Web *design* is not something I've practiced much; I welcome assistance from a more experienced designer.

Searching for themes rapidly grew into a nontrivial task.

Github has a [list of supported Jekyll themes for Github Pages sites](https://pages.github.com/themes/). Many are simple and straightforward, favoring flexibility over features. All great starts, but a little *too* minimal for my preference. Github led me to, well, Github, where user-created themes are available to suit various needs.

Turns out, there are a [*lot* of themes on Github](https://github.com/topics/jekyll-theme). They range from simple to impressively robust, and from free to premium. After eyeing [Hydejack](https://github.com/hydecorp/hydejack) for a while, I discovered [Alembic, by David Darnes](https://github.com/daviddarnes/alembic).

This site is based on Alembic. *Thanks David!*

>I highly encourage you to donate or tip creators that make things that help you; every peer-to-peer transaction like that empowers creators and creativity everywhere, and helps create a more equitable culture.

## Implementing a Theme

[Jekyll supports theming](https://jekyllrb.com/docs/themes/), allowing creators to bundle themes into gems, packages of Ruby code, which can be included in a Jekyll project's Gemfile, something like a package manifest. Github Pages accomplishes its theming with a custom `github-pages` gem and a `jekyll-remote-theme` Jekyll plugin.

Github Pages -- and the wider internet -- has instructions on how to incorporate a theme into your Github Pages site; there are several methods:
- [Using the Theme Chooser](https://docs.github.com/en/pages/getting-started-with-github-pages/adding-a-theme-to-your-github-pages-site-with-the-theme-chooser)
- As a remote theme in `_config.yml`, detailed [here in Cayman's README](https://github.com/pages-themes/cayman#usage) and [here in Github's Docs](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-a-theme-to-your-github-pages-site-using-jekyll)
- As a repository fork or copy; often discouraged, as in [Alembic's README](https://github.com/daviddarnes/alembic#as-a-boilerplate--fork)

I opted for none of the above. Something like a fork with benefits.

>There are a lot of ways to implement a theme. At the end of the day, I went with a largely manual approach that allowed me to extend an existing theme into my own. My method provides me with more flexibility and control, as well as an opportunity to see, interact with, and modify many of the moving parts involved in the theme I started with.

Realizing that I wanted to start with a theme and tune it to my needs, modifying it in any number of ways, I decided I wanted to start with Alembic's base and grow from there. [David encourages the use of Alembic as a starting point](https://github.com/daviddarnes/alembic#about), and I've done so.

When it comes to aesthetic and style, my preferences change frequently. 

>What if I change my mind?

From the outset, I wanted flexibility to potentially swap in a new theme -- in case I decided I wanted to build my own from scratch, or radically change the look and feel of my site.

Some searching led me to the blog of Matthias Lischka, who authored an [article on the subject of establishing repositories for Jekyll sites](https://matthiaslischka.at/2018/12/03/github-jekyll-best-practice/). 

Matthias recommends using multiple `remotes` to separate responsibility and ensure that theme-switching is simple later on.

## Three Remotes; Three Responsibilities

At the end of Matthias' recommended setup, you have 3 repositories with their own responsibilities:
- `origin` - your website's publishing source repository, where the **content** of your site will live. Pages, posts, logos, etc.
- `upstream` - your theme's repository; in my case, [Alembic's repository](https://github.com/daviddarnes/alembic)
- `personalUpstream` - a fork of your theme's repository for any custom changes that aren't content-related. This might include new features (or feature removal), etc.

My content goes to `origin` and stays mine, a history isolated from the theme itself. To swap to another theme, I'll rebase my content on top of the new theme's history and modify my `upstream` and `personalUpstream` remotes accordingly. I can incorporate new features from `upstream` into my repository with a fetch and rebase, and can add, extend, or remove features via my `personalUpstream` fork, all independently of my site's content.

I'm very passionate about git -- it was love at first usage, from the first `git rebase -i`. It's my favorite source control technology to use. I'm pretty new to blogging, though. My websites of yesteryear were typically portfolios, shiny but unchanging, showing off images and linking to videos of past projects. Not a whole lot of insight into technologies or cool solutions to weird problems.

As this site grows, I may include some portfolio content in a similar style, but I'm more interested in sharing knowledge and building a library of content for myself that may also benefit others.

Is there value in writing a walkthrough of how I setup this site, from installing Ruby and Jekyll to finally merging a pull request to `main` in this site's repository to publish on Github Pages?

*Maybe.*
