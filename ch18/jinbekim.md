## 함수와 일급 객체

### 일급 객체

1. 런타임에 생성할 수 있다.
2. 변수나 자료구조에 저장할 수 있다.
3. 함수의 매개변수에 전달할 수 있다.
4. 함수의 반환값으로 사용할 수 있다.

> -> 자바스크립트에서 함수는 일급 객체이다.
> -> 함수형 프로그래밍을 가능케 한다.

```js
const increase = function (num) {
  return ++num
}

function makeCounter(predicate) {
  let num = 0
  return function () {
    num = predicate(num)
    return num
  }
}
```

### 함수 객체의 프로퍼티

- 함수는 객체다. 함수도 프로퍼티를 가진다.
- arguments: 함수를 호출할 때 전달된 인수들이 **\*유사배열(iterable)** 형태로 저장된다.

\*유사배열(iterable): 배열처럼 인덱스로 접근할 수 있고 length 프로퍼티를 가지고 있다. 하지만 배열의 메서드를 사용할 수 없다. (Symbol.iterator 메서드를 가지고 있기 때문에 for...of 문으로 순회할 수 있다.)

- `length`: 함수에 정의된 매개변수(parameter)의 개수를 나타낸다.
- `name`: 함수의 이름을 나타낸다. 익명 함수의 경우 빈 문자열을 반환한다(~ES5).
- `__proto__`: [[prototype]] 내부 슬롯이 가리키는 프로토타입 객체에 접근하기 위해 사용하는 접근자 프로퍼티로 간전적으로 프로토타입 객체에 접근할 수 있다.

```js
console.log(increase.__proto__ === Function.prototype) // true
console.log(increase.__proto__.__proto__ === Object.prototype) // true
console.log(increase.hasOwnProperty("__proto__")) // false
```

- `prototype`: 함수가 생성자 함수로 사용될 때, 생성자 함수가 생성할 인스턴스의 프로토타입 객체를 가리킨다.

```js
;(function () {}.hasOwnProperty("prototype")) // true
;({}.hasOwnProperty("prototype")) // false
```
