---
title: Use Wercker to deploy Hexo blog
date: 2016-06-06 15:00:53
tags: [hexo, wercker]
thumbnail: /img/blog.png
categories: Technical
banner: /img/banner.png
---

# Get a Wercker account

- [Get started for free >](https://app.wercker.com/users/new/)
- [Get started with Github >](https://app.wercker.com/sessions/github/new)

## Must add Steps

1. wercker/add-to-known_hosts@2.0.1
2. leipert/add-ssh-key-gh-bb@0.0.6
3. wercker/email-notify@1.1.0
    - may need application specific password

## Config file for wercker

[wercker.yml](https://raw.githubusercontent.com/dracher/elogs/master/_config.yml)