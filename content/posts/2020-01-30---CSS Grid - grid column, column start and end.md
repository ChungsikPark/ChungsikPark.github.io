---
title: CSS Grid - grid column, column start and end
date: "2020-01-30T12:00:00+09:00"
template: "post"
draft: false
slug: "/posts/css_grid_grid_column_column_start_and_end/"
category: "HTML & CSS"
tags:
  - "html"
  - "css"
  - "grid"
description: grid-column, grid-column-start, grid-column-end
socialImage: "../../static/media/css_grid_one.jpg"
---

<img src="../../static/media/css_grid_one.jpg">

![grid column base.png](https://images.velog.io/post-images/qkrcndtlr123/0be582e0-4340-11ea-a592-8f3ffaf91139/grid-column-base.png)

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
      <div class="box">10</div>
      <div class="box">11</div>
      <div class="box">12</div>
      <div class="box">13</div>
      <div class="box">14</div>
      <div class="box">15</div>
      <div class="box">16</div>
      <div class="box">17</div>
      <div class="box">18</div>
      <div class="box">19</div>
      <div class="box">20</div>
      <div class="box">21</div>
      <div class="box">22</div>
      <div class="box">23</div>
      <div class="box">24</div>
      <div class="box">25</div>
      <div class="box">26</div>
      <div class="box">27</div>
      <div class="box">28</div>
      <div class="box">29</div>
      <div class="box">30</div>
    </div>
  </body>
</html>
```

![grid column set.png](https://images.velog.io/post-images/qkrcndtlr123/192c19f0-4340-11ea-87c0-6d5529729683/grid-column-set.png)

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
        grid-column: 1 / 3;
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
      <div class="box">10</div>
      <div class="box">11</div>
      <div class="box">12</div>
      <div class="box">13</div>
      <div class="box">14</div>
      <div class="box">15</div>
      <div class="box">16</div>
      <div class="box">17</div>
      <div class="box">18</div>
      <div class="box">19</div>
      <div class="box">20</div>
      <div class="box">21</div>
      <div class="box">22</div>
      <div class="box">23</div>
      <div class="box">24</div>
      <div class="box">25</div>
      <div class="box">26</div>
      <div class="box">27</div>
      <div class="box">28</div>
      <div class="box">29</div>
      <div class="box">30</div>
    </div>
  </body>
</html>
```

![grid column start end.png](https://images.velog.io/post-images/qkrcndtlr123/984925c0-4340-11ea-9a51-e5e168f75dd9/grid-column-start-end.png)

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
        grid-column-start: 1;
        grid-column-end: 5;
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
      <div class="box">10</div>
      <div class="box">11</div>
      <div class="box">12</div>
      <div class="box">13</div>
      <div class="box">14</div>
      <div class="box">15</div>
      <div class="box">16</div>
      <div class="box">17</div>
      <div class="box">18</div>
      <div class="box">19</div>
      <div class="box">20</div>
      <div class="box">21</div>
      <div class="box">22</div>
      <div class="box">23</div>
      <div class="box">24</div>
      <div class="box">25</div>
      <div class="box">26</div>
      <div class="box">27</div>
      <div class="box">28</div>
      <div class="box">29</div>
      <div class="box">30</div>
    </div>
  </body>
</html>
```
