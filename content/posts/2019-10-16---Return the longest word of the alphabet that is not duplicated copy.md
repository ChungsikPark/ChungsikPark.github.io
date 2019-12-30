---
title: Return the longest word of the alphabet's length that is not duplicated
date: "Thu Oct 16 2019 10:00:00 GMT+0900"
template: "post"
draft: false
slug: "/posts/return_the_longest_word_of_the_alphabet's_length_that_is_not_duplicated/"
category: "Algorithm"
tags:
  - "JAVASCRIPT"
  - "ALGORITHM"
description: The function 'getLengthOfStr' takes str argument of type String. Return the longest word of the alphabet's length that is not duplicated.
socialImage: "../../static/media/love_is.jpeg"
---

<img src="../../static/media/love_is.jpeg">

- ### 문제

  String 형인 str 인자에서 중복되지 않은 알파벳으로 이루어진 제일 긴 단어의 길이를 반환해주세요.

  str: 텍스트</br>
  return: 중복되지 않은 알파벳 길이 (숫자 반환)

  예를 들어,

  ```
  str = "abcabcabc"
  return은 3
  => 'abc' 가 제일 길기 때문
  ```

  ```
  str = "aaaaa"
  return은 1
  => 'a' 가 제일 길기 때문
  ```

  ```
  str = "sttrg"
  return은 3
  => 'trg' 가 제일 길기 때문
  ```

  ***

- ### 나의 코드

  - Solution

  ```
  const getLengthOfStr = str => {
    let maxLength = 0;
    let arr;
    for (let i = 0; i < str.length; i++) {
      arr = [];
      for (let j = i; j < str.length; j++) {
        if (arr.indexOf(str[j]) === -1) {
          arr.push(str[j]);
          if (maxLength < arr.length) {
            maxLength = arr.length;
          }
        } else {
          break;
        }
      }
    }
    return maxLength;
  };
  ```

        console.log(getLengthOfStr("abcabcabc"));</br>
        //expected output : 3 => 'abc'가 제일 길기 때문</br>
        console.log(getLengthOfStr("aaaaa"));</br>
        //expected output : 1 => 'a'가 제일 길기 때문</br>
        console.log(getLengthOfStr("sttrg"));</br>
        //expected output : 3 => 'trg'가 제일 길기 때문</br>
        console.log(getLengthOfStr("appleahhe"));</br>
        //expected output : 5 => 'pleah'가 제일 길기 때문
