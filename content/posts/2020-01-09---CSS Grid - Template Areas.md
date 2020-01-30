---
title: CSS Grid - Template Areas
date: "2020-01-09T12:00:00+09:00"
template: "post"
draft: false
slug: "/posts/css_grid_template_areas/"
category: "HTML & CSS"
tags:
  - "html"
  - "css"
  - "grid"
description: grid-template-areas
socialImage: "../../static/media/css_grid_one.jpg"
---

<img src="../../static/media/css_grid_one.jpg">

![grid template areas.png](https://images.velog.io/post-images/qkrcndtlr123/c6499d60-3b7f-11ea-bac6-35599d657c1f/grid-template-areas.png)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>CSS Grid</title>
    <style>
      .father {
        display: grid;
        grid-auto-rows: 200px;
        grid-gap: 5px;
        grid-template-areas: "header header header" "content content sidebar" "content content sidebar" "footer footer footer";
      }
      .first {
        grid-area: header;
        background-color: #f1c40f; // yellow colour
      }

      .second {
        grid-area: sidebar;
        background-color: #27ae60; // green colour
      }

      .third {
        grid-area: footer;
        background-color: #3498db; // blue colour
      }

      .fourth {
        grid-area: content;
        background-color: #d35400; // red colour
      }
    </style>
  </head>
  <body>
    <div class="father">
      <div class="first"></div>
      <div class="second"></div>
      <div class="third"></div>
      <div class="fourth"></div>
    </div>
  </body>
</html>
```
