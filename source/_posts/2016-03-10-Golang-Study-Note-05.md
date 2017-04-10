title: Golang Study Note 05
thumbnail: /img/golang.png
categories: Technical
date: 2016-03-10 15:20:06
tags: golang
---

## [The Go Blog](http://blog.golang.org) 学习之 [The Laws of Reflection](http://blog.golang.org/laws-of-reflection)

### Type Assertion

```golang

var r io.Reader
tty, err := os.OpenFile("/dev/tty", os.O_RDWR, 0)
if err != nil {
    return nil, err
}
r = tty

var w io.Writer
w = r.(io.Writer)

```
