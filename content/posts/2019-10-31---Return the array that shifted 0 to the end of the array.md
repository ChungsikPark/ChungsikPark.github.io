---
title: Return the array that shifted 0 to the end of the array
date: "2019-10-31T10:00:000Z GMT+0900"
template: "post"
draft: false
slug: "/posts/return_the_array_that_shifted_0_to_the_end_of_the_array/"
category: "Algorithm"
tags:
  - "JAVASCRIPT"
  - "ALGORITHM"
description: The function 'moveZeroes' takes an arr of numbers. Return the array that shifted 0 to the end of the array.
socialImage: "../../static/media/move_zero.jpeg"
---

<img src="../../static/media/move_zero.jpeg">

- ### 문제

  주어진 숫자 배열에서, 0을 배열의 마지막쪽으로 이동시켜주세요.
  원래 있던 숫자의 순서는 바꾸지 말아주세요.

  - 새로운 배열을 생성해서는 안 됩니다.

  ```
  Input: [0,1,0,3,12]
  Output: [1,3,12,0,0]
  ```

  ***

- ### 나의 코드

  - Solution

  ```
  const moveZeroes = nums => {
    nums.sort(function(a,b) {
      if (a === 0 && b !== 0) {
        return 1;
      } else if (a !== 0 && b === 0) {
        return -1;
      } else {
        return 0;
      }
    });
    return nums;
  };
  ```

        console.log(moveZeroes([0,1,0,3,12]));</br>
        //expected output : [ 1, 3, 12, 0, 0 ]</br>
