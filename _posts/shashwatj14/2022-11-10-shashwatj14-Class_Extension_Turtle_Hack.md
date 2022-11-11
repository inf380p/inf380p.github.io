---
layout: post
author: shashwatj14
title: “Shashwat's Class Extension turtle"
---

I created a class with a custom function - Overridden the Dunder function and chnaged the tutle parameters. (shape and color)

Created a function to draw the shape required:
```
  def draw(self, shape, size):
    if(shape == "circle"):
      self.circle(size)
    elif(shape == "square"):
      self.square(size)
    elif(shape == "triangle"):
      self.triangle(size)
```

Here's my trinket:
<iframe src="https://trinket.io/embed/python/a293a02771" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

