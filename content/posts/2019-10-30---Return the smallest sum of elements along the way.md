---
title: Return the smallest sum of elements along the way
date: "Thu Oct 30 2019 12:00:00 GMT+0900"
template: "post"
draft: false
slug: "/posts/return_the_smallest_sum_of_elements_along_the_way/"
category: "Algorithm"
tags:
  - "JAVASCRIPT"
  - "ALGORITHM"
description: The function 'minPathSum' takes m X n grid. Return the smallest sum of elements along the way.
socialImage: "../../static/media/parking_grid.jpeg"
---

<img src="../../static/media/parking_grid.jpeg">

- ### 문제

  양수로 이루어진 m x n 그리드를 인자로 드립니다.
  상단 왼쪽에서 시작하여, 하단 오른쪽까지 가는 길의 요소를 다 더했을 때,
  가장 작은 합을 찾아서 return 해주세요.

  한 지점에서 우측이나 아래로만 이동할 수 있습니다.

  ```
  Input:
  [
    [1,3,1],
    [1,5,1],
    [4,2,1]
  ]

  Output: 7

  설명: 1→3→1→1→1 의 합이 제일 작음
  ```

  ***

- ### 나의 코드

  - Solution

  ```
  const minPathSum = grid => {
    let m = grid[0].length;
    let n = grid.length;
    if (!m || !n) {
      return 0;
    }
    for (let i = 1; i < n; i++) {
      grid[i][0] += grid[i - 1][0];
    }
    for (let j = 1; j < m; j++) {
      grid[0][j] += grid[0][j - 1];
    }
    for (let i = 1; i < n; i++) {
      for (let j = 1; j < m; j++) {
        grid[i][j] = Math.min(grid[i - 1][j] + grid[i][j], grid[i][j - 1] + grid[i][j]);
      }
    }
    return grid[n - 1][m - 1];
  }
  ```

        console.log(minPathSum([[1,3,1],[1,5,1],[4,2,1]];));;</br>
        //expected output : 7</br>
