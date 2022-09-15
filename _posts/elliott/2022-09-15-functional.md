---
layout: post
author: elliott
title: "Flow of Control with function (+ catch up)"
category: notes
published: true
inprogress: false
mode: "In person"
---

Catch-up! It might feel like we're "Behind". Don't worry: I give you the chance to go over things again and again. And I repeat things. That's critical for learning and so that's why we do it!

Outline of today's aspiration.

* Textbook check-in: How's it been for you?
* Variables


* Debugging
* Logical turtles review
* Conditionals
 

* Approx 2:10pm: Functions Preview
* Flow of Control
* Refactoring: Functional Turtle

By around 2:10 I'd like to be onto the functions preview. and hopefully help you refactor some Turtle before class ends. *Anything we don't get to, go through as part of your homework*.

<h2><span>Variables</span></h2>
<p><span>This is a console:</span></p>
<p><iframe title="embedded content" src="https://trinket.io/embed/python/b7c6c3a9f3?toggleCode=true&amp;runOption=console&amp;start=result&amp;runMode=console" width="100%" height="600" allowfullscreen="allowfullscreen"></iframe></p>
<p><span>It&nbsp;<strong>reads</strong>, <strong>evaluates</strong> and&nbsp;<strong>prints</strong> any expression you type in. In programming generally this is also called a read, evaluate, print loop, or REPL.</span></p>
<p><span>The <code>&gt;&gt;&gt;&gt;</code> is what Python shows at its default prompt. So now you know, if you see this in examples online, they're describing what would happen if you were to enter this into a REPL.&nbsp;<em>Aside: If you've ever used Python in a&nbsp;<strong>notebook</strong> this is also what happens: results are printed automatically. This leads to confusion about&nbsp;<strong>Flow of Control</strong>, which is why we won't use notebooks in this class.&nbsp;</em></span></p>
<h3>Let's Code, Shall We?</h3>
<p><span>Let's dive into an apparently simple problem:</span></p>
<p><iframe title="embedded content" src="https://trinket.io/embed/python/b433ddd080" width="100%" height="600" allowfullscreen="allowfullscreen"></iframe></p>
<p><span>OK let's debug some code. There are at least 3 things wrong with this program. Let me tell you what it should do, and let's identify the errors, categorize them as logical or semantic, and fix the code to do what I told you it would do.</span></p>
<p><span>Along the way let's figure out how to make debugging faster by commenting out the input statements.</span></p>
<p style="padding-left: 40px;"><span>Write code below to get at least 3 values from the user using the&nbsp;<code class="docutils literal notranslate"><span class="pre">input</span></code>&nbsp;function and output a mad lib (which will use the input to tell a silly story).</span></p>
<p><iframe title="embedded content" src="https://trinket.io/embed/python/da29ee603b" width="100%" height="600" allowfullscreen="allowfullscreen"></iframe></p>

