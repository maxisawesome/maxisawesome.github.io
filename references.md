---
title: References
layout: post
---

Amalgamation of code, commands, formulas, or tidbits I find myself repeatedly googling the syntax of 

## Python

Dict <--> Json

```
import json

with open('data.json', 'w') as fp:
    json.dump(data, fp, sort_keys=True, indent=4)

with open('data.json', 'r') as fp:
    data = json.load(fp)
```

List comprehension with conditional

```
new_list = [x for x in blah blah blah ] 
```

## Conda

Create new env

```sh
conda create --name <ur env name here> python=3.8
```

Delete old env

```sh
conda env remove --name <ur env name here> 
```

Add conda env to jupyter 

```sh
idk lol
```

## Git commands

Remove large file from commit history - careful with this one:

```sh
git filter-branch -f --index-filter 'git rm --cached --ignore-unmatch <filepath>’ HEAD
```

Checkout branch from remote

```sh
git checkout -b <branch_name> origin/<branch_name>
```

## F1 vs Precision vs Recall vs Accuracy

F1 - blah blah blah 

Precision - percentage of positive predictions that were correct

Recall - percentage of positive class that was correctly identified

Accuracy - percentage of predictions that were correct

![](/assets/posts/f1_precision_recall.png)

<!-- ## Neural Nets
Linear Algebra
CNN math
How to understand Transformers -->
