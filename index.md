---
layout: default
Title: Home
---
I'm Max. My main claim to fame is doing machine learning in industry in Austin. I've been a goofball at [KUNGFU.AI](https://kungfu.ai) for most of the time it's existed. My work has touched domains like computer vision, natural language processing, audio, and unsupervised learning. Here's a list of the cooler stuff I've done, during which my role always fell under "make the neural network work":

* an algorithm to judge the price of collectibles like Pokemon cards, baseball cards, or rare coins
* a computer vision project identifying and pricing exterior damage on cars from cell phone photos
* a model for processing ambient rainforest noise to find gunshots, chainsaws, and vehicles indicating poaching and logging
* a system to scan insurance corpora to extract helpful sentences like "drug X is covered by plan Y under situation Z, but not situation A"
* a CTR (Click Through Rate) predictor for *crowd groaning noises* ads
* a FOD detector for runway radar scans (detects debris on your runway that'd destroy your fancy plane engines)
* A number of "information extractors" for large datastores of pdfs 
* the algorithm that judges SXSW speaker applications alongside human judges
* and more! that are less interesting and/or slightly secret

I play ultimate frisbee on [Riverside](https://www.riversideultimate.org/), enjoy backpacking where I can forget about the anthropocene, have spent a whopping \<REDACTED> hours playing Dota 2 (go EG), lift, and hang out in my backyard with [my cat](../cat). I grew up here in Austin, went to school in Los Angeles, then moved back home. 

poor attempts at professionalism [here](https://www.linkedin.com/in/max-marion/)

worst takes [here](https://twitter.com/maxisawesome538)

code [here](https://github.com/maxisawesome)

my str8 up email (remove the hightech captcha): m m a r i o n 5 3 8 @ < r o b o t s  g o  a w a y > @ g m a i l 

<!--  

The following code lets u page through posts. 
Not working - it doesnt seem to load the posts right.
dont know how to get the posts that use layout: posts to be listed to be found here

The writing above I borrowed from the "about" page and then delisted the about page 

<div class="posts">
  {% for post in paginator.posts %}
  <div class="post">
    <h1 class="post-title">
      <a href="{{ post.url }}">
        {{ post.title }}
      </a>
    </h1>

    <span class="post-date">{{ post.date | date_to_string }}</span>

    {{ post.content }}
  </div>
  {% endfor %}
</div>

<div class="pagination">
  {% if paginator.next_page %}
    <a class="pagination-item older" href="{{ site.baseurl }}page{{paginator.next_page}}">Older</a>
  {% else %}
    <span class="pagination-item older">Older</span>
  {% endif %}
  {% if paginator.previous_page %}
    {% if paginator.page == 2 %}
      <a class="pagination-item newer" href="{{ site.baseurl }}">Newer</a>
    {% else %}
      <a class="pagination-item newer" href="{{ site.baseurl }}page{{paginator.previous_page}}">Newer</a>
    {% endif %}
  {% else %}
    <span class="pagination-item newer">Newer</span>
  {% endif %}
</div> -->