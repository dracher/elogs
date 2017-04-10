title: A supervisor tip
date: 2014-10-21 14:43:55
tags: [python, supervisor]
thumbnail: /img/python.png
---

### Some quotes

- [original post](https://coderwall.com/p/4tcw7w)
- [killasgroup](https://github.com/Supervisor/supervisor/blob/d46baedb87e5fa4a98b9110074291630f366bf9f/CHANGES.txt#L116)
- [stopasgroup](https://github.com/Supervisor/supervisor/blob/d46baedb87e5fa4a98b9110074291630f366bf9f/CHANGES.txt#L53)


### Solution

add `stopasgroup` works

```
[program:some_django]
command=python manage.py runserver
directory=/dir/to/app
stopasgroup=true
```