<h2><span>Conditionals</span></h2>
<p>Here's a series of examples that give you an initial framework to start with, and demonstrate how crafting and running slightly different examples can help you learn.</p>
<p><strong>If</strong></p>
<pre>num = 2<br /><br />if num &gt; 0:<br />  print("Greater than 0")<br />if num &gt; 1:<br />  print("Greater than 1")<br />if num &gt; 2:<br />  print("Greater than 2")</pre>
<p>How many of these things print? <strong>Why?</strong></p>
<p><strong>Else If</strong></p>
<pre>num = 2<br /><br />if num &gt; 0:<br />  print("Greater than 0")<br />elif num &gt; 1:<br />  print("Greater than 1")<br />elif num &gt; 2:<br />print("Greater than 2")</pre>
<p>How many of these things print? <strong>Why?</strong></p>
<p><strong>Else if again</strong></p>
<pre>num = -2<br /><br />if num &gt; 0:<br />  print("Greater than 0")<br />elif num &gt; 1:<br />  print("Greater than 1")<br />elif num &gt; 2:<br />print("Greater than 2")</pre>
<p>How many of these things print? <strong>Why?</strong></p>
<p><strong>Else</strong></p>
<pre>num = -2<br /><br />if num &gt; 0:<br />  print("Greater than 0")<br />elif num &gt; 1:<br />  print("Greater than 1")<br />elif num &gt; 2:<br />  print("Greater than 2")<br />else:<br />  print("Not greater than 0, 1, or 2")</pre>
<p>How many of these things print? <strong>Why?</strong></p>
<p>These are the kinds of experiments you might set up for yourself when you're&nbsp;<strong>asking Python questions in Python code.</strong></p>
<h3>Flow of Control!</h3>
<p>Conditionals are great, but can get complex fast when they're&nbsp;<strong>chained</strong> and&nbsp;<strong>nested</strong>. This is our first introduction to&nbsp;<strong>Flow of Control</strong>, which is a fancy way of saying "what's Python doing now? why?"</p>
<p>Much more about this, but pay attention to what Python's doing, and why, throughout this chapter. Conditionals are a core feature that help us modulate what python's doing.</p>
<h3>Recommended Skill: Read First</h3>
<p><strong>I highly recommend practicing your code Reading skills on this chapter. </strong>Go line by line, trying to figure out what Python is doing there. In doing that, you're starting to get practice internalizing Flow of Control through understanding conditionals. You'll notice that order of conditionals can matter a lot, as will whether there's an <code>else</code> statement ensuring that&nbsp;<em>something</em> will happen even if all the conditional statements return <code>False</code></p>

<h2>Conditionals, Booleans, and Flow of Control</h2>

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

* *Flow of Control*: Python does things in a specific order. Sometimes it'll not execute some code, and any *runtime errors* in that code won't appear until or unless it does.
 
<h2>Flow of Control: What's Python Doing, and Why?</h2>
<p>Some chapter concepts:</p>
<ul>
    <li><strong>Boolean Expressions.</strong> They evaluate to <code>True</code> or <code>False</code></li>
    <li><strong>Logical Operators. </strong>Specify how to turn<strong> data types </strong>of various kinds into<strong>&nbsp;</strong><code>True</code> or <code>False</code>.&nbsp;</li>
    <li>Execution types:
        <ul>
            <li>Conditional: only <code>if</code></li>
            <li>Alternative: this or that</li>
            <li>Chained: do one thing (<code>if</code>, followed by zero or more <code>elifs</code>, and an <code>else</code>), or do one or zero things (no <code>else</code>)</li>
            <li>Nested: layers of conditions</li>
        </ul>
    </li>
    <li><strong>Exceptions</strong>
        <ul>
            <li>One way to say to Python "I know an error might happen here. If so, do this instead of what you normally do"</li>
        </ul>
    </li>
    <li>Understanding order of evaluation matters: 'short-circuiting'</li>
</ul>

<h2>Functions: Repeatable Units of Modifiable Code</h2>
<p>Functions are awesome!</p>
<p>So awesome, in fact, that we'll touch on them throughout the rest of class, including the next several weeks.</p>
<p>So far, most of our code has been all the way to the left, unindented. if statements have indented blocks: that's the first instance we've seen of code being&nbsp;<em>inside</em> other code.&nbsp;</p>
<p>Conditionals&nbsp;<em>maybe</em> execute the code inside them. Functions use the code inside them in a different way:</p>
<ul>
    <li>Function <strong>definitions</strong> tell Python to remember code for later. <em>Nothing else is done when a function is defined</em>.</li>
    <li>Function <strong>calls</strong> tell python to go execute the code in the function.</li>
    <li>Functions can be defined such that Python is expecting some extra information,&nbsp;<strong>arguments</strong>, when you call them. These arguments can change the behavior of the function when you call it different ways. Or, they can be defined to not need any kind of input.</li>
    <li>Functions can de defined to <code>return</code> something. If they do, nothing else will happen unless that&nbsp;<strong>return value</strong> is stored or computed upon.</li>
</ul>
<p>Functions are a fundamental concept in programming, and a powerful tool for making programs do cool stuff.</p>