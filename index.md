---
layout: default
Title: Home
---
I'm Max. I'm a Machine Learning Engineer and Researcher, first working at [KUNGFU.AI](https://kungfu.ai) applying ML as an engineer, then [cohere.for.ai](https://cohere.for.ai/) doing research, and now at [MosaicML](https://www.mosaicml.com/). My work has covered computer vision, natural language processing, audio, and unsupervised learning. I recently published a pre-print on [data pruning](https://arxiv.org/abs/2309.04564) for natural language pretraining at scale. 

I enjoy backpacking where I can forget about the anthropocene, have spent a whopping \<REDACTED> hours playing Dota 2 (go zai, go rtz, go cr1t), lift, do a lil surfing, and do a lil climbing. In Austin I played ultimate frisbee on [Riverside](https://www.riversideultimate.org/), and loved hanging out in my backyard with [my cat, Callie](../cat). I grew up in Austin, went to school in Los Angeles, moved back home, and now live in San Francisco (hmu I just got here). 

poor attempts at professionalism [here](https://www.linkedin.com/in/max-marion/)

worst takes [here](https://twitter.com/maxisawesome538)

research only [here](https://twitter.com/maxdoesresearch)

code [here](https://github.com/maxisawesome)

my str8 up email (remove the hightech captcha): m m a r i o n 5 3 8 @ < r o b o t s  g o  a w a y > @ g m a i l 

Here's a list of the cooler projects I've worked on, during which my role always fell under "make the neural network work":

* a preprint exploring various methods of judging language data as low or high quality ([paper link](https://arxiv.org/abs/2309.04564))
* LLM eval for SOTA LLMs currently in production
* an algorithm to judge the price of collectibles like Pokemon cards, baseball cards, or rare coins
* a computer vision project identifying and pricing exterior damage on cars from cell phone photos
* a model for processing ambient rainforest noise to find gunshots, chainsaws, and vehicles indicating poaching and logging
* a system to scan insurance corpora to extract helpful sentences like "drug X is covered by plan Y under situation Z, but not situation A"
* a CTR (Click Through Rate) predictor for *crowd groaning noises* ads
* a FOD detector for runway radar scans (detects debris on your runway that'd destroy your fancy plane engines)
* A number of "information extractors" for large datastores of pdfs 
* the algorithm that judges SXSW speaker applications alongside human judges
* and more! that are less interesting and/or slightly secret


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