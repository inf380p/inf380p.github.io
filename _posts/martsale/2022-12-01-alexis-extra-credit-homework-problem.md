---
layout: post
author: martsale
title: "Alexis's Extra Credit Homework Problem"
---

# Clarifying how to parse files

For extra understanding of the class this semester, I went back to problem 8.14.15 from the files section. When I originally did this chapter, I struggled with splitting out data files. Since my final project is centered around analyzing a text file, I wanted to do this homework problem because it's similar to the problem I'm facing with my project. 

I'm glad I waited a while to come back to this assignment. The chapter after files is about lists, and understanding how to handle lists really helped me solve this problem. 

When I first started it, I thought it would be a fairly quick solve. However, as I started writing code, I realized there were several problems to solve to get the final result. This is the order that I solved the problems in:

1. First I split out the data into the values I needed
2. I added logic to check for the month and appended it to the `closing_values_list`
3. Next I did the calculation to find the average
4. Finally I wrapped everything in a function

It took me a bit to get the values to append to my list. After refreshing my python list knowledge, I realized that I was calling `append.closing_values_list(closing_value)` instead of `closing_values_list.append(closing_value)`. Once that was solved, the list populated. 

I got stuck with calculating the average because the closing values are a `float` and the average was coming in as an `int`. Once I did some problem solving by using `print(type())`, I realized I needed to convert the `int` to a `float`.

Working through this reaffirmed using `print` to problem solve, and helped me fully understand how to separate data. 

Here is the homework problem I was solving:

>Write a function avg_month_close(lines, month) that takes the lines from the stocks file in a list and the abbreviation for a month (i.e. “Jan”, “Feb”) as parameters and returns the average value of the closing prices during that month for all the years in the file. Each line has: Date, Open, High, Low, and Close. The Date is in the format day-month-yy. The month is just the first three letters of the month.


Here is my final, working solution for the problem:
```
file = open("stocks.txt", "r")
def avg_month_close(lines, month):
    closing_values_list = []
    lines = file.readlines()
    for line in lines:
        values = line.split(",")
        closing_value = values[4].strip()
        dates = values[0]
        date = dates.split("-")
        month_data = date[1]
        if month_data == month:
            closing_values_list.append(closing_value)

    closing_length = len(closing_values_list)

    closing_total = 0.0
    for number in closing_values_list:
        number_float = float(number)
        closing_total += number_float

    closing_average_calculation = closing_total / closing_length
    return closing_average_calculation
```                     
