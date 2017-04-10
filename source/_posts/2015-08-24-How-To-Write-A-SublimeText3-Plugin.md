title: How To Write A SublimeText3 Plugin
thumbnail: /img/sublime-text.png
categories: Technical
date: 2015-08-24 15:45:56
tags: [python, sublime-text]
---

最近把 _Blog_ 从 [Jekyll](http://jekyllrb.com/) 转到了 [Hexo](https://hexo.io/), No reason, just 折腾 ㄟ( ▔, ▔ )ㄏ
以前一直都在用 SublimeText + [Jekyll](https://packagecontrol.io/packages/Jekyll) 的组合，所以自然也去搜索了下是否有Hexo适用的插件...

(;´༎ຶД༎ຶ`) 然而并**没有**  ┻━┻︵╰(‵□′)╯︵┻━┻
好吧一直想学习下SublimeText的插件的写法，天赐良机啊
因为懒（几）得（乎）去（没）翻（有）文（啊）档（！）

---

## Environment

Name | Value
-----|------
OS | 4.1.5-200.fc22.x86_64
Desktop | Mate 1.10.1
SublimeText | Build 3083


## The Very First Step

1. 打开sblt, `Menu`  ->  `Tools`  ->  `New Plugins...`

<i class="fa fa-hand-o-right"></i>  **to be continued...**


<!--
## 1.共有两种命令类型

- Window commands (sublime_plugin.WindowCommand)
- Text commands (sublime_plugin.TextCommand)

所有命令必须要实现 `.run()` 方法，这些方法可以接受任意长度的 **keyword parameters**

**Note:** 参数必须是合法的JSON值，因为ST会将参数转换为JSON格式



## 2. APIs

### Region

- region.a
- region.b
- region.begin
- region.end

这两者都可表示选择区域的端点，区别在于`a`, `b` 的值取决于选择的方向
比如

    import os

当你用鼠标从左向右选择import时, `a`和`b`值为

    (0, 6)

当你用鼠标从右向左选择import时，`a`和`b`的值为

    (6, 0)

而`begin`和`end`是按从左向右的方式给出端点的值，即是无论如何选择import，`begin`和`end`的指都为

	(0, 6)

---

- region.contains
- region.cover
- region.empty

- region.intersection
- region.intersects
- region.size
- region.xpos
-->
