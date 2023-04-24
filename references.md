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
(credit to [levy5674](https://github.com/levy5674)!)

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
new_list = [x if x <3 else y for x in list ]
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
duration = time.time() - start
print(duration)
```

## Jupyter Magic Commands

```
%matplotlib inline

%load_ext autoreload
%autoreload 2
```

Startup Script (`#!/bin/bash` not needed if it's not a script)
```
#!/bin/bash
jupyter lab \
    --port=8888 \
    --allow-root \
    --NotebookApp.token='' \
    --NotebookApp.password=''
```

Add conda env to jupyter 

```sh
python -m ipykernel install --user --name <ur_env_name_here> --display-name "<ur display name here>"
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
conda create --name <ur_env_name_here> python=3.8
```

Delete old env

```sh
conda env remove --name <ur_env_name_here> 
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

## Copy files to and from remote
From your local machine:
```sh
scp /path/to/local/file user@example.com:/home/name/dir

scp user@example.com:/home/name/dir/file /path/to/local/dir
```
You can replace `user@example.com` with predefined aliases in `.ssh/config`

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
