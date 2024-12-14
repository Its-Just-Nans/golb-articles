# Python

## How to print the error name

```python
import traceback

try:
    #code here
except Exception as exception:
    print(type(exception).__name__)
    print(exception.__class__.__name__)
    print(exception.__class__.__qualname__)
    print(traceback.format_exc())
```

Reference : [stackOverflow](https://stackoverflow.com/questions/18176602/how-to-get-the-name-of-an-exception-that-was-caught-in-python)

## Super easy multiprocess

```python
from multiprocessing import Pool

def multi_process(my_func, my_args, num_processes=10):
    """my_args is a table of arguments for my_func"""
    results = []

    with Pool(processes=num_processes) as pool:
        for result in pool.imap(my_func, my_args):
            results.append(result)

    return results
```

## How to get the path of the current folder

```python
import pathlib
pathlib.Path(__file__).parent.resolve()
```

## How to get the KeyboardInterrupt

```python
try:
    #code here
except KeyboardInterrupt:
    pass
    #or do something
```

## Pylint

```sh
python3 -m pip install pylint
pylint <filename>
```

## The Zen of Python

```sh
python -c "import this"
```

## Get the path to a package

```sh
python -c "import numpy as _;print(_.__path__)"
python -c "import numpy as _;print(_.__file__)"
```

## Simple http server

```sh
python -m http.server
```

## Pip config

Location:

- Windows: `$HOME/pip/pip.ini`
- Linux: `$HOME/.pip/pip.conf`

```sh
# show the location
pip config debug
# location location and config
pip config -v list
```
