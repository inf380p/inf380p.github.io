---
layout: post
author: JamesAthrun
title: "JamesAthrun's Reflection on the Class So Far"
---

# Reflection Text:
I think starting from turtle to draw something amazing is really a good point of learning python. Because turtle, as a white board, can let me see what they have done and feel satisfactory. 

For confusion, I do think the some of the python codes are a little bit hard to understand and make me feel puzzled. But I can always try to change the parameter of turtle functions to see what has changed, which will give me a hint of the true meaning of the code.

Currently, I do not have fuzzy things in the codes which I have completed.

I think the best code-learning strategy is to write code on my own. Knowing which code can work and which can not is grealy helpful for coding. Besides, the document of turtle is another great assistance in reading and writing codes.

# Interaction Code
<iframe src="https://trinket.io/embed/python/464cc7b37b" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

```python
## code example
def draw_rainbow(colors, num):
  for x in range(num):
    pencolor(colors[x % 6])
    width(x / 5 + 1)
    forward(x)
    left(20)
