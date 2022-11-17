---
layout: post
author: amptex101
title: "Allison (amptex101) Final Project Interface Update"
---

### What I'm doing 

I decided upon data processing for my project; specifically, I want to make a data processing program that browses rows, columns, and deletes columns from the CSV file that I chose --  scottish witchcraft trials. I got the CSV set from data.world, and it has served me well. Basically, this file contains data from the trials of hundreds of men, women and children who were allegedly engaged in pacts with the devil in Scotland between 1563 and 1736. It does contain more columns than are necessary, so I wanted to add the delete columns function to clean up the dataset. 

```
menu_dict = {
  "1" : "Browse Rows",
  "2" : "Browse Columns",
  "3" : "Delete Columns",
  "4" : "Exit"
}
```

This first block of code above creates a menu. I basically took this from the class assignment we did previous, and made sure my choices (1-4) were labelled correctly.
