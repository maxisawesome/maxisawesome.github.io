---
layout: default
title: Notes 
---

## Notes:

long posts
<!-- If I find myself thinking about something for long enough, I'll wrangle all the points in my head into text. There is a theoretic audience in mind, but like most burgeoning artists, the real audience thus far has been isolated to family and friends. Feel free to send me some feedback. -->

<!-- NOTE: I removed the link to this from the website bcus I never added too many pieces of writing and I decided the suck. Congrats u found a super secret easter egg!! Well done! lmk what u think of the writing i guess -->

## Posts:

<!-- This list is generated automatically from files in _posts/.
     To add a post, drop a YYYY-MM-DD-title.md file in _posts/ — it shows up here.
     Work-in-progress lives in _drafts/ and won't appear until moved to _posts/. -->

{% for post in site.posts %}
[{{ post.title }}]({{ post.url | relative_url }}), {{ post.date | date: "%B %Y" }}

{% endfor %}

