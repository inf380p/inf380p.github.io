---
layout: post
author: atUtexas
title: “One Modification in my Final Project” 
---

One Modification in Final Project

My initial plan was to compile a few of my user research surveys and create a data program requesting certain questions to reveal specific answers. Because there were only four respondents in each of the three surveys, there were only 12 total participants, so it didn't meet the project's parameters. Additionally, each survey had different questions, so it was going to get messy. 

My new plan was to sort data from a survey gathered for a Booster Club. This was a better idea because it had 100 participants, and all the same questions were asked. I spoke to my group in detail about my plan. I mentioned that I had been stuck on an issue with separating each column and requesting the program print each column separately. My group members suggested that I keep trying, and I appeared to be close to a resolution.

Fixed Issue

I was able to keep troubleshooting and  was finally able to get the print to run correctly. Here is my updated code to print columns :

```
elif choice_str == "3":
    columns_to_print = get_columns_to_print()
    
    for key in columns_to_print:
    
      for row in row_dicts_list[0:]:
        print(row[key])

```

Thank you for reading.
