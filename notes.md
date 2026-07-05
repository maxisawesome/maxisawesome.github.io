---
layout: default
title: Notes 
---

## Notes:

long posts

## Posts:

<!-- This list is generated automatically from files in _posts/.
     To add a post, drop a YYYY-MM-DD-title.md file in _posts/ — it shows up here.
     Work-in-progress lives in _drafts/ and won't appear until moved to _posts/. -->

{% for post in site.posts %}
[{{ post.title }}]({{ post.url | relative_url }}), {{ post.date | date: "%B %Y" }}

{% endfor %}

