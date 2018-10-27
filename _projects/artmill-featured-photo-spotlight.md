---
title: "Artmill Photo Spotlight - Architecture"
layout: home
toc: true
excerpt: "Each week we chat with a new photographer and feature one of his or her photos."
header:
  image: /images/architecture.jpg
  teaser: /assets/images/foo-bar-identity-th.jpg
sidebar:
  - title: "Role"
    image: /images/artmill-logo.jpg
    image_alt: "Artmill.com"
    text: "Front End Developer"
gallery:
  - url: /assets/images/unsplash-gallery-image-1.jpg
    image_path: assets/images/unsplash-gallery-image-1-th.jpg
    alt: "placeholder image 1"
  - url: /assets/images/unsplash-gallery-image-2.jpg
    image_path: assets/images/unsplash-gallery-image-2-th.jpg
    alt: "placeholder image 2"
  - url: /assets/images/unsplash-gallery-image-3.jpg
    image_path: assets/images/unsplash-gallery-image-3-th.jpg
    alt: "placeholder image 3"
---

## Purpose

Each week we wanted to feature a photo on a theme from a different photographer. We'd then also share photos from other photographers on that same theme. This first week's feature was **architectural photography**.

For a live version, visit: [Artmill Featured Photo Spotlight](https://www.artmill.com/blog/photo-spotlight-architectural-photography/)

To view code for the prototype, visit: [the GitHub repo](https://github.com/loudmouse/photo_spotlight)

![Artmill Photo Spotlight Featured Photographer](/images/artmill-featured-photographer.png)


## Requirements

1. I needed to build a system that once in place could be easily updated each week by a non-technical member of our team.
2. The system would need to automatically display relevant info about the featured photographer such as his or her name, a profile photo, location, and social media links.
3. The system would also need to pull in a collection of similarly themed photos and display those on the page.

## My Solution

I built a template for our blog that could be copied and edited in a few places to generate fresh content each week. I chose to use the [Unsplash API](https://unsplash.com/documentation). Unsplash is a website that provides, in their own words, "Beautiful, free photos. Gifted by the world’s most generous community of photographers.".

I used javascript's fetch method to make calls to a couple of Unsplash's API endpoints to pull in the info I needed.

1. I called the `users` endpoint which allowed me to get a user's public profile.
  - With this call I was able to access the user's name, profile photo, location, and social media links.

2. I also called the `collections` endpoint which allowed me to retrive a single collection.
  - We had curated photos into a collection based on each week's photo theme. I could simply make a call to this endpoint, passing it the `:id` of our collection and I'd access the image in this manner.

I then used javascript to render HTML elements to the page with custom classes. I next used CSS and some Bootstrap to style the HTML that was rendered on page.

---

## Author

**Nolan Neeley** - [Nolan's GitHub](https://github.com/loudmouse)

---

## Screenshot

![Artmill Featured Photo Spotlight Layout](/images/artmill-featured-photo-spotlight-layout.png)
