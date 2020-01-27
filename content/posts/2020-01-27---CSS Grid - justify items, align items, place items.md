---
title: CSS Grid - justify-items, align-items, place-items
date: "2020-01-27T12:00:00+09:00"
template: "post"
draft: false
slug: "/posts/css_grid_justify_items_and_align_items_and_place_items/"
category: "HTML & CSS"
tags:
  - "HTML"
  - "CSS"
  - "grid template columns"
  - "justify-items"
  - "align-items"
  - "place-items"
description: justify-items, align-items, place-items
socialImage: "../../static/media/css_grid_one.jpg"
---

<img src="../../static/media/css_grid_one.jpg">

![justify items center.png](https://images.velog.io/post-images/qkrcndtlr123/606579e0-40db-11ea-9bd2-93871bb104c4/justify-items-center.png)

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
        grid-gap: 10px;
        grid-auto-rows: 100px;
        grid-template-columns: repeat(5, 100px);
        color: white;
        height: 100vh;
        justify-items: center;
      }
      .box:nth-child(even) {
        background-color: #3498db; /* light blue colour */
      }
      .box:nth-child(odd) {
        background-color: #34495e; /* dark blue colour */
      }
    </style>
  </head>
  <body>
    <div class="father">
      <div class="box">1</div>
      <div class="box">2</div>
      <div class="box">3</div>
      <div class="box">4</div>
      <div class="box">5</div>
    </div>
  </body>
</html>
```

![align items center.png](https://images.velog.io/post-images/qkrcndtlr123/6c8f5650-40db-11ea-9c20-43c7dac52886/align-items-center.png)

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
        grid-gap: 10px;
        grid-auto-rows: 100px;
        grid-template-columns: repeat(5, 100px);
        color: white;
        height: 100vh;
        align-items: center;
      }
      .box:nth-child(even) {
        background-color: #3498db; /* light blue colour */
      }
      .box:nth-child(odd) {
        background-color: #34495e; /* dark blue colour */
      }
    </style>
  </head>
  <body>
    <div class="father">
      <div class="box">1</div>
      <div class="box">2</div>
      <div class="box">3</div>
      <div class="box">4</div>
      <div class="box">5</div>
    </div>
  </body>
</html>
```

![place items end center.png](https://images.velog.io/post-images/qkrcndtlr123/772f5e70-40db-11ea-9c20-43c7dac52886/place-items-end-center.png)

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
        grid-gap: 10px;
        grid-auto-rows: 100px;
        grid-template-columns: repeat(5, 100px);
        color: white;
        height: 100vh;
        place-items: end center;
      }
      .box:nth-child(even) {
        background-color: #3498db; /* light blue colour */
      }
      .box:nth-child(odd) {
        background-color: #34495e; /* dark blue colour */
      }
    </style>
  </head>
  <body>
    <div class="father">
      <div class="box">1</div>
      <div class="box">2</div>
      <div class="box">3</div>
      <div class="box">4</div>
      <div class="box">5</div>
    </div>
  </body>
</html>
```
