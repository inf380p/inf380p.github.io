---
author: elliott
category: notes
layout: post
title: "Lists, CSV review, & Intro to Dicts"
mode: Remote
published: true
inprogress: false
---

# Announcements

* Added a reading for next week on communicating effectively as a developer.


# Q&A and Vocab
* What questions do you have?


# Dictionaries Preview


The [official Python documention on dictionaries](https://docs.python.org/3/library/stdtypes.html#typesmapping) is helpful - if you konw how to use it. Let's learn how to use it.

<h2>Dictionaries</h2>
<p>Let's use dictionaries to count the total number of emails from a given&nbsp;<strong>domain name</strong> (part after the @).</p>
<p><iframe src="https://trinket.io/embed/python3/9b3c1d3ff8" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe></p>
<p>Let's look at dictionaries in comparison to other methods, on the air pollution problem from the Files chapter:</p>
<p><iframe src="https://trinket.io/embed/python3/e4e02cc580" width="100%" height="756" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe></p>
<h3>Dictionaries and Data Processing</h3>
<p>Imagine a dictionary named <code>city_stats</code> containing statistics for a bunch of US cities. To get the population for Austin, Texas, we could do something like this:</p>
<pre>city_stats["TX"]["Austin"]["Population"]</pre>
<p>This passes the key <code>"TX"</code> to the outer dictionary, which gives a dictionary of Texas cities. Then <code>"Austin"</code> is passed as the key to the dictionary of cities, which evaluates to a dictionary of statistics about Austin. <code>"Population"</code> is then passed to that dictionary, which would give us that statistic. If the data was drawn from 2020, the statement above would evaluate to the integer <code>961855.</code></p>
<p>Even though it'd be very useful, the three-deep nested dictionary of <code>city_stats</code> I'm describing here isn't built in to Python, so we'd have to build it from a raw data file if we wanted to use it in our program.</p>
<p>Building such a <strong>Data Structure</strong> is part of what we mean when we talk about&nbsp;<strong>Data Processing</strong>. A big text file with a bunch of data in it isn't of much use. But once it's digested into a data structure, we as programmers suddenly have lots of power, power we can pass on to users who want to know stats about US cities, for instance. By collecting a City, State, and Statistic type from a user, we could tell them the answer to any question our data could answer.</p>
<p>Appropriate complexity can be difficult. Above I specified that our nested dictionary contained information from 2020. What if we wanted more years? We could:</p>
<ul>
    <li>make a new dictionary for each year (one dictionary per year, each its own variable)</li>
    <li>make the <code>"Austin"</code> dictionary contain years as keys, each of which would then have statistics dictionaries</li>
    <li>make an outer dictionary containing our dictionary as the&nbsp;<strong>value</strong> for the key <code>2020</code>&nbsp;</li>
    <li>make each statistic key, like <code>"Population"</code>, point to a data structure like a dictionary, containing that data for multiple years, instead of the value for a single year.&nbsp;</li>
</ul>
<p>Each of these choices would impact the things that are easy to do with this data structure.&nbsp; The last option, for instance, would make it much easier to get all the data related to a specific statistic over time, since we'd have data for all the years in our data set stored in a convenient data structure each time we looked something up.</p>
<p>A dictionary that stored a bunch of years' worth of data for <code>"Population"</code> would contain key-value pairs like <code>{ 2020 : 961855, 2010 : <span>790491 ....}</span></code>. We could then get the population of Austin for different years easily, at the cost of having to specify a year each time:</p>
<pre>city_stats["TX"]["Austin"]["Population"][2020]<br />city_stats["TX"]["Austin"]["Population"][2010]</pre>
<p>This would make calculating changes in population very easy. The other options would require us to extract data for multiple years, store it in a data structure, and <em>then</em> do the comparison.</p>


# Peer Feedback Review

Let's read and discuss these briefly. 

# Pair Up, Merge Up, and discuss

## 1. Pull Request

Find your partner's pull request and review it for correctness.  Request changes if needed, or Approve. **Practice writing clearly, even though you'll also be able to talk with your partner**.
Help your partner fix any errors, and Approve their changes once they seem correct. Merge the pull request and confirm it's showing on the site (after a minute or two to rebuild)

If the post isn't showing up correctly, help each other navigate to the file via the Code tab to fix anything that you might have missed.

## 2. Read each other's reflections

Take your time doing this, and run your partner's code.

## 3. Discuss your code

Compare and contrast each other's code and reflections.

Some questions for discussion:

1. What was different about this assignment compared to others?
2. What concepts clicked for you in this assignment?
3. What confusions or questions remain?

Help answer each other's confusions or questions if you can, and we'll also discuss them together.


## If time: Merge some outstanding PRs

Find pull requests that you and/or your partner still have outstanding. If *your partner's** PR is ready to be merged (i.e., any errors or requested changes have been addressed), Approve it via a review, and merge.
If there are outstanding requested changes, help each other make them, then merge.

**Do not merge your own pull requests**