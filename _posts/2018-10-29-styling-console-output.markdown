---
layout: single
title:  "Styling Console Output"
date:   2018-10-29
categories: [programming]
tags: [javascript]
excerpt: "Learn how to add basic CSS styling to console text using console.log() and a bit of special syntax."
header:
  teaser: /images/russn_fckr-66974-unsplash.jpg

---

Normally when you use console.log() to output content to the console it is pretty boring to look at.

{% highlight javascript %}
  console.log("Good morning!");
{% endhighlight %}

#### Default Console Output

![DefaultOutput Styled](/images/default-console-output.png)




If you want to style it up a bit you can use the `%c` syntax below and provide css styling which will be applied to your output.

{% highlight javascript %}
  console.log("%cGood morning!", "color:green; font-size: 1.5em; font-weight: bold; text-transform: uppercase;");
{% endhighlight %}

#### Styled Console Output

![Console Output Styled](/images/console-output-styled.png)
