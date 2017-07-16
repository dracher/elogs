title: Golang Study Note 03
thumbnail: /img/golang.png
date: 2015-08-02 20:54:53
tags: golang
categories: Technical
---

## XOR in Golang

1. either one (is one), but not both

```go
1 ^ 1 = 0
1 ^ 0 = 1
0 ^ 0 = 0
0 ^ 1 = 1
```

## Go Routine

1. Create go routine

```
go function(args)
go func(args) { block } (args)
```