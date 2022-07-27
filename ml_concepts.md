---
layout: post 
Title: Ways Machine Learning Shaped My World View 
---

<!-- #### Embedding vectors:
Many concepts fit well into an embedding space analogy. Music genres, let's say, are loosely defined categories that bleed in and out of each other through tractable and intractable connections. Representing them in high dimensional space and capturing a lot of these properties bodes well in the theory that _something_ like that is happening in our heads. Simply the idea that my mind is has representations of experiences has been influential to how I understand my own feelings and brain -->

<!-- Other ideas:
    layers = layers in my brain when I see visions of relations
    embeddings like above ^^^
 -->
#### Loss, Reward, and Psychedelics
Loss is a measurement of failure that a model minimizes, usually some metric that's directly linked to error rate. Less loss means your model is doing better. Conversely, reward is the opposite. Some agent is interacting with an environment (this paradigm is the reinforcement learning framework), and it learns it's policy for operating in that environment by maximizing that reward. Model is trying to predict 
<!-- u can edit ur own reward/loss functions. feelings = signal-->

#### local minima
The idea is you want to get to some global minimum, but while traveling there in small steps, you'll arrive at a minima that is the best in its area but not the best on the entire surface. When you're sitting at that local minimum, every direction from where you are is a step up, despite your goal of descent, so it appears that you're at the best spot. In order to get to the global minimum, you need to somehow realize that taking those apparently bad steps are actually the correct thing to do.  
![](/assets/posts/local_minimum.png)
In ML this is occurs on the loss landscpae - the model optimizes to get the loss to be as low as possible, and in the high dimensional loss landscape it could reach local minima such that it seems like it's hit the least total amount of loss, but in reality there are better orientations the model could take that would have less loss. In my own life, it applies to this loss function idea - if I'm getting better at something and hit a plateau, a teacher might tell me to take steps that seem bad to me but are the route to the global minimum. It relates to feelings, where in order to feel better I might need to feel worse for a bit. How it feels to play piano when I'm a still a noob can be frustrating, but it'll feel way more fun once I'm better. Abandoning an old habit can feel bad at first though overall you'll feel better once it's gone. It's a useful analogy in the moment to comprehend immediate  


#### train/test set difference
You train your model, or you train some skill, on some set of data. Then you go to use this learned behavior, either by applying the model in production or using the skill in a more official setting (a sports tournament, a project at work, or some act of public facing creation, like writing an album or a novel). Whatever information that was digested in training will produce your outcomes at "inference" time. If whatever occurs at test time is radically different than what we prepared with, then the pattern we learned from our training will not succeed. This is just as relevant to ourselves as agents achieving whatever goal (social skills, some sport, understanding a field of research, etc) as it is to models trained on practical datasets.
Restated with examples: you train a model on 100 pictures of cats and 100 pictures of Dalmations (with the label of 'dog'). The validation set is 10 cats and 10 dalmations, and you get good results on it. The test set has pictures of golden retrievers, but your model doesn't recognize them as dogs because they are outside of the distribution of data your model used to determine the definition of 'dog.'

You train  

![train_test_set.png](/assets/posts/train_test_set.png)
*An illustration of an incorrectly learned distribution based on the difference between the data that was used to derive the function vs what it was applied to. The training examples are the blue dots, the test examples are the x's.*

#### Skill vs Wisdom vs Intelligence 
I was once watching Hikaru Nakamura, a top five supergrandmaster chess player, [stream](https://www.twitch.tv/gmhikaru) some blitz chess (each player gets 3 minutes for the entire game). His opponent retreated his bishop and Nakamura recognized the position, played three or four positionally forcing moves, and entombed the bishop behind his opponent's pawns. After the game he showed a classical match (120 minutes of time control per player) he had played _fourteen_ years before against a Mexican GM in which the same situation with the bishop happened. (I do not have a timestamp to the moment on stream, sorry!)

This story neatly demonstrates some hard to define words. Choosing the right moves was skill, it was achieved through wisdom of knowing the path, which was originally found through intelligent thought. The skill is the raw output. Actions are taken and they achieve the end goal or do not achieve the end goal, and how well you achieve that goal is "skill." Wisdom is applying previous knowledge to the current situation. Hikaru had seen that board position before and it was wise to apply what he knew about it. Intelligence is your ability to process a new situation. Way back when, assuming he hit that position in the game and then figured out what the best move was over the board, our streamer used his intellect to intake the board position and derive a skillful response. 

These are not technical definitions, they are how I've come to interpret the murky, existing definitions that float about the internet. "Intelligence" is famously ill-defined (the best attempt I've seen thus far needed only [sixty-four pages](https://arxiv.org/pdf/1911.01547.pdf)) and querying ML fields will give you a slew of answers. 

#### Bonus: shape rotators vs wordcels

The impetus of shape rotators vs wordcels makes itself super clear when you're familiar with any of the stuff above. High dimensional representations are shapes. Manipulating these manifolds that define or divide these representations in your brain is shape rotation. Words are the abstract concepts constructed on top of the interplay of all these shape. Wordcels play on the levels of the abstractions and the fallout of these abstractions and dont come down and deal with the technical underbelly, creating the "shape rotators *vs* wordcels" dichotomy. Of course all people do both all the time, but the applicability as well as the ease with which it intuitively follows from all the linear algebra of ML is amusing.  
