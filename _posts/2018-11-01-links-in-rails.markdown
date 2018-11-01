---
layout: single
title:  "Using the link_to Helper in Rails"
date:   2018-11-01
categories: [programming]
tags: [rails]
excerpt: "A quick note on using the link_to helper in Rails to create an anchor element."
header:
  teaser: /images/jj-ying-215308-unsplash.jpg
---

This is nothing groundbreaking but I kept forgetting. I'm writing it down in hopes of better retaining in the future. Enjoy.

If we want to create an anchor element with HTML and apply a CSS class we would do something like this:

{% highlight ruby %}
  <a class="navbar-brand" href="index.html">DailyPrompt</a>
{% endhighlight %}

This will create an anchor element which will link to `index.html` and apply the `navbar-brand` Bootstrap CSS class.

To do the same thing in Rails we'd write it like this:

{% highlight ruby %}
  <%= link_to 'DailyPrompt', root_path, class: 'navbar-brand' %>
{% endhighlight %}

Here we write an opening ERB tag and then use the `link_to` helper method. We pass this method:

- the text we want to display
- the url in the form of a url_helper which we can check by calling `rails routes` in terminal
- the class to be assigned to this anchor element

For a deeper dive check out the [rails docs on link_to][rails docs on link_to].




<!--  Links -->

[rails docs on link_to]: https://api.rubyonrails.org/v5.2.1/classes/ActionView/Helpers/UrlHelper.html#method-i-link_to
