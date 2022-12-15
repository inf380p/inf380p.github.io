---
layout: post
author: zengjilie
title: "Final Project Update"
---

## Todo List Check
- [x] Find Website to collect data. )
- [x] Using `BeautifulSoup` to parse **HTML** raw data
- [x] Store data in csv files
- [x] Command-line user interface
- [X] Provide answers to each questions
- [x] Print Bueautifier
- [x] Add wait time to mimic data fetching 

## Reflections 
This was a very challenging but also fun task for me. I'm a huge YouTube obsessive, so I chose YouTube facts as the topic.
I spent a lot of time finding the perfect data for my project. Unfortunately, the only website, "socialblade.com", which satisfies my needs is not a free resource, so I figured out I could use a Python scraper to extract all the data from the website.

### Did I achieved my goals?
Yes, especially the parsing HTML part. Using regular expressions is one of the most difficult parts of this project.

### Setbacks
I shouldn't have used a traditional for loop.
```python
all_lines = ...
for i in range(len(all_lines)):
  all_lines[i] = '|' + all_lines[i][:div_index] + '|' + all_lines[i][div_index] + '|\n'
```
Instead, I can just use this one-line for loop, which is a cleaner approach
```python
all_lines = ['|' + i[:div_index] + '| ' + i[div_index:] + '|\n' for i in all_lines]
```
### What have I learned?
- Beautiful Soup
- Pandas
- Regular expression
- f-string


### What could be done better? 
I could add some data visualization to make the interface more engaging.

## Demo
<iframe src="https://trinket.io/embed/python3/fe7464ca7b" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen>
</iframe>
