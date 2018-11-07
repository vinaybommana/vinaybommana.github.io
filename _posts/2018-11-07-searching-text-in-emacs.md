---
layout: post
title:  "Searching Text in Emacs"
date:   2018-11-07
image: /assets/images/2018-11-07.jpg
---

## Using good old grep

press meta + x grep #Enter#

{% highlight bash%}
grep --color -nH --null -e "the Text you have to search for" *filetype
{% endhighlight %}
