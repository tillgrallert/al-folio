---
layout: post
title: "XSLT functions for converting calendars"
author: Till Grallert
date: 2013-07-04
categories:
- blog
tags:
- calendars
- tools
- digital humanities
- xml
- xslt
---

Recently I came across the necessity of converting Islamic *hijrī* dates to Gregorian dates in order to automatically harvest data from the Baṣbakanlik Osmanli Arṣivi's catalogue into my research database. Unfortunately the database I use (the reference manager Sente) is proprietary software that can only deal with Gregorian dates. Thus, I needed to translate a certain string through XSLT in order to produce the correct XML for import into the database. I soon discovered that even though, formally the specifications for the format-date() function in XPath 2.0 include the *hijrī* calendar (labelled "Islamic") and even Arabic month names, this specification was never actually implemented.
As I could not find any available code on the net, I adopted the javascript conversion between Gregorian, Julian, and Hijri calendars provided by John Walker's Calendar Converter for XSLT 2.0 and decided to share the functions on [GitHub](https://github.com/tillgrallert/xslt-calendar-conversion) for reuse.
