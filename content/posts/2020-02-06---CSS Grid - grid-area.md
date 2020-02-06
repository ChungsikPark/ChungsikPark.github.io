---
title: CSS Grid - grid-area
date: "2020-02-06T12:00:00+09:00"
template: "post"
draft: false
slug: "/posts/css_grid_area/"
category: "HTML & CSS"
tags:
  - "html"
  - "css"
  - "grid"
description: grid-area
socialImage: "../../static/media/css_grid_one.jpg"
---

<img src="../../static/media/css_grid_one.jpg">

![grid-area 2:1:4:-1.png](https://images.velog.io/post-images/qkrcndtlr123/b1aed390-4811-11ea-ade4-5d87fd8e5cb7/grid-area-214-1.png)

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
        grid-area: 2 / 1 / 4 / -1;
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

![grid-area 2:span 3:4:-1.png](https://images.velog.io/post-images/qkrcndtlr123/628f5630-4817-11ea-b996-31c898d07854/grid-area-2span-34-1.png)

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
        grid-area: 2 / span 3 / 4 / -1;
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

![grid-area span 4:span 4.png](https://images.velog.io/post-images/qkrcndtlr123/afd4ada0-4817-11ea-808a-fd2499a972e2/grid-area-span-4span-4.png)

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
        grid-area: span 4 / span 4;
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
