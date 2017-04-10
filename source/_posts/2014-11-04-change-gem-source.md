title: Change gem source due to f**king wall
date: 2014-11-04 08:17:38
tags: ruby
thumbnail: /img/ruby.jpg
---

### Change to taobao's mirror 

```
$ gem sources --remove https://rubygems.org/
$ gem sources -a https://ruby.taobao.org/
$ gem sources -l
```