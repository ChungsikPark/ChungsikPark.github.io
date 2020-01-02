---
title: Callback Function
date: "2019-11-21T12:00:00+09:00"
template: "post"
draft: false
slug: "/posts/callback_function/"
category: "Javascript"
tags:
  - "JAVASCRIPT"
description: Callback Function
socialImage: "../../static/media/hell.jpg"
---

<img src="../../static/media/hell.jpg">

콜백 함수는, 특정 함수에 매개변수로서 전달된 함수를 말합니다.
그리고 그 콜백 함수는 그 함수를 전달받은 함수 안에서 호출됩니다.
콜백함수를 사용하기 이전의 코드는 데이터가 준비되지 않은 상태에서 함수가 끝나기 때문에 원하는 대로 동작하지 못하지만, 콜백함수를 사용하면 필요한 데이터가 다 준비된 시점에서만 원하는 동작을 수행하도록 할 수 있습니다.

### 비유로 이해하는 콜백 함수 동작 방식

콜백 함수의 동작 방식은 일종의 식당 자리 예약과 같습니다. 일반적으로 맛집을 가면 사람이 많아 자리가 없습니다. 그래서 대기자 명단에 이름을 쓴 다음에 자리가 날 때까지 주변 식당을 돌아다니죠. 만약 식당에서 자리가 생기면 전화로 자리가 났다고 연락이 옵니다. 그 전화를 받는 시점이 여기서의 콜백 함수가 호출되는 시점과 같습니다. 손님 입장에서는 자리가 날 때까지 식당에서 기다리지 않고 근처 가게에서 잠깐 쇼핑을 할 수도 있고 아니면 다른 식당 자리를 알아볼 수도 있습니다.

자리가 났을 때만 연락이 오기 때문에 미리 가서 기다릴 필요도 없고, 직접 식당 안에 들어가서 자리가 비어 있는지 확인할 필요도 없습니다. 자리가 준비된 시점, 즉 데이터가 준비된 시점에서만 저희가 원하는 동작(자리에 앉는다, 특정 값을 출력한다 등)을 수행할 수 있습니다.

### 콜백 지옥

```js
$.get("url", function(response) {
  parseValue(response, function(id) {
    auth(id, function(result) {
      display(result, function(text) {
        console.log(text);
      });
    });
  });
});
```

코드 관점에서 콜백함수는 중첩으로 들여쓰기(nesting)가 반복되 가독성이 떨어지게 됩니다. 콜백 함수를 분리하여 콜백 지옥을 해결할 수 있습니다.

```js
function parseValueDone(id) {
  auth(id, authDone);
}
function authDone(result) {
  display(result, displayDone);
}
function displayDone(text) {
  console.log(text);
}
$.get("url", function(response) {
  parseValue(response, parseValueDone);
});
```

하지만 Promise를 사용하면 더 편하게 구현할 수 있습니다!

참고
https://joshua1988.github.io/web-development/javascript/javascript-asynchronous-operation/#%EC%BD%9C%EB%B0%B1-%EC%A7%80%EC%98%A5-callback-hell
