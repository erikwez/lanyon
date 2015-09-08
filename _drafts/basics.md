---
layout: post
title: Basic Markdown
date: 2015-08-30
excerpt: Some (multi)markdown testing with Jekyll and Lanyon
categories: markdown
tags:
    - tables
    - footnotes
    - image
---

# Start with header 1

And a nice table. Nothing too fancy


| header1 | header2 | header3 |
| ------- | :-----: | ------: |
|  data   |  data   |  data   |
|  data   |  data   |  data   |
|  data   |       data       ||

A quote

> If you find yourself in a hole, the first thing to do is stop diggin’. ~ Cowboy wisdom

## This is header 2

Time for a footnote [^1].

And how does `code`display?

And a script

{% highlight py %}

#!/usr/bin/env python
# -*- encoding: utf-8 -*-
"""
Author: Seth Brown
Description: description
"""
from src import formd
from distutils.core import setup

setup(
    name='formd',
    version=formd.__version__,
    description='A Markdown formatting tool',
    author='Seth Brown',
    author_email='sethbrown@drbunsen.org',
    url='http://drbunsen.github.com/formd/',
    packages=['', ],
    scripts=['src/formd.py', ],
    requires=['markdown (>=2.0)', ],
    license='MIT',
    long_description=open('README.md').read(),
)


{% endhighlight %}


{% highlight yaml %}

# Permalinks
#
# Use of `relative_permalinks` ensures post links from the index work properly.
permalink:           /:year/:title
relative_permalinks: true

# Dependencies
markdown:         kramdown
kramdown:
    input: GFM
#highlighter:      pygments

# Setup
title:               erikwb.net
tagline:             'Whatever escapes'
description:         'Just some of my ramblings.'
url:                  http://localhost:4000
baseurl:             ''
paginate:            5

# About/contact
author:
  name:              Erik Wessel-Berg
  url:               https://twitter.com/erikwb
  email:             erik@wez.no

# Custom vars
version:             1.0.0

{% endhighlight %}


[^1]: Footnotes are always nice
