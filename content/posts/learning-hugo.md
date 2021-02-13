---
title: "Playing with Hugo"
date: 2021-02-13T16:11:23+11:00
tags: ["software-engineering", "blogging"]
categories: ["software-engineering", "blogging"]
draft: false
---

# Getting started with Hugo and static page generation.

I've always been interested in blogging (see my previous wordpress blog for when I would write about what games I was playing, https://weeklygameblog.wordpress.com), but the time/money cost of maintaining a wordpress blog, for what is essentially is a static site was always a little bit over the top. Not to mention, wordpress isn't really the latest and greatest in blogging techonlogies. Recently I learnt about Hugo, and started to play with netlify, after a few iterations (and months of down time), I came up with this blog.

What did I do to get here though? I am running MacOS, so it was as simple as: 

```shell
brew install hugo
hugo new <site name> .
git init
```

Finding a theme (I recommend using https://themes.gohugo.io/ to find something, so many choices. I landed at https://themes.gohugo.io/hugo-papermod/) and importing the theme as a submodule `git submodule add https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod --depth=1` and setting `theme: PaperMod` in my config.yaml file.

and setting up the netlify config ( which is in the source repo for this, feel free to steal it https://github.com/Jacko161/Jackson-Blog/blob/master/netlify.toml ).

I've configured to auto deploy the site with each push to the master branch, this means no messing around with saving or logging into a crappy page editor. Just write some markdown, and run a  `git push`, easy as!
