## Information

[![PyPI](https://img.shields.io/pypi/v/pylprename.svg)](https://pypi.org/project/pylprename)
[![PyPI](https://img.shields.io/pypi/format/pylprename.svg)]()
[![PyPI](https://img.shields.io/pypi/pyversions/pylprename.svg)]()

**pylprename** is a plugin for [Pylp](https://github.com/pylp/pylp) that rename files in
a stream.


## Installation

Install **pylprename** with `pip`:

    pip install pylprename

If you don't have Python `Scripts` folder in your PATH you can run also:

    python -m pip install pylprename


## Usage

```python
import pylp
from pylprename import rename

# Rename with a string
pylp.src('src/main/text/hello.txt')
  .pipe(rename('ciao/goodbye.md'))
  .pipe(pylp.dest('dist'))  # ./dist/ciao/goodbye.md


# Rename with a function
pylp.src('src/main/text/hello.txt')
  .pipe(rename(lambda n:
    n.replace('ell', 'all')
  ))
  .pipe(pylp.dest('dist'))  # ./dist/hallo.txt


# Rename with some values (all values are optional)
pylp.src('src/main/text/hello.txt')
  .pipe(rename(
    dirname='md/ciao',
    basename='aloha',
    prefix='bonjour-',
    suffix='-hola',
    ext='.md'
  ))
  .pipe(pylp.dest('dist'))  # ./dist/md/ciao/bonjour-aloha-hola.md
```


## Notes

- `basename` is the filename **without** the extension
- `ext`  is the file extension **including the '.'**
