# 타입 변환과 단축 평가

- 기존 원시 값을 사용해 다른 타입의 새로운 원시 값을 생성한다.

## 명시적 타입 변환(explicit coercion), 타입 캐스팅(type casting)

- 개발자가 의도적으로 값의 타입을 변환한다.

## 압묵적 타입 변환(implicit coercion), 타입 강제 변환(type coercion)

```javascript
1 + "2"; // '12'
1 - "1"; // 0
```

- 표현식을 평가하는 도중에 개발자의 의도와 상관없이 자바스크립트 엔진에 의해 암묵적으로 타입이 자동 변환된다.
- 자바스크립트 엔진은 압묵적 타입 변환해 새로운 타입의 값을 만들어 단 한 번 사용하고 버린다.
- 자바스크립트 엔진은 boolean 타입이 아닌 값을 **Truthy** 값(참으로 평가되는 값) 또는 **Falsy** 값(거짓으로 평가되는 값)으로 구분한다.

## 단축 평가(short-circuit evaluation)

- 논리 연산의 결과를 결정하는 피연산자를 타입 변환하지 않고 그대로 반환한다.
- 표현식을 평가하는 도중에 **평가 결과가 확정된 경우 나머지 평가 과정을 생략**한다.
  |단축 평가 표현식|평가 결과|
  |--|--|
  |true \|\| anything| true|
  |false \|\| anything| anything|
  |true && anything| anything|
  |false && anything| false|

- 객체를 가리키기를 기대하는 변수가 `null` 또는 `undefined`가 아닌지 확인하고 프로퍼티를 참조할 때

  ```javascript
  var elem = null;

  var value = elem && elem.value; // null
  ```

- 함수 매개변수에 기본값을 설정할 때

### 옵셔널 체이닝(optional chaining) 연산자 `?.`

- 좌항의 피연산자가 null 혹은 `undefined`인 경우, `undefined`를 반환하고 아니라면(Falsy 값 포함) 우항의 프로퍼티 참조를 이어간다.

```javascript
var elem = null;

var value = elem?.value;
console.log(value); // elem이 null 또는 undefined라면 undefined 반환, 아니라면 우항의 프로퍼티 참조를 이어간다.
```

### null 병합 연산자 `??`

- 좌항의 피연산자가 null 혹은 `undefined`인 경우, 우항의 피연산자를 반환하고 아니라면(Falsy 값 포함) 좌항의 피연산자를 반환한다.
- 변수에 기본값을 설정할 때 유용하다.
  ```javascript
  var foo = null ?? "default string";
  console.log(foo); // 'default string'
  ```
