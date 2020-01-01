---
title: Function Object
date: "2019-11-14T12:00:00+09:00"
template: "post"
draft: false
slug: "/posts/function_object/"
category: "Javascript"
tags:
  - "JAVASCRIPT"
description: Function is Object. (Subroutine, Clousre, Parser)
socialImage: "../../static/media/function_object.jpg"
---

<img src="../../static/media/function_object.jpg">

함수는 객체다.

함수 객체란 Subroutine으로 수행될 수 있는 객체를 말한다.동작을 나타내는 실행 코드와 상태를 포함하고 있으며 객체 지향의 생성자 역할도 할 수 있다.

---

### 서브루틴(Subroutine)

Subroutine : 먼저 매크로를 알아야 한다. 매크로는 반복되어 자주 사용되는 명령어를 묶어서 하나의 이름으로 만드는 것을 말한다. 매크로를 사용하게 되면, 컴파일 시에 매크로 사용 부분이 매크로의 원문으로 모두 교체 되기 때문에 소스 코드의 크기가 커진다. 즉 그만큼 메모리의 점유율이 높아지는 단점이 있다.

서브루틴의 매크로의 단점을 극복하여 메모리 사용을 최대한 줄이도록 고안된 것이다. 메인루틴과 대비되는 개념으로, 혼자 쓰이지 않고 메인루틴에 붙어 보조하는 역할을 한다. 반복되는 특정한 기능을 모아 놓아 이름을 붙여 놓았다는 것은 매크로와 같지만, 프로그램의 흐름이 메인루틴에 있지 않고 별도의 공간에 한 번만 생긴다는 것이 다르다.하나의 서브루틴은 한 번 메모리에 적재된 후에, 필요시마다 해당 메모리를 호출하여 기능을 실행한다. 즉, 한번의 메모리를 적재 후 여러 번의 사용을 통해 메모리 사용량을 줄인다.

함수는 일반 객체의 확장이다. 함수로 작동하기 위한 추가적인 기능을 가진다.
함수 객체는 다음과 같은 데이터들을 내부에 추가로 저장한다.

- 클로저로 묶이는 Lexical Environment
- 함수 코드
- 함수 종류: "normal", "classConstructor", "generator", "async"
- 생성자 종류: "base", "derived"
- this 참조 형태
- strict mode 여부
- super 참조
- 기타 등등

---

### 클로저(Closure)

```js
function init() {
  var name = "Mozilla"; // name은 init에 의해 생성된 지역 변수이다.
  function displayName() {
    // displayName() 은 내부 함수이며, 클로저다.
    alert(name); // 부모 함수에서 선언된 변수를 사용한다.
  }
  displayName();
}
init();
```

위 코드를 실행하면 displayName() 함수 내의 alert()문이 부모 함수에서 정의한 변수 name의 값을 성공적으로 출력한다. 이 예시를 통해 함수가 중첩된 상황에서 parser가 어떻게 변수를 처리하는지 알 수 있다. 이는 어휘적 범위 지정(lexical scoping)의 한 예이다. 여기서 "lexical"이란, 어휘적 범위 지정(lexical scoping) 과정에서 변수가 어디에서 사용 가능한지 알기 위해 그 변수가 소스코드 내 어디에서 선언되었는지 고려한다는 것을 의미한다. 단어 "lexical"은 이런 사실을 나타낸다. 중첩된 함수는 외부 범위(scope)에서 선언한 변수에도 접근할 수 있다.

---

#### 파서(Parser)

파서(parser)란 Compiler의 일부로서 원시 프로그램의 명령문이나 온라인 명령문, HTML 문서 등에서 Markup Tag 등을 입력으로 받아들여서 구문을 해석 할 수 있는 단위로 여러 부분으로 분할해 주는 역할을 한다. 즉, Compiler나 Interpreter에서 원시 프로그램을 읽어 들여, 그 문장의 구조를 알아내는 구문 분석(parsing)을 행하는 프로그램 이다.

대표적 파싱 모델은 DOM과 SAX가 있다.DOM 과 SAX는 API로서, XML문서를 구조화시켜서 그 문서를 원하는 방법으로 활용할 수 있게 해준다. DOM이나 SAX는 XML 문서에 있는 Data를 효과적으로 다루기 위해서 필요하다. 특정한 node에 있는 Data만 가져오고, 특정한 Attribute의 값을 수정 할 때, DOM과 SAX를 이용해서 이런 작업 들을 method 몇 개를 활용해서 쉽게 행할 수 있다. DOM 과 SAX는 XML문서에 접근해서 필요한 Data를 가져오거나 수정하는 API인 것이다.

