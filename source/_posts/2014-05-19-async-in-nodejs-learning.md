title: Async in Nodejs learning
date: 2014-05-19 15:42:46
tags: [nodejs, javascript]
thumbnail: /img/blog.png
---

### Useful Reference

- [Offical Site](https://www.npmjs.org/package/async)
- [A great example collection on GitHub](https://github.com/freewind/async_demo.git)

### async.series

``` coffeescript

summaryByProfile: (cb, profile) ->
  async.series([
    (cbk) ->
      summaryByProfile_(profile, cbk)
  , (cbk) ->
      timeOutSessionId(profile, cbk)
  ], (err, results) ->
    cb.json({ret:results})
  )

summaryByProfile_ = (profile, cbk) ->
    db.all("SQL query here",
      (err, rows) ->
        cbk(err, rows)  # Important here pass `err` and `output` into callback
    )

```