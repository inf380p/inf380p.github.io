---
layout: post
author: elliott
categories:
- how-to
- reading
title: "How to make a good reflection great"
external: false
---

<h3>Taking a reflection from good to great</h3>
<p>We've talked about how to write a good reflection. This page gives an example of how to turn a good reflection into a great reflection with a few simple changes that you could accomplish in a quick editing pass of your work.</p>
<p>Here's an excerpt of a good reflection:</p>
<p>&nbsp;</p>
<p style="padding-left: 40px;">Another good point was the factorial function in section 5.36 of the textbook. This was my final code:</p>

<pre style="padding-left: 40px;"><code>def factorial(num):</code><br /><code>&nbsp; &nbsp; total = 1</code><br /><code>  &nbsp; for i in range(1, num + 1):</code><br /><code>&nbsp; &nbsp; &nbsp; &nbsp; total = total * i</code><br /><code>&nbsp; &nbsp; return total</code></pre>

<p style="padding-left: 40px;">This was a good problem because it let me review how the range function worked. It can be inclusive or exclusive, but when the second parameter is added it becomes exclusive to it, and so I had to remember to add 1 to get the full range that the factorial calls for. This also is a good review of function creation, where the "fruitful" nature of this function called for me to create the variable total and then update it as the loop was iterating. This was a good review of functions and loops and enabled me to understand that even if common functions seem familiar, they may have caveats that need to be remembered.</p>
<p>&nbsp;</p>
<p>What's good about it?</p>
<p>No, seriously, read and think about the things this passage does well.</p>
<p><strong>Even with these strengths, there's room for improvement.</strong> How can this reflection be improved from good to great with a quick editing pass?</p>
<p>Here's an example revision, that might take 5-10 minues:</p>
<p>&nbsp;</p>
<p style="padding-left: 40px;"><span style="text-decoration: line-through;">Another good point was the</span> <span style="color: #236fa1;">The</span> factorial function that we had to write in 5.36 <span style="color: #236fa1;">was a opportunity to make use of my understanding of how functions work</span>. This was my final code:</p>

<pre style="padding-left: 40px;"><code>def factorial(num):</code><br /><code>&nbsp; &nbsp; total = 1</code><br /><code>  &nbsp; for i in range(1, num + 1):</code><br /><code>&nbsp; &nbsp; &nbsp; &nbsp; total = total * i</code><br /><code>&nbsp; &nbsp; return total</code></pre>

<p style="padding-left: 40px;">This was a good problem because it let me review how the <span style="text-decoration: line-through;">range</span> <code>range</code> function worked. It can be inclusive or exclusive, <span style="color: #236fa1;">which I ("knew from math class"/"learned from the textbook" means stopping before or after the boundary</span>. <span style="text-decoration: line-through;">but when</span> <span style="color: #236fa1;">When</span> the second parameter is added it becomes exclusive to it. <span style="color: #236fa1;">When I put <code>num</code> as the parameter the results weren't correct,</span>&nbsp;so I had to remember to <span style="text-decoration: line-through;">add 1</span> <span style="color: #236fa1;">use <code>num + 1</code></span> to get the full range that the <span style="color: #236fa1;">mathematical operation</span> <strong>factorial</strong> calls for<span style="color: #169179;"> (note: good job not writing <code>factorial</code> here. you're talking about the concept, not the function name)</span>. This also is a good review of function creation, where the "fruitful" nature of this function, called for me to create the variable <span style="text-decoration: line-through;">total</span>&nbsp;<span style="color: #236fa1;"><code>total</code></span>, <span style="text-decoration: line-through;">and then</span> update it as the loop was iterating<span style="color: #236fa1;">, and then pass <code>total</code> to the <code>return</code> statement</span>. This was a good review of functions and loops and enabled me to understand that even if common functions seem familiar, <span style="text-decoration: line-through;">they may have</span> <span style="color: #236fa1;">I need to remember their</span> caveats. <span style="text-decoration: line-through;">that need to be remembered.</span> <span style="color: #236fa1;">I'm trying out a problem solving strategy I'm calling <strong>going slow</strong>, which is my own combination of <strong>reading</strong> and <strong>ruminating</strong>,&nbsp;to help me do this, and it worked for me here.</span></p>
<p>&nbsp;</p>
<p>There was a great foundation to build upon here, and our revisions took this reflection from good to great. The formatting makes it clearer, and in a few places we added new specific in-line code mentions to help the reader understand where in the code we were talking about.</p>
<p>The <strong>biggest improvement </strong>is that we finished it up by relating what we just did to a <strong>larger problem solving strategy process</strong> that, while not in the <a class="inline_disabled" href="https://utexas.instructure.com/courses/1325008/pages/your-starting-problem-solving-toolkit" target="_blank" rel="noopener" data-api-endpoint="https://utexas.instructure.com/api/v1/courses/1325008/pages/your-starting-problem-solving-toolkit" data-api-returntype="Page">starting problem solving toolkit</a>, was related to two concepts that were. Speaking of concepts, we wrote several in <strong>bold,</strong> just like the class notes and textbook do, to call them out and in the case of factorial, distinguish it from the function of the same name.</p>
<p><strong>A quick revision pass can make your good reflection great</strong>. It doesn't 