XML파서는 애플리케이션에게 어떤 방법으로든지 파싱한 결과를 넘겨줘야 하는데, 보통은 트리(Tree)기반의 파서와 이벤트(Event)기반의 파서 두 가지로 분류된다. 그리고 양쪽 모두 전 세계적 표준이 제안되어 있는 상태이다. 현재 W3C에서는 DOM이란 스펙을 제안한 상태로 파서가 트리 기반으로 작동할 때 제공되어야 할 트리의 인터페이스를 규정하고 있고, W3C의 표준은 아니나 이벤트 기반의 파서와 작업할 수 있는 업계 표준으로 SAX라는 표준이 제안되었다. DOM과 SAX의 차이점은 문서 접근 방식의 차이에 있다. DOM 파싱 모델은 트리를 통해 여러 번 순회할 필요가 있거나, 트리 구조를 수정하기를 원하거나, XML문서를 임의로 접근할 필요가 있을 때, 순차적 접근을 제공하는 SAX 모델보다 유용하다.

![dom sax.png](https://images.velog.io/post-images/qkrcndtlr123/e2b6f320-10bf-11ea-a365-21635b9c5b79/dom-sax.png)

---

```js
function makeFunc() {
  var name = "Mozilla";
  function displayName() {
    alert(name);
  }
  return displayName;
}

var myFunc = makeFunc();
//myFunc변수에 displayName을 리턴함
myFunc();
//리턴된 displayName 함수를 실행(name 변수에 접근)
```

이전 코드와 차이는 displayName()함수가 실행되기 전에 외부함수인 makeFunc()로부터 리턴되어 myFunc 변수에 저장된다는 것이다.

자바스크립트는 함수를 리턴하고, 리턴하는 함수는 클로저를 형성한다. myFunc은 makeFunc이 실행될 때 생성된 displayName 함수의 인스턴스에 대한 레퍼런스다. 이런 이유로 myFunc가 호출될 때 변수 name은 사용할 수 있는 상태로 남게 되고 "Mozilla" 가 alert에 전달된다.

```js
function makeAdder(x) {
  var y = 1;
  return function(z) {
    y = 100;
    return x + y + z;
  };
}

var add5 = makeAdder(5);
var add10 = makeAdder(10);
//클로저에 x와 y의 환경이 저장됨

console.log(add5(2)); // 107 (x:5 + y:100 + z:2)
console.log(add10(2)); // 112 (x:10 + y:100 + z:2)
//함수 실행 시 클로저에 저장된 x, y값에 접근하여 값을 계산
```

이 예제에서 단일 인자 x를 받아서 새 함수를 반환하는 함수 makeAdder(x)를 정의했다. 반환되는 함수는 단일 인자 z를 받아서 x와 y와 z의 합을 반환한다.

본질적으로 makeAdder는 함수를 만들어내는 공장이다. 이는 makeAdder함수가 특정한 값을 인자로 가질 수 있는 함수들을 리턴한다는 것을 의미한다. 위의 예제에서 add5, add10 두 개의 새로운 함수들을 만들기 위해 makeAdder함수 공장을 사용했다. 하나는 매개변수 x에 5를 더하고 다른 하나는 매개변수 x에 10을 더한다.

add5와 add10은 둘 다 클로저이다. 이들은 같은 함수 본문 정의를 공유하지만 서로 다른 맥락(어휘)적 환경을 저장한다. 함수 실행 시 add5의 맥락적 환경에서 클로저 내부의 x는 5 이지만 add10의 맥락적 환경에서 x는 10이다. 또한 리턴되는 함수에서 초기값이 1로 할당된 y에 접근하여 y값을 100으로 변경한 것을 볼 수 있다. (물론 x값도 동일하게 변경 가능하다.) 이는 클로저가 리턴된 후에도 외부함수의 변수들에 접근 가능하다는 것을 보여주는 포인트이며 클로저에 단순히 값 형태로 전달되는 것이 아니라는 것을 의미한다.

---

### 클로저를 이용한 프라이빗 메소드와 모듈 패턴

#### 프라이빗 메소드

```js
var myModule = (function() {
  "use strict";

  var _privateProperty = "Hello World";

  function _privateMethod() {
    console.log(_privateProperty);
  }

  return {
    publicMethod: function() {
      _privateMethod();
    }
  };
})();

myModule.publicMethod(); // outputs 'Hello World'
console.log(myModule._privateProperty); // is undefined protected by the module closure
myModule._privateMethod(); // is TypeError protected by the module closure
```

#### 모듈 패턴

```js
var myModule = (function() {
  "use strict";

  var _privateProperty = "Hello World";
  var publicProperty = "I am a public property";

  function _privateMethod() {
    console.log(_privateProperty);
  }

  function publicMethod() {
    _privateMethod();
  }

  return {
    publicMethod: publicMethod,
    publicProperty: publicProperty
  };
})();

myModule.publicMethod(); // outputs 'Hello World'
console.log(myModule.publicProperty); // outputs 'I am a public property'
console.log(myModule._privateProperty); // is undefined protected by the module closure
myModule._privateMethod(); // is TypeError protected by the module closure
```

JavaScript에는 기본적으로 비공개 키워드가 없지만, 클로저를 사용하여 비공개 메소드와 비공개 상태를 만들 수 있다.

---

### 클로저 사용하기

특정 작업에 클로저가 필요하지 않는데 다른 함수 내에서 함수를 불필요하게 작성하는 것은 현명하지 않다. 이것은 처리 속도와 메모리 소비 측면에서 스크립트 성능에 부정적인 영향을 미칠 것이다.

```js
// 예시 코드
function MyObject(name, message) {
  this.name = name.toString();
  this.message = message.toString();
  this.getName = function() {
    return this.name;
  };

  this.getMessage = function() {
    return this.message;
  };
}
```

앞의 코드는 클로저의 이점을 이용하지 않음으로 다음과 같이 다시 쓸 수 있다.

```js
function MyObject(name, message) {
  this.name = name.toString();
  this.message = message.toString();
}
MyObject.prototype = {
  getName: function() {
    return this.name;
  },
  getMessage: function() {
    return this.message;
  }
};
```

그러나 프로토타입을 다시 정의하는 것은 권장되지 않음으로 기존 프로토타입에 추가하는 다음 예제가 더 좋다.

```js
function MyObject(name, message) {
  this.name = name.toString();
  this.message = message.toString();
}
MyObject.prototype.getName = function() {
  return this.name;
};
MyObject.prototype.getMessage = function() {
  return this.message;
};
```

위의 코드는 같은 결과를 가진 더 깨끗한 방법으로 작성할 수도 있다.

```js
function MyObject(name, message) {
  this.name = name.toString();
  this.message = message.toString();
}
(function() {
  this.getName = function() {
    return this.name;
  };
  this.getMessage = function() {
    return this.message;
  };
}.call(MyObject.prototype));
```

상속된 프로토타입은 모든 객체에서 공유될 수 있으며 메소드 정의는 모든 객체 생성시 발생할 필요가 없다.

### 함수가 일급 객체인 것이 중요한 이유

일급 객체(first class object)라는 것은 특정 언어에서 객체(object)를 일급 시민으로써 취급한다는 뜻이다. 일반적으로 일급 시민의 조건은 세 가지가 있다. 첫째, 변수(variable)에 담을 수 있다. 둘째, 인자(parameter)로 전달할 수 있다. 셋째, 반환값(return value)으로 전달할 수 있다.

고차 함수(high order function)가 가능하다. JavaScript의 each, filter, map, sort 등의 함수들이 얼마나 편리한지는 잘 알고 있을 것이다. 인자로 목적에 맞는 함수를 하나 넘겨주면 아주 쉽게 처리가 된다.

일급 객체가 Closure와 만나면 또 하나의 장점이 생긴다. 자바스크립트의 함수는 생성될 때 Lexical Environment를 기억하게 되는데, 함수를 주고받게 되면 이 Lexical Environment도 함께 전달된다. 이것을 이용해서 커링(currying)과 메모이제이션(memoization)이 가능하다.

참고
https://sinun.tistory.com/94
https://redthing.tistory.com/entry/%ED%8C%8C%EC%84%9C%EB%9E%80Parser
https://coryrylan.com/blog/javascript-module-pattern-basics
https://developer.mozilla.org/ko/docs/Web/JavaScript/Guide/Closures
https://bestalign.github.io/2015/10/18/first-class-object
