---
layout: post
title: jekyll github pages restart
date: '2021-02-07T13:27:00.001-07:00'
author: rabbitear
tags: Jekyll Github-Pages
modified_time: '2021-02-07T13:27:00.001-07:00'
---
## Game plan
:todo-lists:
* [✓] Read primer on Jekyll
* [✓] Read how Fedora should handle rubygems
        - What does bundler do?
* [○] Do it

Questions:
- Q: Do I really need to use the github recommended version of the gems?
- A: Should, or the site might look weird.

## Jekyll with Github Pages
0) ``gem install jekyll bundler`` <-- this is *WRONG*, all I have to do is
   install _bundler_ somehow.

1) Then I make a Gemfile, inside the rabbitear.github.io repo:
   `bundler init` will make a simple Gemfile, then I can add to it:
   `gem "github-pages", "~> VERSION", group: :jekyll_plugins`
   Look up on the github jekyll dependences site the *VERSION* number,
   which at the time was 211, at: https://pages.github.com/versions/

2) be in the repo and: `bundler install` this will install the correct
   versions of things, because of the "github-pages" gem being in the
   Gemfile.

3) Run it `bundler exec jekyll serve`, Site is served at 
   http://127.0.0.1:4000 by default, changes made
   while the server is on, will automaticly be updated.

## Configuration of Jekyll
Configuration happens in __config.yaml_ file.
Ex of the file:
```yaml
title: My Cute Jekyll Blog
email: me@mycutejekyllblog.com
description: >-
  This is my cute jekyll blog. I post some awesome stuff every day.
baseurl: ""
url: "https://mycutejekyllblog.com"
twitter_username: MyCuteJekyllBlog
github_username:  MyCuteJekyllBlog
```
When editing the _config.yaml file, you MUST _restart_ the server.

## Creating Posts in Jekyll
All posts have the filename format of *YEAR-MONTH-DAY-title.md*, ex:
`2020-02-07-how-i-started-to-blog.md`.  All posts start with a yaml
syntax called *Front Matter*, code/text between three dashs, ex:
```yaml
---
layout: post
title: Best Tools for Remote Teams
bestTool: SomeTool
---
```
Posts are to be put in the __posts_ directory.
These are variables in jekyll, some are preexisting, others, you can
make new, to use in your post.  Every post must have a layout var.  You
can use the bestTool variable with:
```
{{ page.bestTool }}
```
instead the post.

SEE: https://talk.hyvor.com/blog/creating-a-static-site-blog-with-jekyll-and-github-pages/

## Other Jekyll Things to Try
Privacy focused commenting: https://talk.hyvor.com/
nice blog on what's all in jekyell: https://blog.webjeda.com/jekyll-guide/

Github Actions and Jekyll: https://jekyllrb.com/docs/continuous-integration/github-actions/
From gh marketplace: https://github.com/marketplace/actions/jekyll-actions

