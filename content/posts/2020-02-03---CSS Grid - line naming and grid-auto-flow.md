---
title: CSS Grid - Line naming and grid-auto-flow
date: "2020-02-03T12:00:00+09:00"
template: "post"
draft: false
slug: "/posts/css_grid_line_naming_and_grid_auto_flow/"
category: "HTML & CSS"
tags:
  - "html"
  - "css"
  - "grid"
description: Line naming and grid-auto-flow
socialImage: "../../static/media/css_grid_one.jpg"
---

<img src="../../static/media/css_grid_one.jpg">

![1 to -1 and first-line to last-line.png](https://images.velog.io/post-images/qkrcndtlr123/2e393980-4594-11ea-ac5e-0765b29c9d59/1-to-1-and-first-line-to-last-line.png)

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
        grid-column-end: -1;
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

![sexy-line to lynn-line.png](https://images.velog.io/post-images/qkrcndtlr123/3fd03ef0-4594-11ea-aedc-05a3cc075e6a/sexy-line-to-lynn-line.png)

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
        grid-template-columns: [first-line] 1fr [awsome-line] 1fr [sexy-line] 1fr [nico-line] 1fr [lynn-line] 1fr [line-line];
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
        grid-column-start: sexy-line;
        grid-column-end: lynn-line;
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
        grid-template-columns: [first-line] repeat(5, 1fr) [last-line];
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
        grid-column-start: first-line;
        grid-column-end: last-line;
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

![git-auto-flow row dense.png](https://images.velog.io/post-images/qkrcndtlr123/cada4fd0-4595-11ea-aedc-05a3cc075e6a/git-auto-flow-row-dense.png)

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
        grid-auto-flow: row dense; /* dense */
        grid-template-columns: [first-line] 1fr [awsome-line] 1fr [sexy-line] 1fr [nico-line] 1fr [lynn-line] 1fr [line-line];
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
        grid-column-start: sexy-line;
        grid-column-end: lynn-line;
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
