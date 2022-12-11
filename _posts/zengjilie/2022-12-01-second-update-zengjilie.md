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
- [ ] Print Bueautifier
- [ ] Add wait time to mimic data fetching 

## What did I learned
- A new python package called `pandas`
- Merging two different csv files using `pd.merge`
- Applying lambda function all the value of a sepecific column

## Setbacks
- There are a lot of bugs when I was dealing with pandas
For example, when I was using `sort_values`

```python
# works
tmp = data.sort_values(by=['subs_new'], ascending=False)['channel_name'][0:10].to_string(index=False)
# doesn't work
tmp = data.sort_values(by=['subs_new'], ascending=False)['channel_name','subs'][0:10].to_string(index=False)
print(tmp)
```
It turns out I cann't use `['channel_name', 'subs']` like this. The right way is to use it like this:  
```python
data['subs_new'] = data['subs'].apply(lambda x: format_numbers(x))
tmp = data.sort_values(by=['subs_new'], ascending=False)
print_beautifier(tmp[['channel_name', 'subs']][0:10].to_string(index=False))
```

## Demo
<iframe src="https://trinket.io/embed/python3/1858e92d28" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen>
</iframe>
