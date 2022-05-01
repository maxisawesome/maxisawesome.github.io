---
layout: post 
Title: Ways Machine Learning Shaped My World View 
---

### A List of Machine Learning Concepts That Have Influenced My Way of Thinking 
#### Embedding vectors:
Many concepts fit well into an embedding space analogy. Music genres, let's say, are loosely defined categories that bleed in and out of each other through tractable and intractable connections. Representing them in high dimensional space and capturing a lot of these properties bodes well in the theory that _something_ like that is happening in our heads. Simply the idea that my mind is has representations of experiences has been influential to how I understand my own feelings and brain

#### local minima
Local minima as a concept is a powerful and relatively simple idea (generally spotting those two traits together is an indication that its a useful paradigm). Much better explained with the picture below, the idea is you want to get to some global minimum, but while traveling there with small steps, you'll arrive at a minima that is the best in its area but not the best on the entire surface. When you're sitting at that local minimum, every direction from where you are is a step up, despite your goal of descent. In order to get to the global minimum, you need to somehow realize that taking those bad _looking_ steps is actually the correct thing to do, and then do it.  
![](/assets/posts/local_minimum.png)
What situations does this apply to? In ML it's used in loss functions - the model optimizes to get the loss to be the least possible, and in the high dimensional loss landscape it could reach local minima such that it seems like it's hit the least total amount of loss, but in reality there are better orientations the model could take that would have less loss. In my own life, it applies to this loss function idea - if I'm getting better at something and hit a plateau, a teacher might tell me to take steps that seem bad to me but are the route to the global minimum. It relates to feelings, where in order to feel better I might need to feel worse for a bit. How it feels to play piano when I'm a still a noob can be frustrating, but it'll feel way more fun once I'm better. Abandoning an old habit can feel bad at first though overall you'll feel better once it's gone. It's a useful analogy in the moment to comprehend immediate  

#### loss and reward
I just mentioned loss - its the measurement of failure that models minimize. In ML this is usually some easy to measure metric, like number of incorrect predictions. We dont have direct losses that can be measured as raw numbers but we take mistakes, things that didn't go quite well 

#### train/test set difference
You train your model, or you yourself train some skill, on some set of data. Then you go to use this learned behavior, either by applying the model in production or using the skill in a more official setting (a sports tournament, a project at work, or some act of public facing creation, like writing an album or a novel). Whatever information that was digested in training will produce our outcomes at "inference" time. If whatever occurs at test time is radically different than what we prepared with, then the pattern we learned from our training will not succeed in the expected manner. While this is easily digestable with data distributions and ML models, it is just as relevant to ourselves as agents achieving whatever goal (social skills, some sport, understanding a field of researhc, etc) as it is to models trained on practical datasets.
| ![train_test_set.png](/assets/posts/train_test_set.png) | 
|:--:| 
| *An illustration of an incorrectly learned distribution based on the difference between the data that was used to derive the function vs what it was applied to* |

#### skill and experience are synonymous
I was once watching Hikaru Nakamura, a top five supergrandmaster chess player, [stream](https://www.twitch.tv/gmhikaru) play blitz chess (each player gets 3 minutes for moves for the entire game). His opponent retreated his bishop and Nakamura recognized the position immediately, played three or four positionally forcing moves, and entombed the bishop behind his opponent's pawns. After the game he showed a classical match (120 minutes of time control per player) he had played _fourteen_ years before against a Mexican GM in which the same situation with the bishop happened. (I do not have )
This story displays three often confused concepts. Choosing the right moves was skillful, it was achieved through wisdom of knowing the path, which was originally found through intelligent thought. The skill is the raw output. Actions are taken and they achieve the end goal well or do not achieve the end goal well, and how well you achieve it is the skill. Wisdom is knowing the path from direct, past experience that 
These are not technical definitions I got from a textbook and applied to chess. They are how I've come to interpret the murky, existing definitions within my own life. "Intelligence" is famously ill-defined (the best attempt I've seen thus far needed only [sixty-four pages](https://arxiv.org/pdf/1911.01547.pdf)) and querying ML fields will give you a slew of answers. "Skill" and "wisdom" have similar issues.

#### Bonus: shape rotators vs wordcels

The impetus of shape rotators vs wordcels makes itself super clear when you're familiar with any of the stuff above. High dimensional representations are shapes. Manipulating these manifolds that define or divide these representations in your brain is shape rotation. Words are the abstract concepts constructed on top of the interplay of all these shape. Wordcels play on the levels of the abstractions and the fallout of these abstractions and dont come down and deal with the technical underbelly, creating the "shape rotators *vs* wordcels" dichotomy. Of course all people do both all the time, but the applicability as well as the ease with which it intuitively follows from all the linear algebra of ML is amusing.  
