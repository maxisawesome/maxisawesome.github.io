---
title: References
layout: post
---

Amalgamation of code, commands, formulas, or tidbits I find myself repeatedly googling the syntax of 

## ML code

The most basic calls to openai client
```
import openai
client = openai.OpenAI(base_url=base_url, api_key=os.environ['OPENAI_API_KEY']) 
prompt = "your prompt here!"
response = client.chat.completions.create(
    model=model,
    messages=[{'role': 'user', 'content': prompt}],
    max_tokens=max_tokens,
)
print(response.choices[0].message.content)

```
<!-- 
Call openai client with threads
```
import openai

shared_client = OpenAI(base_url=base_url, api_key=os.environ['OPENAI_API_KEY'])

def generate(content: str):
    return shared_client.chat.completions.create(
        model=model,
        messages=[{'role': 'user', 'content': content}],
        max_tokens=max_tokens,
    ).choices[0].message.content

with ThreadPoolExecutor(max_workers=12) as executor:
    futures = {executor.submit(generate, content): index for index, row in df.iterrows()}
    for future in tqdm(as_completed(futures)):
        index = futures[future]
        result = future.result()
        
        df.loc[index, f'{model}_response'] = result

``` -->

Using a tiktoken tokenizer
```
import tiktoken

enc = tiktoken.encoding_for_model("gpt-4")

tokens = enc.encode("The profundities are mine to ransack!")
not_tokens = enc.decode([1, 2, 3, 4])
```

Using a HuggingFace Tokenizer
```
from transformers import AutoTokenizer

tokenizer = AutoTokenizer.from_pretrained("bert-base-cased")
tokens = tokenizer("My totality eclipses the cosm!")['input_ids']
not_tokens = tokenizer.decode([1, 2, 3, 4])
```

Load a HF dataset
```
from datasets import load_dataset
dataset = load_dataset("Aiden07/dota2_instruct_prompt", name="train")
```


## Python

Dict <--> JSON

```
import json
with open('data.json', 'r') as fp:
    data = json.load(fp)

with open('data.json', 'w') as fp:
    json.dump(data, fp, sort_keys=True, indent=4)
```

Read a .jsonl
```
import json

file_path = 'data.jsonl'
with open(file_path, 'r', encoding='utf-8') as file:
    for line in file:
        data = json.loads(line)
        print(data)
```

Write a .jsonl

```
import json

with open('output.jsonl', 'w') as outfile:
    for dict in list_of_dicts:
        json.dump(dict, outfile)
        outfile.write('\n')
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

Or with a decorator!
(credit to [Suresh Kumar](https://dev.to/kcdchennai/python-decorator-to-measure-execution-time-54hk)!)
```
from functools import wraps
import time


def timeit(func):
    @wraps(func)
    def timeit_wrapper(*args, **kwargs):
        start_time = time.perf_counter()
        result = func(*args, **kwargs)
        end_time = time.perf_counter()
        total_time = end_time - start_time
        print(f'Function {func.__name__}{args} {kwargs} Took {total_time:.4f} seconds')
        return result
    return timeit_wrapper


@timeit
def calculate_something(num):
    """
    Simple function that returns sum of all numbers up to the square of num.
    """
    total = sum((x for x in range(0, num**2)))
    return total

if __name__ == '__main__':
    calculate_something(10)
    calculate_something(100)
    calculate_something(1000)
    calculate_something(5000)
    calculate_something(10000)

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

See staged changes
```sh
git diff --cached
```

See changes from latest commit

```sh
git diff HEAD~ HEAD
```

See changes from last X commits

```sh
git diff HEAD~X HEAD
```

## Copy files to and from remote
From your local machine:
```sh
scp /path/to/local/file user@example.com:/home/name/dir

scp user@example.com:/home/name/dir/file /path/to/local/dir
```
You can replace `user@example.com` with predefined aliases in `.ssh/config`

## F1 vs Precision vs Recall vs Accuracy

![](/assets/posts/f1_recall_precision.png)

Precision - percentage of positive predictions that were correct - True Positive / (False Positives + True Positives)

Recall - percentage of positive class that was correctly identified - True Positive / (False Negatives + True Positives)

Accuracy - percentage of predictions that were correct - True Positive + True Negatives / (False Positives + False Negatives + True Positives + True Negatives)

F1 - 2 * (Precision * Recall) / (Precision + Recall) - harmonic mean of precision and recall 


## i.e. vs e.g.
I.e. stands for id est or 'that is' and is used to clarify the statement before it. 
E.g. means exempli gratia or 'for example. '

<!-- test -->

<!-- ## Neural Nets
Linear Algebra
CNN math
How to understand Transformers -->
