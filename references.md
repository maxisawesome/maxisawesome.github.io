---
title: References
layout: post
---

Amalgamation of code, commands, formulas, or tidbits I find myself repeatedly googling the syntax of 

## Python

Dict <--> JSON

```
import json
with open('data.json', 'r') as fp:
    data = json.load(fp)

with open('data.json', 'w') as fp:
    json.dump(data, fp, sort_keys=True, indent=4)
```

Pretty print a dictionary/JSON

```
print(json.dumps(ur_dict, indent=4))
```

Page through a compressed JSON

```
import gzip
import json
import boto3

def stream_objects(filename):
    with gzip.open(filename, 'rt') as f:
        for line in f:
            yield json.loads(line)

json_path = "json_path.ndjson.gz"
for i, line in enumerate(stream_objects(json_filepath)):
    print(line.keys())
    break

```

List comprehension with conditionals
why are they like this w/ different conditionals this annoys me
```
new_list = [x for x in list]
new_list = [x for x in list if x <3]
new_list = [x if x <3 else y for x in x ]
```

Debugging Interpreter 
```
import IPython; IPython.embed()
```

Time something in seconds
```
import time
start = time.time()
function_to_time()
end = time.time()
duration = end - start
```

## Jupyter Magic Commands

```
%matplotlib inline

%load_ext autoreload
%autoreload 2
```

## Bash

find a file with wildcards
```
find . -name "*.csv"
```

unzip file
```
unzip file.zip -d destination_folder
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
python -m ipykernel install --user --name <ur env name here> --display-name "<ur display name here>"
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

Precision - percentage of positive predictions that were correct - True Positive / (False Positives + True Positives)

Recall - percentage of positive class that was correctly identified - True Positive / (False Negatives + True Positives)

Accuracy - percentage of predictions that were correct - True Positive + True Negatives / (False Positives + False Negatives + True Positives + True Negatives)

F1 - harmonic mean of precision and recall 

![](/assets/posts/f1_precision_recall.png)

<!-- ## Neural Nets
Linear Algebra
CNN math
How to understand Transformers -->
