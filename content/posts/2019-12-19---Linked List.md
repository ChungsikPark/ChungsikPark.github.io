---
title: Linked List
date: "2019-12-19T12:00:00+09:00"
template: "post"
draft: false
slug: "/posts/linked_list/"
category: "Data Structure"
tags:
  - "Data Structure"
description: Linked List
socialImage: "../../static/media/linked_list.jpg"
---

<img src="../../static/media/linked_list.jpg">

## 연결 리스트는 무엇인가요?

연결 리스트는 순서가 지정된 데이터 요소의 모음이다. 연결 리스트에서는 데이터 요소는 노드로 표시합니다. 각 노드는 데이터와 다음 노드에 대한 포인터로 구성되어 있습니다.

## 연결 리스트가 가지는 속성:

- 연속된 노드는 포인터로 연결되고, 마지막 노드는 null을 가리킵니다.
- 리스트의 첫 번째 노드를 가리키는 헤드 포인터가 존재합니다.
- 연결 리스트는 프로그램 실행중에 크기가 커지거나 줄어들 수 있습니다.
- 연결 리스트는 필요한 만큼 만들 수 있고 리스트가 커짐에 따라 메모리를 할당합니다. 이 말인 즉슨, 데이터 요소의 수의 상한을 미리 알고 있어야 한다는 것입니다. 일반적으로 할당 메모리는 사용량에 관계없이 상한과 같습니다.

## 배열과 비교하기

- 배열과 달리 데이터 요소는 연속 된 위치에 저장되지 않습니다. 데이터를 연속적으로 메모리에 저장하는 배열과 차이점이 있습니다. 그래서 연결 리스트는 전체 데이터 구조를 재구성하지 않고도 리스트에서 노드를 쉽게 삽입 또는 제거할 수 있습니다.
- 일반적으로 배열보다 연결 리스트가 더 많은 메모리를 차지하게 됩니다. 배열은 단순 데이터 저장인데 비해, 연결 리스트는 포인터가 사용하는 스토리지를 위한 각각의 객체 생성이 이루어져야 하기 때문입니다.
- 인덱스를 가지고 있는 배열과 달리, 연결 리스트는 현재 위치의 이전 및 다음 위치를 기억하고 있습니다. 그러므로 각 데이터 요소에 대한 임의 접근은 불가능하고, 첫 번째 노드부터 순차적으로 접근해야 합니다. 따라서 데이터 접근 속도가 떨어집니다.

## 연결 리스트의 종류

연결 리스트의 종류에는 몇 가지 유형이 있습니다. 대표적인 것들로 단일, 이중, 원형 연결 리스트가 있습니다.

#### 단일 연결 리스트

단일 연결 리스트란 단일 방향(포인터)을 가진 리스트를 말합니다. 포인터를 이용해 다음 순서의 노드를 가리켜주고, 이를 통해 머리부터 끝까지 탐색을 할 수 있습니다.
![singly linked list.png](https://images.velog.io/post-images/qkrcndtlr123/f0fe2df0-1ccb-11ea-a3f0-67eb27cac529/singly-linked-list.png)

#### 이중 연결 리스트

이중 연결 리스트란 이중 방향(포인터)를 가진 리스트를 말합니다. 이 전의 단일 연결 리스트는 특정 방향의 포인터 1개였지만 이중 연결 리스트는 이전 노드, 다음 노드를 둘다 가리키는 포인터를 가지고 있습니다. 그래서 양쪽으로 탐색이 가능하다는 장점이 있습니다.
![doubly linked list.png](https://images.velog.io/post-images/qkrcndtlr123/004a8010-1ccc-11ea-bf27-c786d621cb8c/doubly-linked-list.png)

#### 원형 연결 리스트

원형 연결 리스트는 이 전에 해왔던 단일 연결 리스트나 이중 연결 리스트에서 끝을 처음과 연결된 리스트를 말합니다. 원형 리스트(단일 연결 리스트로 표현)는 모든 포인터가 다음 노드로 연결되어 있습니다. 즉 다시 마지막에서 첫번째로 이동하지 않아도 다음 노드가 첫번째 노드를 가리킵니다.
![circular linked list.png](https://images.velog.io/post-images/qkrcndtlr123/0a73d190-1ccc-11ea-bf27-c786d621cb8c/circular-linked-list.png)

## 연결 리스트 구현하기

```js
class Node {
  constructor(value, prev, next) {
    this.value = value;
    this.next = next || null;
    this.prev = prev || null;
  }
}
```

#### 데이터 삽입하기

![apend singly linked list.png](https://images.velog.io/post-images/qkrcndtlr123/fc977840-1ccd-11ea-8840-dd38c1084347/apend-singly-linked-list.png)

```js
class LinkedList {
  constructor() {
    this.head = this.tail = null;
  }

  // 꼬리 뒤 쪽에 데이터 추가하기
  append(value) {
    // 빈 리스트일 때
    if (!this.tail) {
      this.head = this.tail = new Node(value);
    }
    // 리스트에 노드가 하나 이상일 때
    else {
      let oldTail = this.tail;
      this.tail = new Node(value);
      oldTail.next = this.tail;
      this.tail.prev = oldTail;
    }
  }

  // 헤드 앞 쪽에 데이터 추가하기
  prepend(value) {
    // 빈 리스트일 때
    if (!this.head) {
      this.head = this.tail = new Node(value);
    }
    // 리스트에 노드가 하나 이상일 때
    else {
      let oldHead = this.head;
      this.head = new Node(value);
      oldHead.prev = this.head;
      this.head.next = oldHead;
    }
  }
}
```

#### 데이터 삭제하기

![delete singly linked list.png](https://images.velog.io/post-images/qkrcndtlr123/a49c9f70-1cce-11ea-a6b9-ef2635374665/delete-singly-linked-list.png)

```js
class LinkedList {
  constructor() {
    this.head = this.tail = null;
  }

  deleteHead() {
    // 빈 리스트일 때
    if (!this.head) {
      return null;
    }
    // 리스트에 노드가 하나 이상일 때
    else {
      let removedHead = this.head;
      // 리스트에 노드가 하나 밖에 없을 때
      if (this.head === this.tail) {
        this.head = this.tail = null;
      }
      // 리스트에 노드가 하나보다 많을 때
      else {
        this.head = this.head.next;
        this.head.prev = null;
      }
      return removedHead.value;
    }
  }

  deleteTail() {
    // 빈 리스트일 때
    if (!this.tail) {
      return null;
    }
    // 리스트에 노드가 하나 이상일 때
    else {
      let removedTail = this.tail;
      // 리스트에 노드가 하나 밖에 없을 때
      if (this.head === this.tail) {
        this.tail = this.head = null;
      }
      // 리스트에 노드가 하나보다 많을 때
      else {
        this.tail = this.tail.prev;
        this.tail.next = null;
      }
      return removedTail.value;
    }
  }
}
```

#### 데이터 검색

```js
class LinkedList {
  constructor() {
    this.head = this.tail = null;
  }

  search(value) {
    let currentNode = this.head;

    while (currentNode) {
      if (currentNode.value === value) {
        return currentNode;
      }
      currentNode = currentNode.next;
    }

    return null;
  }
}
```
