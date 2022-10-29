# 09장. 타입 변환과 단축 평가

## 9.1 타입 변환이란?

- 개발자가 의도적으로 타입 변환할 경우: 명시적 타입 변환(explicit coercion) 또는 타입 캐스팅(type casting)
- JS 엔진에 의해 암묵적으로 변환: 암묵적 타입 변환(implicit coercion) 또는 타입 강제 변환(type coercion)
- 타입 변환 시, 원시 값을 사용해 새로운 값을 생성함

## 9.2 암묵적 타입 변환

### 9.2.1 문자열 타입으로 변환

```js
0 + ''; // '0'
```

### 9.2.2 숫자 타입으로 변환

```js
+'0'; // 0
```

### 9.2.3 불리언 타입으로 변환

- Falsy 값: `undefined`, `null`, `0`, `-0`, `NaN`, `''`, `false`
- Truthy 값: Falsy 값을 제외한 모든 값

```js
!!0; // false
```

## 9.3 명시적 타입 변환

### 9.3.1 문자열 타입으로 변환

```js
String(0); // '0'
(0).toString(); // '0'
0 + ''; // '0'
```

### 9.3.2 숫자 타입으로 변환

```js
Number('0'); // 0
parseInt('0', 10); // 0
parseFloat('0'); // 0
+'0'; // 0
'0' * 1; // 0
```

### 9.3.3 불리언 타입으로 변환

```js
Boolean(0); // false
!!0; // false
```

## 9.4 단축 평가

### 9.4.1 논리 연산자를 사용한 단축 평가

- 논리 연산자를 사용해 표현식을 간결하게 작성할 수 있음
- 불리언 타입이 아닐 경우, Truthy/Falsy 값으로 평가됨
- `true && anything`: `anything`
- `false && anything`: `false`
- `true || anything`: `true`
- `false || anything`: `anything`
- 사용 상황
  - `null` 혹은 `undefined` 체크 후 프로퍼티 참조
  - 함수 매개변수 기본값 설정

### 9.4.2 옵셔널 체이닝 연산자

- `?.`
- 프로퍼티가 존재하는지(`null` 혹은 `undefined`인지) 체크

### 9.4.3 null 병합 연산자

- `??`
- 좌항의 피연산자가 `null` 혹은 `undefined`인 경우 우항의 피연산자를 반환
