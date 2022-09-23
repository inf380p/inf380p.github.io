---
layout: post
author: Prakash-sa
title: "Prakash's reflection on the class so far."
---

# Problem statement

Given an integer x, return true if x is palindrome integer. An integer is a palindrome when it reads the same backward as forward. 
For example, 121 is a palindrome while 123 is not.

I implemented the function of above solution in python.

```


def isPalindrome(x: int) -> bool:
  if x < 0:
    return False
  return str(x) == str(x)[::-1]
  
  
print("Enter the number to check whether it is Plaindrome or not")
num=int(input())
print("Is the number palindrome: ",isPalindrome(num))

```

You have to enter the number when the program run and it will give the output whether the number is palindrome or not.

# Example 1:

Input: x = 121
Output: true
Explanation: 121 reads as 121 from left to right and from right to left.

# Example 2:

Input: x = -121
Output: false
Explanation: From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.
Example 3:

# Input: x = 10
Output: false
Explanation: Reads 01 from right to left. Therefore it is not a palindrome.


# My functional trinket
An iframe of my functional trinket can be found below.

<iframe src="https://trinket.io/embed/python/cdbbdec50e" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
