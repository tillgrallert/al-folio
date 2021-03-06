---
layout: post
title: "New XSLT stylesheets for calendar conversion on Github"
author: Till Grallert
date: 2014-01-04
categories:
- blog
tags:
- xml
- xslt
- tools
- digital humanities
- calendars
---

A couple of months ago a posted [a short note]({% post_url 2013-07-04-xslt-calendar-conversion %}) on my XSLT stylesheets to convert the various calendars at use in the late Ottoman empire at will. Now, I have improved the functions and added the Ottoman fiscal calendar (*mālī*, *sene-yi māliye*) to the brew and uploaded everything under a [CC BY-SA 3.0 license](http://creativecommons.org/licenses/by-sa/3.0/) to [GitHub](https://github.com/tillgrallert/xslt-calendar-conversion). Feel free to fork and tinker with the code. Enjoy!

## General description

The single stylesheet in this repo was conceived as a remedy for the bugs in the XPath specification that prevent the computation of Islamic (*hijrī*) dates. As I was, at the same time, working on the transcription of Arabic and Ottoman Turkish sources from the nineteenth century, which made use of Gregorian, *hijrī*, *rūmī*, and *mālī* calendars, into XML files, I also wanted to reliably compute conversions between the various calendars.

In addition to numerical dates, the stylesheet provides a function that returns the common month names.

Detailed descriptions of the functions and their parameters can be found inside the stylesheet.

## Characteristics of the non-Gregorian calendars

- ***Hijrī*** reckoning relies on the observation of the lunar year. Year counts began with Muhammad's exodus (*hijrā*) from Mecca to Medina. *Hijrī* dates cannot really be computed as observations of the new moon varied between locations. The stylesheet uses common astronomical computations of the lunar calendar.
- ***Rūmī*** reckoning is a Julian calendar that adopted 1 January as the beginning of the year. As the rules for leap years are slightly different between Julian and Gregorian calendars, the difference between these two is slowly increasing (currently 13 days).
- ***Mālī*** reckoning is a combination of the old Julian calendar beginning on 1 March and a *hijrī* year count, that was introduced as the fiscal calendar of the Ottoman Empire in 1676. Every 33 lunar years, the year counts between *mālī* and *hijrī* calendars are synchronised by dropping a year.

## Templates

- Templates for the conversion between calendars:
	+ funcDateG2H
    + funcDateG2J
    + funcDateG2JD
    + funcDateG2M
    + funcDateH2G
    + funcDateH2J
    + funcDateH2JD
    + funcDateH2M
    + funcDateJ2G
    + funcDateJ2H
    + funcDateJ2JD
    + funcDateJD2G
    + funcDateJD2H
    + funcDateJD2J
    + funcDateM2G
    + funcDateM2H
    + funcDateM2J
- Templates for converting Date formats
    + funcDateMonthNameNumber
    + funcDateNormaliseInput
    + funcDateFormatTei

## Input / Output

- Input and output for all templates converting dates between the various calendars is as follows: "yyyy-mm-dd"
- The template "funcDateFormatTei" accepts the same input but produces a `<tei:date>` note with `@when` or `@when`, `@when-custom`, `@calendar`, and `@datingMethod` attributes depending on the input calendar.
- The template "funcDateNormaliseInput" can be used to convert variously formatted input  strings to the yyyy-mm-dd required by other templates. Possible input formats are  the common English formats of 'dd(.) MNn(.) yyyy', 'MNn(.) dd(.), yyyy', i.e. '15  Shaʿbān 1324' or 'Jan. 15, 2014'. The template requires an input string and a  calendar-language combination as found in funcDateMonthNameNumber.