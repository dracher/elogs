title: Golang Study Note 02
thumbnail: /img/golang.png
date: 2015-07-10 20:43:13
tags: golang
categories: Technical
---

## 初始化嵌套的结构体

```golang
type File struct {
	name string
	size int
	attr struct {
		perm  int
		owner int
	}
}

// Method 1

f := File {
    name: "t.txt",
    size: 1033,
}

f.attr.perm = 0664
f.attr.owner = 1

// Method 2
// This works, but not recommended

f := File {
    name: "t.txt",
    size: 1033,
    attr: struct {
        perm  int
        owner int
    }{0664, 1},
}
```


## Variadic Functions

Variadic functions can be called in the usual way with individual arguments.
If you already have multiple args in a slice, 
apply them to a variadic function using func(slice...) like this.

```go
nums := []int{1, 2, 3, 4}
sum(nums...)
```