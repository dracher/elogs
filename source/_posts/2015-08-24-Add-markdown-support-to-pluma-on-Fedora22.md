title: Add markdown support to pluma on Fedora22
thumbnail: /img/linux.jpg
categories: Technical
date: 2015-08-24 16:30:12
tags: [linux, pluma]
---

Markdown syntax highlighting isn't supported in the version of `gtksourceview2` that ships with Fedora22.

The easy fix seems to be to check that `gtksourceview3` is installed, if not then:

- Install with dnf

    ```
    sudo dnf install gtksourceview3
    ```

- Make soft link

    ```
    sudo ln -s /usr/share/gtksourceview-3.0/language-specs/markdown.lang /usr/share/gtksourceview-2.0/language-specs/
    ```

- Restart `Pluma` if not work
