---
layout: post
category: notes
title: "Flow of Control with logic and data types"
author: elliott
inprogress: false
mode: Remote (illness)
---

# Part I: Intro

## Announcements

* I had to make class remote this week unexpectedly. Apologies!
* I hope to have about an hour with you before I have to play Dr. Dad

![Don't panic]({{site.baseurl}}/img/dontpanic.jpg)

## Vocab Palette

What things have you encountered, in the readings or elsewhere, that you'd like to make sure I cover in class today?

* Here's a resource on [Python's escape characters](https://www.w3schools.com/python/gloss_python_escape_characters.asp)

# Discussion: Logic and the Flow of Control

Boolean values are very simple but very powerful.  There are tons of useful ways to
construct **expressions** that evaluate to `True` or `False` in Python, and we use these
to change the behavior of our program.

Basic `if` statements act as 'gates' to control whether blocks of code get executed.
`elif` and `else` statements enhance this control.

Some specific concepts to understand:

* *Truithiness*: Everything can be evaluated to either true or false. Most things are true.
* *`try` and `except`*: expecting exceptions (also known as 'errors') in your code. This is *super helpful* for user input. Compare:

<iframe src="https://trinket.io/embed/python3/5cc539fe20" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

...with:

<iframe src="https://trinket.io/embed/python3/8333113d87" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

* *Flow of Control*: Python does things in a specific order. Sometimes it'll not execute some code, and any *runtime errors* in that code won't appear until or unless it does. Let's revisit [the section on short-circuiting](https://books.trinket.io/pfe/03-conditional.html#short-circuit-evaluation-of-logical-expressions).

# Hands-on: Use Conditionals in a Turtle Program

In class, we're going to add conditionals to a turtle program. 

# Reading

Your next reading, Chapter 4, will teach you more about conditionals! Feel free to try out some of what you learn in your Logical Turtles trinket, which you'll bring, and we'll discuss, next week.

# Breakout discussion

Using the Custom Turtle program you brought, discuss your process with your partner. Work on improving your code together.

Afterwards, you may get started on your Logical Turtles program, which you will *bring to class*.