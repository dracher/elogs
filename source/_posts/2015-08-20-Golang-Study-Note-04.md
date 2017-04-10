title: Golang Study Note 04
date: 2015-08-20 09:56:43
tags: golang
thumbnail: /img/golang.png
categories: Technical
---

## A wonderful article
[How to use interfaces in Go](http://jordanorelli.com/post/32665860244/how-to-use-interfaces-in-go)

---

## The core concept in Go’s type system

instead of designing our abstractions in terms of what kind of data our types can hold,
we design our abstractions in terms of what actions our types can execute.

<!-- more -->

### one way to use type `interface`

```go
type Animal interface {
    Speak() string
}

type Dog struct {
}

func (d Dog) Speak() string {
    return "Woof!"
}

type Cat struct {
}

func (c Cat) Speak() string {
    return "Meow!"
}

func main() {
    animals := []Animal{Dog{}, Cat{}}
    for _, animal := range animals {
        fmt.Println(animal.Speak())
    }
}
```

## The `interface{}` type

**All types satisfy the empty interface**

```go
func DoSomething(v interface{}) {
   // ...
}
```

<i class="fa fa-exclamation-triangle fa-2x"></i> **v** is not of any type, is a `interface{}` type

{% blockquote %}
An interface value is constructed of two words of data; one word is used to point to a method table for the value’s underlying type, and the other word is used to point to the actual data being held by that value.
{% endblockquote %}

["can I convert a []T to an []interface{}"](http://golang.org/doc/go_faq.html#convert_slice_of_interface)

## Pointers and interfaces

Another subtlety of interfaces is that an interface definition does not prescribe whether an implementor should implement the interface using a pointer receiver or a value receiver

a pointer type can access the methods of its associated value type, but not vice versa. That is, a `*Dog` value can utilize the Speak method defined on `Dog`, but as we saw earlier, a `Cat` value cannot access the Speak method defined on `*Cat`.

## Wrapping Up

- create abstractions by considering the functionality that is common between datatypes, instead of the fields that are common between datatypes
- an `interface{}` value is not of any type; it is of `interface{}` type
- interfaces are two words wide; schematically they look like (type, value)
- it is better to accept an `interface{}` value than it is to return an `interface{}` value
- a pointer type may call the methods of its associated value type, but not vice versa
- everything is pass by value, even the receiver of a method
- an interface value isn’t strictly a pointer or not a pointer, it’s just an interface
- if you need to completely overwrite a value inside of a method, use the * operator to manually dereference a pointer
