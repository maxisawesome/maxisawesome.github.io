---
title: References
layout: post
---

## Python

Save a dict to a json
```
import json

with open('data.json', 'w') as fp:
    json.dump(data, fp, sort_keys=True, indent=4)

with open('data.json', 'r') as fp:
    data = json.load(fp)
```

## Conda

Create new env
```sh
conda create --name <ur env name here> python=3.8
```

Delete old env
```sh
conda env remove --name bio-env
```

Add conda env to jupyter 
```sh
```

## Git commands

Remove large file from commit history - careful with this one:
```sh
git filter-branch -f --index-filter 'git rm --cached --ignore-unmatch <filepath>’ HEAD
```

## F1 vs Precision vs Recall vs Accuracy
Precision - percentage of positive predictions that were correct
Recall - percentage of positive class that was correctly identified

![](/assets/posts/f1_precision_recall.png)

<!-- ## Neural Nets
Linear Algebra
CNN math
How to understand Transformers -->
