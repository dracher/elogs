---
title: Redux Learning Notes
banner: http://o86u18lvr.bkt.clouddn.com/blog/react.png
date: 2017-08-14 11:30:07
tags: [react, redux]
---

## 1. Building an Effective Redux Store

1. **Don't duplicate data**. If data lives in multiple places, you have no single source of truth, and you waste resources trying to keep the data in sync with each other.
2. **Keep your store as shallow as possible**. Nested data makes reducer logic more complicated (trying to update deeply nested data can get complex and slow quickly)

<!-- more -->

> "In a more complex app, you’re going to want different entities to reference each other. We suggest that you keep your state as normalized as possible, without any nesting. Keep every entity in an object stored with an ID as a key, and use IDs to reference it from other entities, or lists."

## 2. Organizing The Directory Structure Of A Redux Application

- Organization by Type

```
Frontend
   - Components
      - component1.js
      - component2.js
      - component3.js
   - Actions
      - action1.js
      - action2.js
   - Reducers
      - reducer1.js
   - Util
   - Store
```

- Organization by Feature

```
- nav
   - actions.js
   - index.js
   - reducer.js

- dashboard
   - actions.js
   - index.js
   - reducer.js
```

- [An alternative way to handle actions and reducers](https://github.com/reactjs/redux/issues/2378)