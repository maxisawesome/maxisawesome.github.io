---
layout: default
Title: Home
---
## Howdy
This is the brief personal website of Max Marion. I'm a Machine Learning Researcher, most recently at [MosaicML / Databricks](https://www.databricks.com/research/mosaic). Before that I was a Research Scholar at [cohere labs](https://cohere.com/research), and earlier an MLE at [KUNGFU.AI](https://kungfu.ai). I published a paper on [data pruning](https://openreview.net/pdf?id=XUIYn3jo5T) (the longer pre-print [here](https://arxiv.org/abs/2309.04564)) for LLM pretraining. My work has covered LLM evaluations and faithfulness, computer vision, audio, and more.

My motion based hobbies include backpacking where I can forget about the anthropocene, surfing, lifting, and playing ultimate frisbee. My more stationary hobbies include puzzle games and rougelikes, reading, and piano. In Austin I played frisbee on [Riverside](https://www.riversideultimate.org/) and loved hanging out in my backyard with [my cat, Callie](../cat). I grew up in Austin, went to school in [Los Angeles](https://www.oxy.edu/), moved back home, and now as of October 2023 live in San Francisco. 

my poor attempts at professionalism are [here](https://www.linkedin.com/in/max-marion/)

my worst takes are [here](https://twitter.com/maxisawesome538)

research only is [here](https://twitter.com/maxdoesresearch)

my code is [here](https://github.com/maxisawesome)

my str8 up email (remove the hightech captcha): m m a r i o n 5 3 8 @ < r o b o t s  g o  a w a y > @ g m a i l 

I was recently briefly featured in [this Scientific American](https://www.scientificamerican.com/article/the-god-chatbots-changing-religious-inquiry/) article on LLMs and their possibilities for religious applications and [this Wall Street Journal](https://www.wsj.com/sports/olympics/noah-lyles-olympics-100m-ecab1749?st=i9sza7f1tc1b5us&reflink=desktopwebshare_permalink) article on Noah Lyles and the "rise of nerds."

Here's a list of the cooler projects I've worked on, during which my role always fell under "make the neural network work":

* Evals for SOTA LLMs 
* Hallucination detection and correction 
* Efficacy of LLMAsAJudge
* My paper exploring various methods of judging language data as low or high quality ([paper link](https://arxiv.org/abs/2309.04564))
* An algorithm to judge the price of collectibles like Pokemon cards, baseball cards, or rare coins
* A computer vision project identifying and pricing exterior damage on cars from cell phone photos
* A model for processing ambient rainforest noise to find gunshots, chainsaws, and vehicles indicating poaching and logging
* A system to scan insurance corpora to extract helpful sentences like "drug X is covered by plan Y under situation Z, but not situation A"
* A CTR (Click Through Rate) predictor for *crowd groaning noises* ads
* A FOD detector for runway radar scans (detects debris on your runway that'd destroy your fancy plane engines)
* A number of "information extractors" for large datastores of pdfs 
* The algorithm that judges SXSW speaker applications alongside human judges
* and more! that are either less interesting or I'm not allowed to tell you about


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