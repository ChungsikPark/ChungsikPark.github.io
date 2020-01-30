---
title: CSS Grid - Template Rows and Columns
date: "2019-12-26T12:00:00+09:00"
template: "post"
draft: false
slug: "/posts/css_grid_template_rows_and_columns/"
category: "HTML & CSS"
tags:
  - "html"
  - "css"
  - "grid"
description: grid-template-rows & grid-template-columns
socialImage: "../../static/media/css_grid_one.jpg"
---

<img src="../../static/media/css_grid_one.jpg">

![grid-basic.jpeg](https://images.velog.io/post-images/qkrcndtlr123/c6f40070-209f-11ea-ac83-7789855e0f19/grid-basic.jpeg)

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
        grid-template-rows: 30px 12px; // 행, height
        grid-template-columns: 30px 50px; // 열, width
        grid-gap: 5px; // 간격
      }
      .box {
        background-color: #f1c40f;
      }
    </style>
  </head>
  <body>
    <div class="father">
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
    </div>
  </body>
</html>
```
