# 객체 리터럴

- 자바스크립트는 객체(object) 기반의 프로그래밍 언어로 구성하는 거의 '모든 것'이 객체다.(원시 값 제외)
- 원시 값은 변경할 수 없으나(immutable) 객체는 변경(mutable)할 수 있다.

## 객체(object)

- **프로퍼티(property)와 메서드(method)의 집합**

  - 프로퍼티: 객체의 상태를 나타내는 값(data)
  - 메서드: 프로퍼티를 참조하고 조작할 수 있는 동작(behavior)

  ```javascript
  var counter = {
    num: 42, // num: 프로퍼티 키, 42: 프로퍼티 값
    // 메서드
    increase: function () {
      this.num++;
    },
  };
  ```

## 객체 리터럴에 의한 객체 생성

> 인스턴스(instance): 클래스에 의해 생성되어 메모리에 저장된 실체

- 프로토타입 기반 객체지향언어로서 다양한 객체 생성 방법을 지원한다.

  - 객체 리터럴
  - Object 생성자 함수
  - 생성자 함수
  - Object.create 메서드
  - 클래스

## 프로퍼티

- **키(key)와 값(value)** 으로 구성된다.
- 마지막 프로퍼티 뒤의 쉼표 유무는 크게 상관없다.
- 식별자 네이밍 규칙을 따르지 않는 이름에는 반드시 따옴표를 사용한다.

  ```javascript
  var person = {
    "first-name": "Lee",
  };
  ```

## 메서드

## 프로퍼티 접근

- 대괄호 프로퍼티 접근 연산자 내부에 지정하는 프로퍼티 키는 반드시 따옴표로 감싼 문자열이어야 한다.
- 프로퍼티 키가 숫자로 이뤄진 문자열인 경우 따옴표를 생략할 수 있다.

  ```javascript
  var person = {
    name: "Lee",
  };

  console.log(person.name); // 마침표 표기법
  console.log(person["name"]); // 대괄호 표기법
  ```

- 객체에 존재하지 않은 프로퍼티에 접근하면 `undefined`를 반환한다.

## 프로퍼티 값 갱신

## 프로퍼티 동적 생성

- 존재하지 않는 프로퍼티에 값을 할당하면 프로퍼티가 동적으로 생성, 값이 할당된다.

## 프로퍼티 삭제

- `delete`연산자로 객체의 프로퍼티를 삭제한다.

## ES6에서 추가된 객체 리터럴의 확장 기능

- ES6에서 추가되었다.

### 프로퍼티 축약 표현

- 변수 이름과 프로퍼티 키가 동일한 이름일 때 프로퍼티 키를 생략(property shorthand)할 수 있다.
- 프로퍼티 키는 변수 이름으로 자동 생성된다.

  ```javascript
  let x = 1,
    y = 2;

  const obj = { x, y };
  console.log(obj); // {x: 1, y: 2}
  ```

### 계산된 프로퍼티 이름(computed property name)

### 메서드 축약 표현

- 프로퍼티 값으로 함수를 할당한다.
