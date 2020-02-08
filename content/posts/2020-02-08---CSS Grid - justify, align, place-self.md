---
title: CSS Grid - Justify, Align, Place Self
date: "2020-02-08T12:00:00+09:00"
template: "post"
draft: false
slug: "/posts/justify_align_place_self/"
category: "HTML & CSS"
tags:
  - "html"
  - "css"
  - "grid"
description: Justify, Align, Place Self
socialImage: "../../static/media/css_grid_one.jpg"
---

<img src="../../static/media/css_grid_one.jpg">

![justify-self center.png](https://images.velog.io/post-images/qkrcndtlr123/963e0990-4a3d-11ea-a3f6-05b394ecbeee/justify-self-center.png)

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
        grid-template-columns: repeat(5, 1fr);
      }
      .box {
        display: flex;
        align-items: center;
        justify-content: center;
        color: white;
      }
      .box:nth-child(even) {
        background-color: #3498db; /* light blue colour */
      }
      .box:nth-child(odd) {
        background-color: #34495e; /* dark blue colour */
      }
      .box:first-child {
        justify-self: center;
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
      <div class="box">6</div>
      <div class="box">7</div>
      <div class="box">8</div>
      <div class="box">9</div>
    </div>
  </body>
</html>
```

![align-self center.png](https://images.velog.io/post-images/qkrcndtlr123/9eb27f20-4a3d-11ea-9be2-914d7a4b9643/align-self-center.png)

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
        grid-template-columns: repeat(5, 1fr);
      }
      .box {
        display: flex;
        align-items: center;
        justify-content: center;
        color: white;
      }
      .box:nth-child(even) {
        background-color: #3498db; /* light blue colour */
      }
      .box:nth-child(odd) {
        background-color: #34495e; /* dark blue colour */
      }
      .box:first-child {
        align-self: center;
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
      <div class="box">6</div>
      <div class="box">7</div>
      <div class="box">8</div>
      <div class="box">9</div>
    </div>
  </body>
</html>
```

![place-self center center.png](https://images.velog.io/post-images/qkrcndtlr123/a6bc24f0-4a3d-11ea-9be2-914d7a4b9643/place-self-center-center.png)

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
        grid-template-columns: repeat(5, 1fr);
      }
      .box {
        display: flex;
        align-items: center;
        justify-content: center;
        color: white;
      }
      .box:nth-child(even) {
        background-color: #3498db; /* light blue colour */
      }
      .box:nth-child(odd) {
        background-color: #34495e; /* dark blue colour */
      }
      .box:first-child {
        place-self: center;
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
      <div class="box">6</div>
      <div class="box">7</div>
      <div class="box">8</div>
      <div class="box">9</div>
    </div>
  </body>
</html>
```
