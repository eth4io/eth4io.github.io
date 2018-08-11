---
layout: post
title:  "Hello World Post"
date:   2018-08-11 20:11:00 +1000
categories: common
---
Some random words with a code snippet.

{% highlight python %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

`some code`

```
a code block
```

```R
  # calculation for indicator 11
  sp@data$pvCount <- sp@data$aud7800_15599 + sp@data$aud15600_20799 + sp@data$aud20800_25999 + sp@data$aud26000_33799
  sp@data$pvRatio <- sp@data$pvCount / sp@data$totaldwelling
  
  # trunc data
  sp_0 = subset(sp, select=c(id, gid, sa2_main16, sa2_name16, totaldwelling, pvCount, pvRatio))
  names(sp_0)[5] <- "dwCount"
```
