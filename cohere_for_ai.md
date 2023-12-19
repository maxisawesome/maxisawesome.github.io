---
layout: post
title: "Life Lessons from the Scholar's Program"
date:   2023-12-18 20:30:53 -0600
categories: Machine Learning, Research
---
summary: journalesque reflection on my time at cohere.for.ai, mostly written for future me

In October, I finished the [Cohere For AI Scholar's Program](https://txt.cohere.com/c4ai-scholars-program/) during which I published my first [paper](https://openreview.net/attachment?id=XUIYn3jo5T&name=pdf) (preprint version [here](https://arxiv.org/abs/2309.04564)). It was on data pruning - trying to measure and subsequently remove data from a language model's training set while maintaining or improving performance. 

It was pretty inarguably the most potent 8 months of my life in terms of progress, learning, and self-understanding. A lot of the lessons are quite tangible, might be useful for you, and will certainly be useful for me again (at least two of of these were on my [kungfu.ai review](../life_advice_from_kungfu/) in some version)

## How Science Works

### get started, start coding
I started off by digging through literature for about one week too long trying to find some magic metric that I could apply for a bingo on the first runs I tried. Obviously this metric did not exist already as the very smart people at the For AI lab had sent me on this journey to find the said metric in the first place. Regardless I pressed on looking for ideas til I was prompted (lightly scolded perhaps) to "Just start coding!"

This was very good advice. For starters, you will ideally be running experiments at some point and that infrastructure needs to exists. Furthermore you'll gain ideas from doing the experiments themselves. Trying stuff out is the scientific process


### start writing early
Writing for myself takes long enough. Writing that must go through 100 versions of edits takes even longer. Writing that must tell a story in order to defeat the reviewers with a group of people who all have slightly different opinions on the content takes even longest.

Indulge my tangent: I lived in a house in Austin with some high school friends after we all got settled in the city post college. It was on Placid Place, and I liked to refer to us as the Placid Princes in our Placid Palace. That part's not relevant to the overall post in the slightest but it's always been very fun and very goofy to me. s/o the homies. When I moved out of that house, I moved all my furniture out, and most of the major boxes. I felt great! All I had left was the stuff in some cupboards, closets, and on some various shelves. As anyone who's ever moved will know this is the point where I have naively not discovered that that's actually nowhere near close to done and there was still at least half if not more of the moving process left, at least in terms of time required. 

That's what writing your paper is like. You write your abstract. You make your figures, maybe a table. You write a good sectioning of the Experimentation and Results section and you're at the page limit. Oh no you're at the page limit but you still need to write the related works which requires all those papers you read before did I write them all down and shit the last author has opinions on the introduction they're honestly good points and jesus the graphs should be updated to be clearer and 

you get the point

### communication IS science
Speaking of graphs, the reader should look at your charts in your paper and immediately understand whatever you're trying to tell them. They should not have to try at all. You discovered or proved something - now you need to tell them. 

I chatted with [Nick Frosst](https://www.nickfrosst.com/), famous rockstar, about research, specifically about my lull at the beginning reading papers, and he said this: he doesn't really "read" papers anymore. He reads the abstract. If there's more to learn, he'll look through the figures. If there's still more to learn, skim through the experiments. If you're still interested, which at this point is a very deep dive and a very low percentage of papers, go to the appendix and look through those graphs. Nick doesn't need to read research papers like I do, so I'm not gonna prune papers this aggressively, but all this started with the idea that the graphs should communicate a vast majority of information in the paper.

### always be working towards a hypothesis, always be working towards a paper
You should be running experiments _for a reason_. Towards proving or disproving _an idea_. Otherwise you're just poking in the dark and you can do a lot better than [O(√n)](https://en.wikipedia.org/wiki/Random_walk#:~:text=This%20hints%20that,.). Chose a hypothesis and a way to test it.

<!-- In my paper, we retain the bottom, middle or top subset of our dataset based on the distribution of our pruning metrics. My first experiments had different cuts of the data, but they were just some effectively ideas on how to cut up the data. Top/Mid/Bottom was in pursuit of the idea that top is good, bottom is bad, and furthermore what the results  -->

### change one thing at a time
Do not introduce confounding changes. Do not do it. Resist the urge to jump thru five ideas in a single experiment ohoho this'll save me so much time - no it will not you shmuck. If you change more than one thing will have no idea which of those things affected the results. Maybe the result is so because of some combo of them man you'll have no idea. Do not change more than one thing at a time.

### establish a baseline
you gotta measure against something. establish a baseline, or at the very least what the baseline will be, early on. Otherwise you will again have no idea what's happening. Just like when you changed more than one thing at once, which you will not be doing.

### reduce cycle time (esp early experiments)
if you can't iterate quickly and get results its gonna take a lifetime to get anywhere. Most deadlines come before that, so instead start small. Try your idea on a smaller model that takes, oh let's say 2.3 hours to train instead of 29 hours first and go from there. Obviously this is not always possible if you're studying something like scale, but it's a good idea nonetheless. This also applies to coding - if you script takes 6 minutes to run before you hit the bug, and then you run it to find your debugging code has a typo, you gotta wait another 6 minutes before you find anything out. That sucks. Figure out a way to make that loop way quicker.

### wtf is going on
Engineering is very nice because usually it goes something like this:
"hey I wish X existed but I noticed it does not. I will not go make X. I see that it requires a, b, and c. I think I will make a then b then c"
and then you go do that.

Research is more like this:
"hey wtf is going on with X? looks like it could be a, b, c, or d. i guess we'll ablate them all out, then measure the results. I will look at the data and interpret the results. we are now in any one of several situations: we found the cause and it was one of those variables, we found the cause and it was some bug in the code and this whole thing has been a wild goose chase, we cannot tell if any of a, b, c, or d are the cause, or at least it didn't seem like it from our experiments and we need to weigh continuing to investigate and spending more time on it with just giving up and not knowing, it was some combo of a, b, c, and d, or there was a bug in our experiments and we need to do it all again"

The path is a lot less clear in research and you'll have to be comfortable with that. I was not very comfortable with it at all. It stressed me out quite a bit, but understanding it's part of the gig helped me out. 

### remote work is bad 
at least it is for me. Too easy to get distracted, too easy to slip into "I'll do it later" and later is 8:30 pm. Too removed from my coworkers and too huddled in a den. happy if it works for you or parents or 

In some defense of wfh, it gave me three lovely years of days with [Callie](../cat) at the end of her life. I'm very very thankful for that.

<!-- ### you do not need to have all the ideas -->

### don’t be so hard on yourself
I've been told this for years. Fight the feeling that people giving you this advice are missing part of the context, are too easy, or don't have what it takes. You can try really hard and have it not hurt so much. This was the most important lesson I learned cohere.

