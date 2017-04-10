title: Install youdao-dict in Fedora22
thumbnail: /img/blog.png
categories: Technical
date: 2015-10-29 11:10:09
tags: [fedora, linux, youdao-dict]
---

## 1.Add FZUG Repo

- <i class="fa fa-external-link"></i>[origina site](http://repo.fdzh.org/)

**Fedora22+**

```bash
# dnf config-manager --add-repo=http://repo.fdzh.org/FZUG/FZUG.repo
```

or

```bash
# dnf install http://repo.fdzh.org/FZUG/free/23/x86_64/fzug-release-23-0.1.noarch.rpm
```

or

```bash
# wget http://repo.fdzh.org/FZUG/FZUG.repo -P /etc/yum.repos.d/
```

<!-- more -->

## 2.Install Package

```bash
# dnf update && dnf install youdao-dict
```

## 3.Some issue may occurs

- wrong import path, if met follow erros

	```python
	Traceback (most recent call last):
	File "/usr/bin/youdao-dict", line 27, in <module>
	from dae.daeclient import DAEClient
	File "/usr/lib/python3.4/site-packages/youdao-dict/dae/daeclient.py", line 31, in <module>
	from PyQt5.Qt import QApplication
	```

Here should change

```python
from PyQt5.Qt import QApplication 
```

to 

```python
from PyQt5.QtWidgets import QApplication
```

- `libQt5Widgets.so.5` not found

	```python
	from PyQt5.QtWidgets import QApplication
	Traceback (most recent call last):
	  File "<stdin>", line 1, in <module>
	ImportError: libQt5Widgets.so.5: cannot open shared object file: No such file or directory
	```

Possbible solution

```bash
dnf install qt5-qtbase-static
```

- `libQt5Sensors.so.5` not found

	```python
	Traceback (most recent call last):
	File "<stdin>", line 1, in <module>
	ImportError: libQt5Sensors.so.5: cannot open shared object file: No such file or directory
	```

Possbible solution

```bash
dnf install qt5-qtsensors
```