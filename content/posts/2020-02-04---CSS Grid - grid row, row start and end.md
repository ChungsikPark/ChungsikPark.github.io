---
title: CSS Grid - grid row, row start and end
date: "2020-02-04T12:00:00+09:00"
template: "post"
draft: false
slug: "/posts/css_grid_row_row_start_and_end/"
category: "HTML & CSS"
tags:
  - "html"
  - "css"
  - "grid"
description: grid-row, grid-row-start, grid-row-end
socialImage: "../../static/media/css_grid_one.jpg"
---

<img src="../../static/media/css_grid_one.jpg">

![grid row 2 to 5.png](https://images.velog.io/post-images/qkrcndtlr123/843cf4e0-45a1-11ea-b334-31811bbb8b80/grid-row-2-to-5.png)

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
        grid-row-start: 2;
        grid-row-end: 5;
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

![grid row 1 to 5.png](https://images.velog.io/post-images/qkrcndtlr123/8ce8f530-45a1-11ea-92d8-ed677f1568bc/grid-row-1-to-5.png)

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
        grid-row: 1 / 5;
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

![row span 3 column span 2.png](https://images.velog.io/post-images/qkrcndtlr123/95a79320-45a1-11ea-906f-37323b30885d/row-span-3-column-span-2.png)

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
        grid-row: span 3;
        grid-column: span 2;
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
