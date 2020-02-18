---
title: "Auto Generate requirements.txt from Your Python Code"
date: 2020-02-19T00:19:42+09:00
draft: false
tags: ["Python", "DepHell", "Dependencies Resolution"]
---
## Introduction

If you are working with data scientists, he might not make requirements.txt when he write code in "notebook". And you often need to run the program on your PC, even though the program only ran on his machine. In this case, you may have to create python virtual envrironment without requirements.txt(or other dependencies list).

Of course, if he who write the program could make it, it would be the easiest solution. But when it is impossible, there are the following solution: you are programmer, so you can use the program. It's name is DepHell.

## DepHell

[dephell/dephell: Python project management\. Manage packages: convert between formats, lock, install, resolve, isolate, test, build graph, show outdated, audit\. Manage venvs, build package, bump version\.](https://github.com/dephell/dephell)

DepHell has many features. One of them is converting between formats, e.g. requirements.txt, Pipfile, setup.py something else. Especially, you can convert from your code: that is, it can be generated requirements.txt from import statements.

### Installation

```
curl -L dephell.org/install | python3
```

If you need more detail, see [installation documentation](https://dephell.readthedocs.io/installation.html).

### How To Use

I show a simple example. If you have a python package like this:

```
.
└── my_package
    ├── __init__.py
    └── main.py
```

and `main.py` is like following.

```python
import numpy as np
import pandas as pd
from sklearn.svm import SVC
import matplotlib.pyplot as plt
import seaborn as sns

def main():
    ...  # write something

if __name__ == '__main__':
    main()

```

In this situation, all you need is running this.

```sh
dephell deps convert --from=imports --to=requirements.txt
```

You will have requirements.txt. It has all packages you need.

```
$ cat requirements.txt 
matplotlib
numpy
pandas
scikit-learn
seaborn
```
