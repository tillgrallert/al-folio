---
layout: post
title: "Project Jaraid: our new chronology of nineteenth-century Arabic periodicals is online"
author: Till Grallert
date: 2012-09-02
categories:
- blog
tags: 
- 19th century
- arabic newspapers
- digital humanities
- history of press
- newspapers
- ottoman newspapers
- periodicals
- tei
- xml
- xslt
---



After some time out, I return to this blog to announce yesterday's publication of my first ever paid-for website and digital humanities project. Called "Project Jarāʾid – A chronology of nineteenth century periodicals in Arabic" the website is hosted by the [Zentrum Moderner Orient Berlin](http://www.zmo.de/jaraid). Based on a simple analogue table provided by Adam Mestyan and Philip Sadgrove (both nowadays in Oxford), I developed a static HTML page that provides the chronology in tabular form, including information on date of first publication, names of publishers, places of publication, and known holding information. In addition, we provide indexes of persons, organisations, places, and holding institutions, as well as a density map of all periodicals we could trace. As a further experimental feature, we included an index of all languages besides Arabic, such as Ladino, Ottoman, French, English, Spanish, various Arabic colloquiuals etc. The website, we hope, will help all those researchers interested in periodicals als a source for their historical accounts to a) establish possible sources, and b) to locate them for their actual research.

At the moment an update cycle of every 3 months is scheduled and we already implemented various contributions from colleagues.

All this was done using extensive semi-automatic XML mark-up of the original table employing the TEI P5 standard. The HTML is then provided through a series of XSLT transformations applied to the single TEI source file. This structure provides enough leeway for future improvements of both the interface and the data. An Arabic version, for instance could easily implemented without much changes to the XSLT and the CSS.