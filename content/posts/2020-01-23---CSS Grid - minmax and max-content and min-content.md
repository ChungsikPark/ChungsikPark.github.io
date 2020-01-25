---
title: CSS Grid - minmax and max-content and min-content
date: "2020-01-23T12:00:00+09:00"
template: "post"
draft: false
slug: "/posts/css_grid_minmax_and_max_content_and_min_content/"
category: "HTML & CSS"
tags:
  - "HTML"
  - "CSS"
  - "grid template columns"
  - "minmax"
  - "max-content"
  - "min-content"
description: minmax, max-content, min-content
socialImage: "../../static/media/css_grid_one.jpg"
---

<img src="../../static/media/css_grid_one.jpg">

[![minmax.png](https://images.velog.io/post-images/qkrcndtlr123/d9f14da0-3de0-11ea-8879-173a6ea3ad5a/minmax.png)](https://youtu.be/ktwZ98SAExQ)

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
        grid-template-columns: minmax(400px, 2fr) repeat(3, 1fr);
      }
      .first {
        background-color: #f1c40f; /* yellow colour */
      }
      .second {
        background-color: #27ae60; /* green colour */
      }
      .third {
        background-color: #3498db; /* blue colour */
      }
      .fourth {
        background-color: #d35400; /* red colour */
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

![max content.png](https://images.velog.io/post-images/qkrcndtlr123/750b8af0-3de4-11ea-82ac-1fb78e130338/max-content.png)

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
        grid-template-columns: max-content repeat(3, 1fr);
      }
      .first {
        background-color: #f1c40f; /* yellow colour */
      }
      .second {
        background-color: #27ae60; /* green colour */
      }
      .third {
        background-color: #3498db; /* blue colour */
      }
      .fourth {
        background-color: #d35400; /* red colour */
      }
    </style>
  </head>
  <body>
    <div class="father">
      <div class="first">
        CSS Grid Layout excels at dividing a page into major regions or defining
        the relationship in terms of size, position, and layer, between parts of
        a control built from HTML primitives.
      </div>
      <div class="second"></div>
      <div class="third"></div>
      <div class="fourth"></div>
    </div>
  </body>
</html>
```

![min content.png](https://images.velog.io/post-images/qkrcndtlr123/1c5f8a90-3de5-11ea-978a-ed7ab7073e79/min-content.png)

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
        grid-gap: 5px;
        grid-template-columns: min-content repeat(3, 1fr);
      }
      .first {
        background-color: #f1c40f; /* yellow colour */
      }
      .second {
        background-color: #27ae60; /* green colour */
      }
      .third {
        background-color: #3498db; /* blue colour */
      }
      .fourth {
        background-color: #d35400; /* red colour */
      }
    </style>
  </head>
  <body>
    <div class="father">
      <div class="first">
        CSS Grid Layout excels at dividing a page into major regions or defining
        the relationship in terms of size, position, and layer, between parts of
        a control built from HTML primitives.
      </div>
      <div class="second"></div>
      <div class="third"></div>
      <div class="fourth"></div>
    </div>
  </body>
</html>
```
