---
layout: post
author: elliott
title: "Final Project Guide: Data Processing"
categories:
- reading
- how-to
external: false
---

Data processing is the process of taking low-value data and adding value to it.

## Find a suitable data source

* Your data source should be plaintext. CSV, TSV, etc. are common formats. But, if you want, you could use raw emails like we did in class. Don't use a Word document or other kinds of files Python can't easily read.
* Your data source should be substantial but not huge. It should be a minimum of hundreds of lines, but no more than a few thousand. If your files get too big Trinket will take a very long time to load.
* Your data should have interesting questions you can ask about it. "Interesting" is of course subjective here, but a list of a hundred names isn't a complex enough data file.

## Define what *more valuable means*

Some of the value you provide is in the interface: displaying data that matches a user need or question. Other value will be in the form of calculation or integration of new data. Translating two-letter codes into US state names, for instance, adds value by making this information more readable. Calculating averages adds value, AND could allow you to display data ranked by average within a given category.


## Python's Standard Library

You **may** use parts of Python's built-in modules, but you don't have to. I'm going to assess how well you use the built-in features of Python, and you might be able to display _more_ fluency by implementing your own way of parsing CSV files, for instance, rather than using the `csv` module. If you use built-in features to make your life easier, great! Make sure to add your own code to do other things, so that you demonstrate your skills.