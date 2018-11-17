---
layout: post
title:  "Using NASA api"
date:   2018-08-12
image: /assets/images/vintage.jpg
---

## Gathering data using NASA api

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
import chardet
{% endhighlight %}

step two,

get the data from url

{% highlight python %}
url = "https://api.nasa.gov/planetary/apod?api_key={}".format(api_key)
{% endhighlight %}

here api_key is the key that you’ve received after registering in NASA api base.

step three,
get the json data from the following function,
{% highlight python %}
def get_json_data(url):
    '''
    :input: url <class 'str'>
    :return: list of dictionaries
    '''
    request = requests.get(url)
    content = json.loads(request.content.decode(chardet.detect(request.content)["encoding"]))
    return content
{% endhighlight %}

give the url to `get_json_data()` function

{% highlight python %}
content = get_json_data(url)
{% endhighlight %}

download the image using `wget`

{% highlight python %}
os.system('wget {}'.format(content['hdurl']))
{% endhighlight %}
