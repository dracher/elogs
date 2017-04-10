title: Notes about from py2 to py3
thumbnail: /img/python.png
categories: Technical
date: 2015-12-10 14:18:59
tags: python
---

# Text vs Data Instead Of Unicode Vs. 8-bit

- Python 3.0 uses the concepts of text and (binary) data instead of Unicode strings and 8-bit strings,
Use str.encode() to go from str to bytes, and bytes.decode() to go from bytes to str
<!-- more -->
	```python
	>>> s1 = "汉字"
	>>> s1.encode()
	>>> b'\xe6\xb1\x89\xe5\xad\x97'

	>>> s2 = b'汉'
	>>> SyntaxError: bytes can only contain ASCII literal characters.

	>>> s2 = b'\xe6\xb1\x89'
	>>> s2.decode()
	>>> '汉'
	```

- You can no longer use `u"..."` literals for Unicode text. However, you must use `b"..."` literals for binary data

### To be prepared in Python 2.x

- start using `unicode` for all unencoded text
- `str` for binary or encoded data only

### Resources

[Unicode HOWTO](https://docs.python.org/3.0/howto/unicode.html#unicode-howto)

# Overview Of Syntax Changes

## [PEP 3107](http://www.python.org/dev/peps/pep-3107)

