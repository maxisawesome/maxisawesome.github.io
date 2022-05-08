---
layout: post
Title: 2019 Neurips
---
<!-- ## The 5 Best Things I Saw at NeurIPS 2019 -->
This post originally appeared on my company's blog [here.](https://www.kungfu.ai/blog-post/the-5-best-things-we-saw-at-neurips-2019)
I've copied it here, just in case it ever evaporates from that part of the internet.


Last month I had the pleasure of attending NeurIPS, the largest machine learning research conference in the world, which took place in Vancouver, BC. Before you think too highly of me, I did not have a paper accepted. I just put my name in for a normal attendance ticket and was lucky enough to get selected. This was not my first rodeo as I got to attend last year as a student volunteer, but I was very grateful for the opportunity and wanted to share some of the research I saw while there.

The conference ecosystem is the heart of the Machine Learning (ML) field and part of what makes it unique. There are no primary journals, so acceptance to these conferences is where peer review validates the science researchers have done. One of the prominent advantages of not relying on journals is that research doesn’t sit behind a paywall, so anyone anywhere can access it. This is often cited as one of the best aspects of our field. Anyone with the willpower to study the field has access to state of the art research. It’s also cited as being one of the reasons the field has grown so fast. Open access to research means more researchers which means more science getting done. Unfortunately, suspicions have begun to arise that relying heavily on conferences to verify research is not a solution that’s scaling with the massive influx of interest that’s come with deep learning’s successes …

The popularity of the conference was the talk of the conference, and the drawbacks were more than just a crowded convention center. Poster sessions reached maximum capacity and had to bar additional attendees from entering. People took notice, and there was a sense that if nothing about the system changes, the infrastructure would buckle under the weight of the number of people (ironically, reminds me a lot of Austin).

Without further ado, here are the five best takeaways from NeurIPS 2019:

**‍Graph Neural Networks:** GNNs are neural networks over [mathematical graphs](https://en.wikipedia.org/wiki/Graph_theory), and they had a strong showing at this year’s NeurIPS. Successfully applying GNNs is exciting because it opens neural networks to new tasks that can leverage graphs. The most interesting one to me was Machine Learning for Scent. It treats molecules as graphs and makes predictions on how people describe their smell based only on the molecular makeup. [How neat is that?](https://www.youtube.com/watch?v=Hm3JodBR-vs)

- [Provably Powerful Graph Networks](https://arxiv.org/abs/1905.11136): Haggai Maron, Heli Ben-Hamu, Hadar Serviansky, Yaron Lipman
- [GNNExplainer: Generating Explanations for Graph Neural Networks](https://arxiv.org/abs/1903.03894): Rex Ying, Dylan Bourgeois, Jiaxuan You, Marinka Zitnik, Jure Leskovec
- [Machine Learning for Scent: Learning Generalizable Perceptual Representations of Small Molecules](https://arxiv.org/abs/1910.10685): Benjamin Sanchez-Lengeling, Jennifer N. Wei, Brian K. Lee, Richard C. Gerkin, Alán Aspuru-Guzik, Alexander B. Wiltschko

**BERT:** Transformers are a large, feed-forward only neural network architecture designed to tackle sequence data with attention. They delivered huge improvements on many sequence based tasks, most notably being significantly more [impressive language models](https://openai.com/blog/better-language-models/). The Transformer’s continued success ([and continued development](https://ai.googleblog.com/2020/01/reformer-efficient-transformer.html)) implies that the architecture isn’t going anywhere soon, and that feed-forward only networks could be able to tackle a wider variety of problems if the network is constructed in a way to accommodate it.

- [Visualizing and Measuring the Geometry of BERT](https://arxiv.org/abs/1906.02715): Andy Coenen, Emily Reif, Ann Yuan, Been Kim, Adam Pearce, Fernanda Viégas, Martin Wattenberg
- [BERTgrid: Contextualized Embedding for 2D Document Representation and Understanding](https://openreview.net/forum?id=H1gsGaq9US): Timo I. Denk, Christian Reisswig
- [Enhancing the Locality and Breaking the Memory Bottleneck of Transformer on Time Series Forecasting](https://arxiv.org/abs/1907.00235): Shiyang Li, Xiaoyong Jin, Yao Xuan, Xiyou Zhou, Wenhu Chen, Yu-Xiang Wang, Xifeng Yan

**GANs:** GANs maintained the popularity they’ve enjoyed since their discovery (or rediscovery, [depending on who you ask](https://www.reddit.com/r/MachineLearning/comments/djju8a/d_jurgen_schmidhuber_really_had_gans_in_1990/)). There were a number of attempts to apply GANs to domains that hadn’t been previously explored, as well as general improvement of the overall understanding of GANs. GANs are as useful as you are creative. They’ve been used on a variety of tasks that aren’t just “make more faces based on these faces”. That includes denoising data, generating data based only on metadata, super resolution on low quality images, and even automatic photoshop like properties with [Cycle-GANS](https://junyanz.github.io/CycleGAN/).  

- [Modeling Tabular data using Conditional GAN](https://arxiv.org/abs/1907.00503): Lei Xu, Maria Skoularidou, Alfredo Cuesta-Infante, Kalyan Veeramachaneni
- [Classification Accuracy Score for Conditional Generative Models](https://arxiv.org/abs/1905.10887): Suman Ravuri, Oriol Vinyals
- [TAC-GAN - Text Conditioned Auxiliary Classifier Generative Adversarial Network](https://arxiv.org/abs/1703.06412): Ayushman Dash, John Cristian Borges Gamboa, Sheraz Ahmed, Marcus Liwicki, Muhammad Zeshan Afzal

**Deep Learning Theory:** Deep Learning works super well even with a number of unexplained phenomena. The dynamics of the inner workings of neural networks architectures are still not well understood. Despite being hugely overparameterized, they don’t overfit and generalize quite well. Things like how many layers will generalize best, how deep is too deep, what activation functions are best, etc are often just guess work validated by empirical results. Deep Learning theory aims to investigate these mysteries to better understand neural networks and what exactly is going on inside them. With a more solid understanding of why and how deep neural nets do what they do, hopefully we can push AI even further than it’s already come.

- [Deep ReLU Networks Have Surprisingly Few Activation Patterns](https://arxiv.org/abs/1906.00904): Boris Hanin, David Rolnick
- [Control Batch Size and Learning Rate to Generalize Well](https://papers.nips.cc/paper/8398-control-batch-size-and-learning-rate-to-generalize-well-theoretical-and-empirical-evidence.pdf): Theoretical and Empirical Evidence: Fengxiang He, Tongliang Liu, Dacheng Tao
- [Neural Network Surgery with Sets](https://arxiv.org/abs/1912.06719): Jonathan Raiman, Susan Zhang, Christy Dennison


**Fun bonus content:** A curling robot… that’s right, all you all-star curlers got your days numbered. The machines are unbiased in whose jobs they take. But seriously, this is awesome. Is it useful? Unimportant. It’s cool as $#!@. Check out the video [here](https://www.youtube.com/watch?v=yXygf8oz58k&feature=youtu.be) and the paper [here](https://www.ijcai.org/Proceedings/2018/0870.pdf). 
