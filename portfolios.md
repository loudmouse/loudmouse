---
layout: default
title: Portfolio
---


{% for portfolio in site.portfolios %}
  <h2>{{ portfolio.title }}</h2>
  <p>{{ portfolio.excerpt }}</p>
{% endfor %}
