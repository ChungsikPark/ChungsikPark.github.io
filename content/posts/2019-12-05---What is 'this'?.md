---
title: What is 'this'?
date: "2019-12-05T12:00:00+09:00"
template: "post"
draft: false
slug: "/posts/this/"
category: "Javascript"
tags:
  - "javascript"
description: What is 'this'? (with call, apply, bind, arrow function)
socialImage: "../../static/media/this.jpg"
---

<img src="../../static/media/this.jpg">

## what is 'this' ?

&nbsp;&nbsp;this는 본인이 속해있는 객체를 참고합니다. 이 말인 즉슨, 어디서 어떻게 사용되느냐에 따라서 다른 값을 가진다는 겁니다. (어디서 호출했는지가 중요!)

## 'this' in Global Scop !

&nbsp;&nbsp;아무 것도 속하지 않은 범위에서의 this는 전역 객체를 참고합니다.웹 브라우저에서는 window가 전역 객체입니다.

```js
name = "Chungsik";

console.log(this); // Window;
console.log(name); // Chungsik
console.log(this.name); // Chungsik
console.log(window.name); // Chungsik
```

## 'this' inside a method (in object) !

&nbsp;&nbsp;함수를 어떤 객체의 메소드로 호출했을 때, this의 값은 그 객체를 사용합니다.

- normal object

```js
let user = {
  name: "Chungsik",
  greetUser: function() {
    console.log(`Hello ${this.name}`)
  }
};

user.greetUser() = Hello Chungsik
```

- nested object

```js
let user = {
  name: "Chungsik",
  computer: {
    greetUser: function() {
      console.log(`Hello ${this.name}`) // this가 undefined
    }
  }
};

user.computer.greetUser() = Hello undefined // use call, apply, bind... to solve this problem
```

## 'this' inside a function !

&nbsp;&nbsp;함수 내부에서는 함수를 호출한 방법에 따라서 달라집니다.

- 엄격 모드가 아닐 때 (default mode)

```js
function fnc() {
  return this;
}
fnc(); // Window;
```

- 엄격 모드일 때 (strict mode)

```js
function fnc() {
  "use strict";
  return this;
}
fnc(); // undefined;
window.fnc(); // window;
```

- call, apply, bind 함수 메소드를 사용할 때 (**call, apply, bind 사용법**)
  이 때 this의 값은 call, apply, bind 메소드의 인수로 사용되는 객체를 사용합니다.

```js
let user = {
  name: "Chungsik",
  computer: {
    greetUser: function(team, partner) {
      console.log(
        `Hello ${this.name}, your team name is ${team} with ${partner}`
      );
    }
  }
};
// Call & Apply need to invoke immediately
user.computer.greetUser.call(user, "Alpha", "Eunwoo");
// Hello Chungsik, your team name is Alpha with Eunwoo
// call은 단일 인자를 전달합니다.
user.computer.greetUser.apply(user, ["Bravo", "Yeri"]);
// Hello Chungsik, your team name is Bravo with Yeri
// apply는 배열 인자를 전달합니다.
```

```js
let user = {
  name: "Chungsik",
  computer: {
    greetUser: function(team, partner) {
      console.log(`Hello ${this.name}, your team is ${team} with ${partner}`);
    }
  }
};
// Bind returns a copy of the function which can be invoked later
let greet = user.computer.greetUser.bind(user);
greet("Charlie", "Jihoon"); // Hello Chungsik, your team name is Charlie with Jihoon
```

## 'this' with ES6 arrow function !

&nbsp;&nbsp;arrow function은 자신을 포함하는 외부 scope에서 this를 계승 받습니다.

```js
let user = {
  name: "Chungsik",
  computer: {
    greetUser: (team, partner) => {
      console.log(`Hello ${this.name}, your team is ${team} with ${partner}`);
    }
  }
};
user.computer.greetUser("Delta", "Doori"); // Hello , your team is Delta with Doori
// 위와 같이 하면 객체의 this는 바인딩하지 않고 전역 객체가 바인딩 됩니다.
// 즉, 객체의 메소드를 정의할 때는 사용하면 안됩니다.
```

&nbsp;&nbsp;함수 내부에서 this는 window 객체입니다.

```js
// arrow function 적용 전
function Greeting(greet) {
  this.greet = greet;
}
Greeting.prototype.nameArray = function(arr) {
  console.log(this.greet); // 여기서 this.greet는 Hello 입니다.
  return arr.map(function(x) {
    return this.greet + " " + x; // 하지만 여기서 this.greet는 undefined 입니다.
  });
};
var gre = new Greeting("Hello");
console.log(gre.nameArray(["Chungsik", "Yeri"]));
// ["undefined Chungsik","undefined Yeri"]
```

&nbsp;&nbsp;함수 내부더라도 arrow function을 쓰면 this 상위 context(함수가 속해있는 객체)를 가리킵니다.

```js
// arrow function 적용 후
function Greeting(greet) {
  this.greet = greet;
}
Greeting.prototype.nameArray = function(arr) {
  return arr.map(x => `${this.greet}  ${x}`); // 여기서 this.greet는 Hello 입니다.
};
const gre = new Greeting("Hello");
console.log(gre.nameArray(["Chungsik", "Yeri"]));
// ["Hello Chungsik","Hello Yeri"]
```
