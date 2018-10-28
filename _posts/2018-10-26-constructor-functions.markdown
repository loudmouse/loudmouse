---
layout: single
title:  "Constructor Functions"
date:   2018-10-26
categories: [programming]
tags: [javascript]
excerpt: "Read about javascript constructor functions, create a guitar factory, and then build a guitar for Willie Nelson."

---

Constructor functions let us create objects using a sort of template. The object can share things in common but also have their own unique attributes.

Let's write a function to help us create guitar objects. We'll use a constructor function to do this. Let's first figure out what attributes are common to all guitars. We'll keep this pretty basic and may not be 100% true to life but works for this example.

Standard attributes of all guitars:

- has 6 strings
- standard tuning is EADGBE

Now let's consider some things that may be unique from guitar to guitar.

Custom attributes of each individual guitar:

- an owner
- a nickname
- a make
- a model
- a year
- a guitar type (acoustic, electric, etc.)
- a fretboard material (maple, ebony, etc.)

Great, so we've got some ideas to start with. The below code is a template, a *guitar factory*, a **constructor function** to help us create guitars easily.

We name the function and write it to accept seven arguments. Each of these arguments represents one of the custom attributes we'd come up with above.

Inside the function we see that the standard attributes are assigned to their own variables on the Guitar object. We've written the function so these values are auto-assigned when you create the new guitar because we decided they were common across all guitars.

The next set are our custom attributes. These are assigned to variables on the object based on the arguments we pass into the function when we create the guitar object.

This is what the Guitar constructor function looks like:

{% highlight javascript %}
  function Guitar(owner, nickname, make, model, year, type, fretboard) {
    // these are standard attributes
      this.stringCount = 6;
      this.standardTuning = 'EADGBE';
    // these are custom attributes
      this.owner = owner;
      this.nickname = nickname;
      this.make = make;
      this.model = model;
      this.year = year;
      this.type = type;
      this.fretboard = fretboard;
  }
{% endhighlight %}

Next, let's create a guitar for Willie Nelson.

- We create a variable `var willie` so we can access the guitar object after it's been created.
- We assign this variable `=` to the new guitar we are creating.
- We call a constructor function using the `new` keyword and the function name, `Guitar`.
- Then we pass in the arguments which represent the guitar's custom attributes ie. `'Willie Nelson', 'Trigger', 'Martin', 'N-20', 1969, 'acoustic', 'maple'` for `owner, nickname, make, model, year, type, fretboard`.

Using our constructor function, this is what creating a new guitar looks like:

{% highlight javascript %}
  var willie = new Guitar('Willie Nelson', 'Trigger', 'Martin', 'N-20', 1969, 'acoustic', 'maple');
{% endhighlight %}

This will return a guitar object saved to the variable `willie`. We can now access the attributes of this guitar we've created by calling the variable name plus the attribute name. If we want to get the nickname of Willie's guitar we simply type:

{% highlight javascript %}
  willie.nickname
{% endhighlight %}

This will return: `"Trigger"`

If we want to get the make of the guitar we can do this:

{% highlight javascript %}
  willie.make
{% endhighlight %}

This will return: `"Martin"`





This is just the tip of the iceberg. You can learn more by exploring the [Function Constructor Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function).


<!-- Source: [Watch & Code: Constructors, console.log at 4:18. output](https://watchandcode.com/courses/77710/lectures/1600693) -->
