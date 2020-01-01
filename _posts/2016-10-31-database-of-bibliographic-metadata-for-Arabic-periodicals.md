---
layout: post
title: "Project: a database of bibliographic metadata for Arabic periodicals"
author: Till Grallert
date: 2016-10-31 10:40:50 +0100
categories:
- blog
tags:
- 19th century
- arabic newspapers
- history of press
- newspapers
- periodicals
- digital editions
- bibliographic metadata
- tools
published: false
---

In addition to actual digital editions, the project "Open Arabic Periodical Editions" ([OpenAraPE](https://www.github.com.OpenAraPE)) should have a second component, which is much easier to implement: a database of bibliographic metadata.

## project goals

+ provide stable and reliable bibliographic metadata for as many early Arabic periodicals as possible
+ provide metadata in standard form and through computationally accessible interfaces (MARC XML, MODS, Zotero API)
+ metadata should include
    1. first level: data that can be computed (based on known parameters and more important for newspapers):
        1. publication date
        2. volume
        3. issue
        4. editors
        5. publisher
        6. place of publication
    * second level: data that must be transcribed/ sourced from the actual publications:
        4. article/section title
        5. page range
        6. author

##  methodology

### 1. harvest available metadata

#### http://archive.sakhrit.co/ 

Provides tables of content (HTML) on the item level. There pagination does not necessarily correspond to printed editions and they might no have captured every article, but it's a treasure trove of bibliographic information.

Journals of interest available on this platform include:

- Cairo
    + [al-Muqtaṭaf](http://archive.sakhrit.co/newmagazineYears.aspx?MID=107)
    + [al-Ustādh](http://archive.sakhrit.co/newmagazineYears.aspx?MID=106)
    - [al-Hilāl](http://archive.sakhrit.co/newmagazineYears.aspx?MID=134)
    + [al-Bayān](http://archive.sakhrit.co/newmagazineYears.aspx?MID=161)
    + [al-Manār](http://archive.sakhrit.co/newmagazineYears.aspx?MID=33)
    + [al-Jāmiʿa (al-ʿUthmāniyya)](http://archive.sakhrit.co/newmagazineYears.aspx?MID=114)
    + [al-Zuhūr](http://archive.sakhrit.co/newmagazineYears.aspx?MID=40)
- Lebanon
    - [al-Mashriq](http://archive.sakhrit.co/newmagazineYears.aspx?MID=108)
- Syria
    - [al-Muqtabas](http://archive.sakhrit.co/newmagazineYears.aspx?MID=125)
- Iraq
    - [Lughat al-ʿArab](http://archive.sakhrit.co/newmagazineYears.aspx?MID=14)

#### http://zaydanfoundation.org 

Provides indeces of *al-Hilāl* as custom XML if one digs through their website.

### 2. generate new metadata (second level)

- from TEI editions / shamela html
    + *al-Muqtabas*
    + *al-Ḥaqāʾiq*
    + *al-Manār*