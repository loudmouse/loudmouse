---
layout: single
toc: true
title:  "Using the Unsplash API"
categories: [programming]
tags: [javascript, api]
excerpt: "Read about using Javascript to make calls to an API."
header:
  teaser:
---

- get element in the DOM to insert the data you call from the API
- save your api endpoint to a variable
- create helper method to create a new html element
- create helper method to append an html element to a parent element
- call the fetch method and pass it the variable that stores the api endpoint
- then take that response and convert it to JSON
- then we call a function and pass the data object
- we set the data object to a variable called photos
- access data off the photos object and save them to their own variables ie. name, twitter, location, etc.
- then using the helper method create some html elements and assign them to their own variables
- next add a class name to each of the html elements we created previously.
- now we assign data to the html elements we'd created previously
- lastly, we append the elements to other elements and then the parent that will render everything to the DOM
- as a bonus we created logic to check if a value exists. If it doesn't thne we modify the css of the html element so it is hidden.
