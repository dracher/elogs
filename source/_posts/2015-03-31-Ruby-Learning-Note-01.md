title: Ruby Learning Note 01
thumbnail: /img/ruby.jpg
date: 2015-03-31 23:46:00
tags: ruby
categories: Technical
---

## Ruby Convention

- local variables, method parameters, and method names should all start with a lowercase letter2 or an underscore
- global variables are prefixed with a dollar sign ($)
- instance variables begin with an “at” sign (@)
- class variables start with two “at” signs (@@)
- class names, module names, and constants must start with an uppercase letter.

```
Local Variable:     name fish_and_chips x_axis thx1138 _x _26
Instance Variable:  @name @point_1 @X @_ @plan9
Class Variable:     @@total @@symtab @@N @@x_pos @@SINGLE
Global Variable:    $debug $CUSTOMER $_ $plan9 $Global
Class Name:         String ActiveRecord MyClass
Constant Name:      FEET_PER_MILE DEBUG
```
<!--more-->

## Tricks

改变ruby里hash的默认值

```ruby
h = Hash.new
# => nil 

h = Hash.new(0)
# => 0
```


## Access Control in Ruby

**Public methods**
can be called by anyone—no access control is enforced. Methods are public by default (except for `initialize` , which is always private)

**Protected methods**
can be invoked only by objects of the defining class and its subclasses. Access is kept `within the family`.

**Private methods**
cannot be called with an explicit receiver—the receiver is always the current object, also known as `self` . This means that private methods can be called only in the context of the current object; you can’t invoke another object’s private methods.


## Alternative way to define access control

```ruby
class MyClass
  def method1
  end
  
  def method2
  end
  
  def method3
  end

  def method4
  end

  public     :method1, :method4
  protected  :method2
  private    :method3
end
```


## Arrary

- a[start, count]

    a = [1, 3, 5, 7, 9]

    e.g.: a[1, 3] means from positon 1 pick 3 elements from arrary

    a [1, 3] = [3, 5, 7]

- a[start..[.]end]

    a[1..3] = [3, 5, 7]

    a[1...3] = [3, 5]

