---
title: Return a common prefix
date: "2019-10-18T12:00:00+09:00"
template: "post"
draft: false
slug: "/posts/return_a_common_prefix/"
category: "Algorithm"
tags:
  - "JAVASCRIPT"
  - "ALGORITHM"
description: The function 'getPrefix' takes strs, an array of words. Return a common prefix.
socialImage: "../../static/media/its_simple.jpeg"
---

<img src="../../static/media/its_simple.jpeg">

- ### 문제

  strs은 단어가 담긴 배열입니다. 공통된 시작 단어(prefix)를 반환해주세요.

  예를 들어,

  ```js
  strs = ["start", "stair", "step"]
  return은 "st"
  ```

  ```js
  strs = ["start", "wework", "today"]
  return은 ""
  ```

  ***

- ### 나의 코드

  - Solution

  ```js
  const getPrefix = strs => {
    let commonPrefix = "";
    if (strs.length > 0) {
      commonPrefix = strs[0];
      for (let i = 1; i < strs.length; i++) {
        for (let j = 0; j < commonPrefix.length; j++) {
          if (strs[i][j] !== commonPrefix[j]) {
            commonPrefix = commonPrefix.slice(0, j);
            break;
          }
        }
      }
    }
    return commonPrefix;
  };
  ```

        console.log(getPrefix(["start", "wework", "today"]));</br>
        //expected output : ""</br>
        console.log(getPrefix(["start", "stair", "step"]));</br>
        //expected output : "st"</br>
        console.log(getPrefix(["start", "stair", "step", "strite", "store", "sacrifice"]));</br>
        //expected output : "s"</br>
