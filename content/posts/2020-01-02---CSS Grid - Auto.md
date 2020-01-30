---
title: CSS Grid - Auto Rows and Columns
date: "2020-01-02T12:00:00+09:00"
template: "post"
draft: false
slug: "/posts/css_grid_auto_rows_and_columns/"
category: "HTML & CSS"
tags:
  - "html"
  - "css"
  - "grid"
description: grid-auto-rows & grid-auto-columns
socialImage: "../../static/media/css_grid_one.jpg"
---

<img src="../../static/media/css_grid_one.jpg">

![grid-auto-rows.png](https://images.velog.io/post-images/qkrcndtlr123/8acf2610-22e8-11ea-b744-67a9c7414bce/grid-auto-rows.png)

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
        grid-template-rows: 300px 120px; // 행, height
        grid-template-columns: 300px 150px; // 열, width
        grid-gap: 5px; // 간격
        grid-auto-rows: 60px;
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
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
    </div>
  </body>
</html>
```

![grid-auto-columns.png](https://images.velog.io/post-images/qkrcndtlr123/94720980-22e8-11ea-a931-9df1f37fabff/grid-auto-columns.png)

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
        grid-template-rows: 300px 120px;
        grid-template-columns: 300px 150px;
        grid-gap: 5px;
        grid-auto-columns: 60px;
        grid-auto-flow: column;
        /* it is similar as flex-direction in flexbox. and default value is row */
      }
      .box {
        background-color: #f1c40f;
      }
    </style>
  </head>
  <body>
    <!-- when input ".father>.box*6", output as below -->
    <div class="father">
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
    </div>
  </body>
</html>
```
