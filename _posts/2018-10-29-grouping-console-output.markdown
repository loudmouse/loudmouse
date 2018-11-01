---
layout: single
title:  "Grouping Console Output"
date:   2018-10-29
categories: [programming]
tags: [javascript]
excerpt: "Learn how to group console output with .groupCollapsed();"
header:
  teaser: /images/jessica-lee-745621-unsplash.jpg
---

Here's another trick I learned while working through [Watch & Code][Watch & Code]. If you want to group text that you output to the console you can do it using `.groupCollapsed();` like this:

{% highlight javascript %}
  console.groupCollapsed('Click to See Grouped Items Below');
    console.log('Item 1');
    console.log('Item 2');
    console.log('Item 3');
  console.groupEnd();
{% endhighlight %}

#### Toggled Open After Clicking

![groupCollapsed](/images/groupCollapsed.png)


<!-- Links -->
[Watch & Code]: https://watchandcode.com/
