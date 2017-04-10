title: How To Write Docstring In Python
thumbnail: /img/python.png
categories: Technical
date: 2015-09-09 00:00:35
tags: python
---

<i class="fa fa-external-link"></i> [PEP-0257](https://www.python.org/dev/peps/pep-0257/)

<!-- more -->

# One-line Docstrings

- Triple quotes are used even though the string fits on one line. This makes it easy to later expand it.
- The closing quotes are on the same line as the opening quotes. This looks better for one-liners.
- There's no blank line either before or after the docstring.
- The docstring is a phrase ending in a period. It prescribes the function or method's effect as a command (`Do this`, `Return that`), not as a description; e.g. don't write `Returns the pathname ...`.
- The one-line docstring should NOT be a `signature` reiterating the function/method parameters (which can be obtained by introspection). Don't do:

```python
def function(a, b):
    """function(a, b) -> list"""
```

# Multi-line Docstrings

Multi-line docstrings consist of a summary line just like a one-line docstring, followed by a blank line, followed by a more elaborate description. The summary line may be used by automatic indexing tools; it is important that it fits on one line and is separated from the rest of the docstring by a blank line. The summary line may be on the same line as the opening quotes or on the next line. The entire docstring is indented the same as the quotes at its first line (see example below).

```python
def complex(real=0.0, imag=0.0):
    """Form a complex number.

    Keyword arguments:
    real -- the real part (default 0.0)
    imag -- the imaginary part (default 0.0)
    """
    if imag == 0.0 and real == 0.0:
        return complex_zero
    ...
```
