---
title: Common VSCode Plugins
date: 2017-07-05 15:31:11
tags: [vscode]
categories: Technical
banner: http://res.cloudinary.com/djg5fdwv1/image/upload/v1450770293/vs-code-logo_llvaum.png
---

## Recommended Plugins

<div class="justified-gallery">
![p01](http://o86u18lvr.bkt.clouddn.com/vscode/plugin01.png)
![p02](http://o86u18lvr.bkt.clouddn.com/vscode/plugin02.png)
</div>

<!-- more -->

## 1. Install `Fira Code` font to support `fontLigatures` feature

1. download the font file [latest](https://github.com/tonsky/FiraCode/releases/download/1.204/FiraCode_1.204.zip)
2. unzip the file, and cp everything under directory `ttf/` to `/usr/share/fonts/<make a dir with whatever name you want>/`
3. `chmod 755 *` all the files you just copied
4. run follow commands:

    ```
    $> mkfontscale
    $> mkfontdir
    $> fc-cache -fv
    ```

5. in `settings`, change `"editor.fontLigatures": false,` to `"editor.fontLigatures": true,`