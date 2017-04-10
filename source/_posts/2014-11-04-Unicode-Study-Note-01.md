title: UNICODE Study Note One
date: 2014-11-04 08:19:59
tags: utf-8
thumbnail: /img/blog.png
---

UTF-8的编码规则很简单，只有二条：

1. 对于单字节的符号，字节的第一位设为0，后面7位为这个符号的unicode码。因此对于英语字母，UTF-8编码和ASCII码是相同的。
2. 对于n字节的符号（n>1），第一个字节的前n位都设为1，第n+1位设为0，后面字节的前两位一律设为10。剩下的没有提及的二进制位，全部为这个符号的unicode码。

<!--more-->

```
--------------------+---------------------------------------------
0000 0000-0000 007F | 0xxxxxxx
0000 0080-0000 07FF | 110xxxxx 10xxxxxx
0000 0800-0000 FFFF | 1110xxxx 10xxxxxx 10xxxxxx
0001 0000-0010 FFFF | 11110xxx 10xxxxxx 10xxxxxx 10xxxxxx
```

## Good Article

- [The Absolute Minimum Every Software Developer Absolutely, Positively Must Know About Unicode and Character Sets](http://www.joelonsoftware.com/articles/Unicode.html)
- [ASCII](http://www.robelle.com/library/smugbook/ascii.html)
- [ASCII Doc](http://www.jimprice.com/ascii-dos.gif)
- [Code Pages](http://www.i18nguy.com/unicode/codepages.html#msftdos)


## Terms

- Code Point

	**In Unicode, a letter maps to something**

- High-endian or Low-endian mode

	**FF FE or FE FF**


## Quotes

---

{% blockquote Joel Spolsky http://www.joelonsoftware.com/articles/Unicode.html  The Absolute Minimum Every... %}
Programmers were encouraged not to use s++ and s-- to move backwards and forwards, but instead to call functions such as Windows' AnsiNextand AnsiPrev which knew how to deal with the whole mess.
{% endblockquote %}

---

{% blockquote Joel Spolsky http://www.joelonsoftware.com/articles/Unicode.html  The Absolute Minimum Every... %}
There Ain't No Such Thing As Plain Text.
{% endblockquote %}
