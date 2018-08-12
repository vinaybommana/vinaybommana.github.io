---
layout: post
title:  "Using NASA api"
date:   2018-08-12
image: /assets/images/2018-08-12.jpg
---
# Gathering data using NASA api
This blog post mainly focuses on using NASA’s apis (there are several of them)
and handling the data given by the api.

So let’s get our hands dirty,
Initially we need to get the api_key from nasa so that we can make more than a 1000 request per hour.

In order to do that, go to
[api_link](https://api.nasa.gov/index.html)

Now, let us use this api to get image of the day from nasa’s api
I’ll be using python for this

step one,

{% highlight python %}
import requests
import json
import os
{% endhighlight %}
