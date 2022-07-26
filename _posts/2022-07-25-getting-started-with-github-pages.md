---
title: Getting Started with Github Pages
categories:
- Git
- Github Pages
- Jekyll
---

2022-07-25-getting-started-with-github-pages.md

How does a page look without its feature image?

Professionals often benefit from websites. Portfolios, showcases, blogs. Many platforms offer user-friendly web-hosting and website creation.

I've dabbled in Weebly, Wix, GoDaddy, and others. It's all rather complicated, and the most user-friendly interfaces are still... interfaces.

After more than a decade in computer science, technology, and problem-solving, I decided to try something entirely new to me: Github Pages and Jekyll.

Jekyll is a static-site generator. You specify aspects of the website you want Jekyll to build for you in structures and syntax that Jekyll understands, and then invoke Jekyll to create an HTML website to your specifications. CSS, or Sass (CSS' older, cooler, more theme-friendly sibling), JavaScript, and many plugins are available to enhance functionality and provide more building blocks with which to assemble a site.

## Why Github Pages?

It started with a simple search for inexpensive options to host a website; Wix and the like, which offer robust functionality, can feel pretty steeply priced and easily start at around $150 USD/year -- not counting the price of leasing a domain.

[Github Pages](https://pages.github.com/) is a way to host a website on Github from a repository. I feel it's an awesome possibility to host documentation for projects. It's free, integrated with git, and supports Jekyll out-of-the-box.

I felt compelled to explore Jekyll because I consider html-focused websites to be far faster to load and smaller in memory and storage than some fancier, more modern-seeming alternatives. They archive and share well too -- perfect for knowledge resources like blogs and docs. Plus, I've done a lot of web development, usually in the Microsoft .NET/C#/ASP technology family, and Jekyll is new to me; it represents a different perspective on web development, and an alternative method of creation and maintenance.

Besides -- I always welcome another tool in the toolbox.

## Searching for Themes

Github has a [list of supported Jekyll themes for Github Pages sites](https://pages.github.com/themes/), but I always get a little too interested in searching for themes and styles.

Turns out, there are a [*lot* of themes on Github](https://github.com/topics/jekyll-theme). They range from simple to impressively robust, and from free to premium. After eyeing [Hydejack](https://github.com/hydecorp/hydejack) for a while, I discovered [Alembic, by David Darnes](https://github.com/daviddarnes/alembic).

*Spoilers: this site is based on Alembic.*

### Implementing a Theme

It's important to note that **Github Pages themes are not entirely the same as Jekyll themes.** [Jekyll supports themes in its own way](https://jekyllrb.com/docs/themes/). Jekyll allows creators bundle themes into gems, packages of Ruby code, which can them be included in a Jekyll project's Gemfile, something like a package manifest. Github Pages accomplishes its theming with a custom `github-pages` gem and a `jekyll-remote-theme` Jekyll plugin.

Github Pages -- and the wider internet -- has instructions on how to incorporate a theme into your Github Pages site; there are several methods:
- [Using the Theme Chooser](https://docs.github.com/en/pages/getting-started-with-github-pages/adding-a-theme-to-your-github-pages-site-with-the-theme-chooser)
- As a remote theme in `_config.yml`, detailed [here in Cayman's README](https://github.com/pages-themes/cayman#usage) and [here in Github Docs](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-a-theme-to-your-github-pages-site-using-jekyll)
- As a repository fork or copy as discouraged in [Alembic's own README](https://github.com/daviddarnes/alembic#as-a-boilerplate--fork)

I opted for... none of the above.

Some more searching led me to the blog of Matthias Lischka, who just so happened to have authored an [article on the subject](https://matthiaslischka.at/2018/12/03/github-jekyll-best-practice/). 

What Matthias recommends is something I've known is possible in git since I first learned git around 2016 -- cleverly using multiple remotes to manage multiple repositories.

At the end of setup, you have 3 repositories with their own responsibilities:
- `origin` - your website's publishing source repository, where the content of your site will live. Pages, posts, logos, etc.
- `upstream` - your theme's repository; in my case, [Alembic's repository](https://github.com/daviddarnes/alembic)
- `personalUpstream` - a fork of your theme's repository for any custom changes that aren't content-related. This might include new features (or feature removal), etc.

Your content goes to `origin` and stays yours; to potentially swap to another theme, you simply rebase your content on top of the new theme's history and modify `upstream` and `personalUpstream` accordingly.

Getting updates from the theme's repository in `upstream` is easy this way and keeps everything nice and cleanly separated.

I'm very comfortable with single-repo operations in git; I've used it for more than 6 years, personally and professionally. Setting up my website's structure this way let me try out something new -- multiple `remotes` -- and is letting me deepen my git knowledge further.
