---
layout: post
title: "Academic writing in plain text: useful resources"
author: Till Grallert
date: 2015-07-20
published: false
categories:
- blog
tags:
- links
- tools
- resources
---

This post is more of a continuously updated note on possible workflows that are based on plain text and the principles of minimal computing.

# Plain text and MarkDown

## AcademicMarkdown

## CriticMarkup

[CriticMarkup](http://macdrifter.com/2013/02/everyones-a-critic-the-critic-markup-language-proposal.html): extension to MMD for editorial markup of texts. The project website is [http://criticmarkup.com/](http://criticmarkup.com/) and the code is hosted on [GitHub](https://github.com/CriticMarkup/CriticMarkup-toolkit)

- Integration into tools:
    + Sublime Text 3's AcademicMarkdown package supports syntax highlighting for CriticMarkup
    + There is a CriticMarkup [SL3 package](https://github.com/CriticMarkup/CriticMarkup-toolkit/tree/master/Sublime%20Text%203%20Package/). It is not managed by package control and a documentation can be found [here](http://criticmarkup.com/sublime-text.php)
    + The [CriticMarkup toolkit](https://github.com/CriticMarkup/CriticMarkup-toolkit) contains processors for various programs but not for Sublime Text.
    + [Integration of CriticMarkup and Pandoc](http://vitruviandesign.blogspot.com/2014/05/more-reasons-to-love-markdown-plus.html)

+ Basic Syntax
    * Addition `{++ ++}`
    * Deletion `{-- --}`
    * Substitution `{~~ ~> ~~}`
    * Comment `{>> <<}`
    * Highlight `{== ==}{>> <<}`

# KramDown

An extension of MarkDown with a strict, unambiguous syntax used in Jekyll. The documentation of the syntax can be found [here](http://kramdown.gettalong.org/syntax.html).

# Pandoc and Jekyll

Pandoc can be used as standard processor for markdown in jekyll with the help of small [plugins](http://jekyllrb.com/docs/plugins/). However, one cannot use any plug-ins if jekyll is run on GitHub-pages, which operate in safe-mode. There was a lengthy discussion on the [jekyll forum](https://github.com/jekyll/jekyll/issues/1973) whether or not to include pandoc as a markdown processor. Unfortunately this has been rejected by the jekyll team.

The advantage of pandoc as markdown processor would be support for image captions etc.

## [Another pandoc plugin for jekyll](https://github.com/fauno/jekyll-pandoc-multiple-formats)



##  [jekyll-pandoc](https://github.com/mfenner/jekyll-pandoc)

To install it via terminal type

`$ gem install jekyll-pandoc`

It can then be referenced in one's site's `_config.yml` as `markdown: pandoc` after the following has been added:

~~~
gems:
    - jekyll-pandoc
~~~


## [jekyll-pandoc-plugin](https://github.com/9peppe/jekyll-pandoc-plugin)

This was originally designed to work with jekyll 1.x. Some forks have been updated to provide compatibility with jekyll 2.x and 3.x


# Git / GitHub

- Chad Black's [getting started with github and prose.io](https://parezcoydigo.wordpress.com/2013/08/26/getting-started-with-github-and-prose-io/) on using a combination of GitHub, jekyll, and prose.io for a collaborative seminar [blog](http://dh.chadblack.net/info/all_posts/).
- [GitHub, Academia, and Collaborative Writing](http://www.hastac.org/blogs/harrisonm/2013/10/12/github-academia-and-collaborative-writing)
- [Push, Pull, Fork: GitHub for Academics](http://www.hybridpedagogy.com/journal/push-pull-fork-github-for-academics/)
- [GitHub for Academics: the open-source way to host, create and curate knowledge](http://blogs.lse.ac.uk/impactofsocialsciences/2013/06/04/github-for-academics/)
- [Living in a Plain Text World (Tools We Use)](http://savageminds.org/2013/02/15/living-in-a-plain-text-world-tools-we-use/)
- [This software for academic paper writing is inspired by Git](http://technical.ly/brooklyn/2014/09/12/authorea-software-for-academic-paper-writing-is-inspired-by-git/)
- [How To: Use Git to Version Your Writing](http://www.lifehack.org/articles/technology/how-to-use-git-to-version-your-writing.html)
- [Using git in my writing workflow](https://www.martineve.com/2013/08/18/using-git-in-my-writing-workflow/)

# Jekyll

- Tags in Jekyll / GitHub pages
    + [Tags in jekyll](http://charliepark.org/tags-in-jekyll/)
    + [How To Use Tags And Categories On GitHub Pages Without Plugins](http://www.minddust.com/post/tags-and-categories-on-github-pages/)
- Pandoc
    + [Another pandoc plugin for jekyll](https://github.com/fauno/jekyll-pandoc-multiple-formats)
- Jekyll themes
    + [Poole, Jekyll's buttler](https://github.com/poole/poole): editor for Jekyll themes, at the moment at least two themes are available and GO::DH Minimal Computing SIG used it to build its website
- Plug-ins: if hosted on GitHub, jekyll runs in safe mode and disables third-party plug-ins
    + [Jekyll-hook](https://developmentseed.org/blog/2013/05/01/introducing-jekyll-hook/)
- add image captions:
    + [with an include tag](http://codingtips.kanishkkunal.in/image-caption-jekyll/)

## Liquid templating

Liquid templating was designed by and for the shopify website: "Liquid is an open-source, Ruby-based template language created by Shopify. It is the backbone of Shopify themes and is used to load dynamic content on storefronts."

- [Liquid template engine](http://wiki.shopify.com/Liquid)
- Great overview of [syntax and commands](https://github.com/Shopify/liquid/wiki/Liquid-for-Designers)
- [Jekyll Date Formatting Examples](http://alanwsmith.com/jekyll-liquid-date-formatting-examples) using liquid

## Images in Jekyll

the standard markdown syntax of `![caption, alt text](path to image file)` works with jekyll, but the alt text is not written to a caption element etc.

A [comment on stackoverflow](http://stackoverflow.com/questions/19331362/using-an-image-caption-in-markdown-jekyll) suggests to generate a new template file called `image.html` in `_includes`

~~~{.html}
<figure class="image {{include.class }}">
    <a href="{{ include.url }}">
        <img src="{{ include.url }}" alt="{{ include.description }}">
        <figcaption>{{ include.description }}</figcaption>
    </a>
</figure>
~~~

and then to call this template with

~~~{.}

![My cat, Robert Downey Jr.](/assets/my-cat.jpg)

~~~

The regex to replace existing markdown image links with the new liquid ones is:

1. find: `!\[(Page.+)\]\(\{\{site.baseurl\}\}(/assets/.+.png)\)`
2. replace>

## Post preview in jekyll

add `excerpt_separator: <!--more-->` to _config.yml or the YAML block of your individual post.