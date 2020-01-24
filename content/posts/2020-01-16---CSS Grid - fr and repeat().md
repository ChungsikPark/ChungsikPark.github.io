---
title: CSS Grid - fr and repeat()
date: "2020-01-16T12:00:00+09:00"
template: "post"
draft: false
slug: "/posts/css_grid_fr_and_repeat/"
category: "HTML & CSS"
tags:
  - "HTML"
  - "CSS"
  - "grid template columns"
  - "fr"
  - "repeat"
description: fr and repeat()
socialImage: "../../static/media/css_grid_one.jpg"
---

<img src="../../static/media/css_grid_one.jpg">

![2fr 1fr 2fr 1fr.png](https://images.velog.io/post-images/qkrcndtlr123/a2094260-3ce3-11ea-97bd-ab6a6da50eba/2fr-1fr-2fr-1fr.png)

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
        grid-template-columns: 2fr 1fr 2fr 1fr;
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

![repeat 3 1fr .png](https://images.velog.io/post-images/qkrcndtlr123/ac2484f0-3cf5-11ea-9683-993e0dc87733/repeat-3-1fr-.png)

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
        grid-template-columns: repeat(3, 1fr);
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

![repeat 5 1fr.png](https://images.velog.io/post-images/qkrcndtlr123/c77aa860-3cf5-11ea-aed7-bf7796d2fd0a/repeat-5-1fr.png)

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
        grid-template-columns: repeat(5, 1fr);
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

![repeat 3 1fr 4fr.png](https://images.velog.io/post-images/qkrcndtlr123/97888770-3cf6-11ea-ada5-7f693c0b581e/repeat-3-1fr-4fr.png)

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
        grid-template-columns: repeat(3, 1fr) 4fr;
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
