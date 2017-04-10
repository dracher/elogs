title: Golang Study Note 01
date: 2014-05-20 09:51:15
tags: golang
thumbnail: /img/golang.png
updated: 2015-08-20T21:20:45+08:00
categories: Technical
---

### Function Name

- Capital first mean can access outside package
- Lower first mean only access inside package

### Normal Usage

``` golang
package main

func quickSort () {    // Private
    ...
}

func QuickSort () {    // Public
    quickSort()
}
```

### Difference between `Make` and `New`

`make` 用于内建类型（`map`、`slice` 和`channel`）的内存分配。`new`用于各种类型的内存分配。

`new`返回指针。
`make`返回初始化后的（非零）值。