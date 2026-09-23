---
layout: default
title: Notes 
---

## long posts

<!-- This list is generated automatically from files in _posts/.
     To add a post, drop a YYYY-MM-DD-title.md file in _posts/ — it shows up here.
     Work-in-progress lives in _drafts/ and won't appear until moved to _posts/. -->

{% for post in site.posts %}
[{{ post.title }}]({{ post.url | relative_url }}), {{ post.date | date: "%B %Y" }}

{% endfor %}

## lists

<!-- Hand-maintained: pages that aren't dated posts. Add a line per page. -->

[toplists]({{ '/toplists' | relative_url }}) — lists of things I've done and things I like
