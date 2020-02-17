---
layout: post
title:      "Narrow the *Right* Scope"
date:       2020-02-17 03:19:05 +0000
permalink:  narrow_the_right_scope
---


This time around I felt a lot more confident about putting together my data plans. I spent some time finding just the right *tool* to make a plan look the way I wanted, read up on how all the lines n' dots work (silly, I know, but always good to refresh), and talked over some of the fuzzier points with my Cohort Lead. 

In reality, I ended up building *way* less than I initially dreamt, but not because I failed. In fact I'm feeling pretty good about where I landed! It seems clear that the difference between what I *planned* and what I *built* is good ole' fashioned naivete. 

The TL;DR is that when I thought up my app plans, I came at it from the perspective of a User. What was the maximally useful tool, and what are all the things I wanted it to do. And I was even reasonable about it! I kept the scope relatively narrow. But again, narrow from a *User* perspective.

What I *needed* to have done was kept it narrowly scoped from a *Developer* perspective. My User-based plans were more like "this is just a simple checkbox, and it would add so much, so of course I should do it," when instead they needed to be more like "this checkbox would need to live in a different table, with an entirely different Model and Controller, and possibly an additional Join table to connect it to this *other* thing... so no, this isn't simple at all, and probably doesn't belong in the MVP."

That's a bit of an oversimplification, but it's the essence of the problem. 

It's still surely correct to think of product design from the User perspective, and then figure out how to build it. In general. But in this very specific school-based-scope, with a very specific Project Requirements Spec, and a very limited period of time, figuring out what does and doesn't belong in the project is an entirely different skill. It's about what's practical in the time allotted, and with *the tools already mastered*.

That last bit is a reference to JavaScript, but of course. While building my Rails app there were *so* many cases where I spent way too much time building something I confidently knew would be easier and more appropriate for JavaScript. It's still important and useful to have done the work and mastered the tools, but I'm looking forward to the next module, and to having a more complete toolset. 
