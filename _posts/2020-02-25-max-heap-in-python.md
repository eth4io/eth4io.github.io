---
layout: post
title:  "Using Max Heap in Python with heaps"
date:   2020-02-25 22::00 +1100
categories: python
author: eth4io
---

------





I did an online code challenge for an interview last week. One of the questions can be solved easily with a priority queue. Therefore immediately I decided to use a max heap for the problem.



It wasn't hard to find a python standard library `heapq` can do the job.

The default function handles min heap which was not what I want. Not too long i found a solution recommending a hidden funciton `heapq._heapify_max(list)`  with popping function `heapq._heappop_max(maxheap)`. The underscore at the beginning of a function should be suspicious enough to alert me somewhat, but I didn't pay attention as I really just wanted to find a quick and simple solution so I can solve the challenge. Turned out it was a big mistake I made at that moment.



Turned out the max heap i built couldn't maintain as a max heap after each popping or pushing operation. I tried to `_heapify_max` it after each popping. But apparently that's not how a heap should work, it makes a heap insertion O(logn) became building a new heap which is O(nlogn). 



At the moment I realised the max heap implementation wasn't correct, I had spent more than 30 minutes on it out of 90 minutes of entire challenging time. I quickly realised the top answer of [this](https://stackoverflow.com/questions/2501457/what-do-i-use-for-a-max-heap-implementation-in-python) question suggests using min heap with negative value. What an counter-intuitive solution! But holy moley it saved me and I AC'ed my question with this trick. 



> The easiest way is to invert the value of the keys and use heapq. For example, turn 1000.0 into -1000.0 and 5.0 into -5.0.

> It's also the standard solution. 

It was both frustrating and intriguing knowing this was the correct way to do max heap.



## Use max heap in Python

```python
import heapq # standard python library for data structure: heap

a_list = [4, 3, 9, 13, 7]
heapq.heapify(a_list) # heapify a list into a min heap (not a max heap!)
heapq.heappop(a_list) 
heapq.heappush(a_list, 5)
heapq.heappush(a_list, -1)
print(a_list)
> [-1, 5, 4, 13, 7, 9]
```





## Lessons learned

Don't use builtin functions with underscore prefix. They are either experimental or obsolete and can be removed from the library without giving any notice to the community.



## References

* What do I use for a max-heap implementation in Python?, https://stackoverflow.com/questions/2501457/what-do-i-use-for-a-max-heap-implementation-in-python
*  heapq — Heap queue algorithm,https://docs.python.org/2/library/heapq.html