---
layout: single
title:  "Ternary Operators"
date:   2018-10-25
categories: [programming]
tags: [javascript]
excerpt: "Read about using ternary operators for writing if else statements in shorthand."
header:
  teaser: /images/jens-lelie-15662-unsplash.jpg
---

A ternary operator is like shorthand for an if else statement. It looks sort of weird but once you understand what's going on it saves keystrokes.

 A normal if else statement in javascript looks like this:

{% highlight javascript %}
  var number = 5;
  if (number > 1) {
    'Number is greater than one.';
  } else {
    'Number is not greater than one.';
  }
{% endhighlight %}

The above code should return:

{% highlight javascript %}
  Number is greater than one.
{% endhighlight %}

Now, let's compare the above to a ternary operator:

{% highlight javascript %}
  var number = 5;
  number > 1 ? 'Number is greater than one.' : 'Number is not greater than one.'
{% endhighlight %}

The above code should also return:

{% highlight javascript %}
  Number is greater than one.
{% endhighlight %}

Let's break this down:

- The first part `number > 1` is the expression we want to evaluate
- The `?` acts as the if statement which checks against the preceding expression.
- The next part before the colon is what happens if the initial expression evaluates to true.
- The `:` acts as the else portion of the statement.
- The second part after the colon is what happens if the initial expression evaluates to false.

In english this ternary code says:

"If the value in the variable named number is greater than 5, then return 'Number is greater than one', otherwise return 'Number is not greater than one.'"

<!-- Source: [Watch & Code: Constructors, console.log at 0:23. output](https://watchandcode.com/courses/77710/lectures/1600693) -->
