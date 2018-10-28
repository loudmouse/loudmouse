---
layout: single
title:  "setTimeout"
date:   2018-10-24
categories: [programming]
tags: [javascript]
excerpt: "Read how I used setTimeout() to solve an issue I was facing while working with the Flickr API."
---

![alt text][setTimeout]

## My Problem

I was recently playing with the [Flickr API][Flickr API] and ran into an issue that had me in a standstill. While I was able to successfully call the API endpoint, I was unable to render it on my screen. I was frustrated because I'd worked through some previous roadblocks only to get to this point, but again I was stuck. The ah-ha moment came to me while reviewing some content in Gordon Zhu's course [Watch & Code][Watch & Code]. Gordon was explaining the event loop and I realized this may be relevant to my roadblock.


## The Order of Things (the event loop)

The event loop is like the order of things. It determines what thing happens first, second, third, and so on. In Gordon's example, the basic flow would be like this:

1. the Javascript will run
2. the DOM is updated
3. any extra tasks, such as callbacks passed to a function, will be called

So after seeing this I considered perhaps my issue could be found in this order of things, the event loop.

## Uncovering the Issue

In the video, Gordon uses an example where he suggests wrapping the code in an if else statement. In doing so, we could identify if the issue is related to the event loop.


## The If Statement

In the if statement we'll that two things are true:

1. does the document on the window object exist?
2. does the body on the window object exist?

If both of these statements are correct, then we'll execute the code. This code looks like this:

{% highlight javascript %}
if (window.document && document.body) {
  //code to execute goes here
}
{% endhighlight %}


## The Else Statement

We then want to fire some other code if the if statement evaluates to false. This is where the else statement comes in to play. Within the else statement we can `console.log` a simple statement to let us know that the DOM is not yet ready for us. This code looks likes this:

{% highlight javascript %}
if (window.document && document.body) {
  //code to execute goes here
} else {
      console.log('The DOM is not yet ready!');
  }
{% endhighlight %}

## Trying it Out

I used the above if else statement with my own code. I put my javascript inside the if statements block to execute if the if statement evaluated to true and then I gave the `console.log` statement to the else block to run in case the if statement evaluated to false. And what happened?

{% highlight javascript %}
The DOM is not yet ready!

{% endhighlight %}



## Wrapping it in setTimeout

From the above we see that the DOM is not ready. We need a way to delay the running of my code until the DOM is ready. This is where the `setTimeout` function comes in. Let's look at the event loop flow one more time:

1. the Javascript will run
2. the DOM is updated
3. any extra tasks, such as callbacks passed to a function, will be called

We need to #2 happen before our code runs. From #3 above we see that any extra tasks such as callbacks passed to functions will occur only after the DOM is updated. Let's wrap everything in `setTimeout`. Because extra tasks such as callbacks passed to a function are held until after the DOM is updated, this should resolve our issue. You'll note the `setTimeout` accepts and optional `delay` parameter which is measured in milliseconds. This tells the function to wait `X` many milliseconds before it should run the code. In our situation we are setting this to 0 because all we really need is for the code to wait until the DOM is updated. You can read more on this at [the MDN docs on `setTimout`][MDN Docs for setTimeout]

The code looks like this:

{% highlight javascript %}
setTimeout(function() {
  if (window.document && document.body) {
    //code to execute goes here
  } else {
        console.log('The DOM is not yet ready!');
    }
},0);
{% endhighlight %}

The javascript will load, then the DOM will load/update, and then finally our code that's wrapped in the `setTimeout` method will finally fire.



Do you have any thoughts on setTimeout? Tweet me at [@loudmouse312][@loudmouse312].


---


<!-- Images -->
[setTimeout]: /images/icons8-team-643498-unsplash.jpg "Photo by Icons8 team on Unsplash"

<!-- Links -->
[Flickr API]: https://www.flickr.com/services/api/
[Watch & Code]: https://watchandcode.com/
[MDN Docs for setTimeout]: https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout
[@loudmouse312]: https://twitter.com/loudmouse312
