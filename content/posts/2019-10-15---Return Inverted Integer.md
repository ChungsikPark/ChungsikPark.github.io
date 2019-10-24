---
title: Return Inverted Integer
date: "Thu Oct 15 2019 12:00:00 GMT+0900"
template: "post"
draft: false
slug: "/posts/return_inverted_integer/"
category: "Code Kata"
tags:
  - "javascript"
  - "algorithm"
description: The function 'reverse' takes an integer number. Invert the number and return it.
socialImage: "/media/number_block.jpeg"
---

<img src="../../static/media/number_block.jpeg">

* ### 문제

  reverse 함수에 정수인 숫자를 인자로 받습니다.
  그 숫자를 뒤집어서 return해주세요.

  x: 숫자
  return: 뒤집어진 숫자를 반환!

  예를 들어,

  ```
  x: 1234
  return: 4321
  ```

  ```
  x: -1234
  return: -4321
  ```

  ```
  x: 1230
  return: 321
  ```

  ***

* ### 코드

  + Solution 1
  ```
  const reverse = x => {
    if (x < 0) {
      return -reverse(-x);
    }
    let strX = String(x);
    let strXArr = strX.split("");
    let revStrXArr = strXArr.reverse();
    let revX = revStrXArr.join("");
    return Number(revX);
  };
  ```

  + Solution 2
  ```
  const reverse = x => {
    let nX = Math.abs(x);
    let strNX = String(nX);
    let strNXArr = strNX.split("");
    let revStrNXArr = strNXArr.reverse();
    let revNX = revStrNXArr.join("");
    let result = Number(revNX) * Math.sign(x);
    return result;
  };
  ```

  + Solution 3
  ```
  const reverse = x => {
    return Number(Math.abs(x).toString().split("").reverse().join("")) * Math.sign(x);
  };
  ```

  + Solution 4
  ```
  const reverse = x => {
    return Number(Array.from(Math.abs(x).toString()).reverse().join("")) * Math.sign(x);
  };
  ```

  console.log(reverse(1234));     //expected output :  4321</br>
  console.log(reverse(1230));     //expected output :   321</br>
  console.log(reverse(12300));    //expected output :   321</br>
  console.log(reverse(0));        //expected output :     0</br>
  console.log(reverse(-1234));    //expected output : -4321