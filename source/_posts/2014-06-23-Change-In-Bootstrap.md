title: How to make on/off state color contrast more obvious in Bootstrap
date: 2014-06-23 17:30:41
tags: [bootstrap, css]
thumbnail: /img/blog.png
---

Bootstrap version : `3.1.1`

Line 209 from `bootstrap.js`

Change 

```javascript
if (changed) this.$element.toggleClass('active')
```

To

```javascript
if (changed) this.$element.toggleClass('btn-success')  // or whatever u want
```

- [Ref Link](http://stackoverflow.com/questions/13891650/twitter-bootstrap-button-toggle-how-to-make-on-off-state-color-contrast-more-o)