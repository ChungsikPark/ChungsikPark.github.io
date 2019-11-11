---
title: Which is the best algorithm for searching?
date: "Thu Nov 11 2019 12:00:00 GMT+0900"
template: "post"
draft: false
slug: "/posts/Which_is_the_best_algorithm_for_searching?/"
category: "Algorithm"
tags:
  - "JAVASCRIPT"
  - "ALGORITHM"
description: There is no such algorithm. It depends on factors like how the data is stored, how much resources can be spent, etc. Based on the required time and space complexities, an algorithm has to be selected.
socialImage: "../../static/media/binary_tree.png"
---

<img src="../../static/media/binary_tree.png">

최상의 검색 알고리즘은 따로 없다. 그것은 무슨 데이터인지 검색하려는 데이터의 양이 얼마나인지에 따라 달라진다.
대표적으로 두 가지의 타입의 알고리즘이 있다.

- ### 선형 검색 (Linear Search)

  주어진 숫자 배열에서, 0을 배열의 마지막쪽으로 이동시켜주세요.
  원래 있던 숫자의 순서는 바꾸지 말아주세요.

  - 새로운 배열을 생성해서는 안 됩니다.

  ```
  Input: [0,1,0,3,12]
  Output: [1,3,12,0,0]
  ```

  ***

- ### 이진 검색 (Binary Search)

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
