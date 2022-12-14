# 05_표현식과 문

## 값

- 표현식이 평가되어 생성된 결과
- 평가는 런타임 전에 이루어지며, 변수를 생성하거나 변수를 참조하게 된다

```tsx
var foo = 1 + 1;
```

- 위 예시에서는 1 + 1이 평가되어 2라는 값이 생성되었고, 이 값이 `foo` 변수에 할당되었다
- 결과적으로 변수가 가리키는 메모리 공간에는 1 + 1 이라는 식이 저장되는 것이 아니라, 그 결과인 2가 저장되는 것이다
    - 평가는 할당 전에 이루어지므로 1 + 1에 대한 결과값 생성도 그 전에 수행된다

## 리터럴

```tsx
"hello this is string" // 문자열 리터럴
123 // 숫자 리터럴
1.5 // 숫자 리터럴
`${foo} is my favorite value` // 문자열 리터럴 (템플릿)
```

- 사람이 이해할 수 있는 문자 또는 약속된 기호를 사용하여 값을 생성하는 표기법
    - 위 예시들은 모두 문자열 또는 숫자 리터럴이다
    - 자바스크립트 엔진은 이처럼 약속된 방식으로 구성된 리터럴들을 평가하여 값을 생성한다

```tsx
123 // 정수 리터럴
1.5 // 부동소수점 리터럴
0b1011 // 2진수 리터럴 - 0b로 시작
0o172 // 8진수 리터럴 - 0o로 시작
0xF3 // 16진수 리터럴 - 0x로 시작
"this is string" // 문자열 리터럴
true // boolean 리터럴
null // null 리터럴
undefined // undefined 리터럴
{ name: "chichoon", age: 1000000 } // 객체 리터럴
[ "foo", "bar" ] // 배열 리터럴
function foo() {} // 함수 리터럴
/[A-Z]+/g // 정규표현식 리터럴
```

- 다양한 리터럴들이 있어요

## 표현식

```tsx
// 리터럴 표현식
10;
'hihi';

// 연산자 표현식
5 + 5;
a = 5;

var score =
```

- 값으로 평가될 수 있는 문
- 표현식이 평가되면 새로운 값을 생성하거나, 기존에 저장되어 있던 변수값 등을 참조한다
    - 리터럴도 값으로 평가되므로 (평가 후 값이 생성되므로) 리터럴도 표현식의 일종이다
- 표현식의 결과값은 다른 표현식의 일부가 되어 새로운 결과를 도출해내는데 사용할 수 있다

## 문

```tsx
var x; // 선언문
x = 5; // 할당문
function foo() {} // 함수 선언문
if (true) {} // 조건문
for (;;) {} // 반복문
```

- door 아님
- 프로그램을 구성하는 기본 단위 + 최소 실행 단위로, 여러 개의 토큰으로 구성된다
    - 토큰은 문법적으로 더 이상 쪼갤 수 없는, 코드에서의 기본 요소 - 최소 단위를 의미한다
    - 토큰의 예시로 예약어, 세미콜론(`;`), 연산자, 식별자, 리터럴 등이 있다
- 명령문이라고도 한다
    - 즉 컴퓨터에게 명령을 내리는 문장이라고 생각하면 된다
- 선언문, 할당문, 반복문, 조건문 등 세부적으로 또 나뉘어진다

## 세미콜론과 자동 삽입 기능

```tsx
var foo = 1;
```

- 어떠한 (명령)문의 끝 (종료 지점) 을 나타낸다
- 자바스크립트 엔진은 세미콜론을 기준으로 문의 종료 위치를 파악하므로, 문을 끝낼 때 세미콜론을 붙이는 것이 좋다
    - 자바스크립트에서 세미콜론은 선택사항이다
    - 엔진에서 소스코드 해석 시에 세미콜론의 위치를 예측해서 자동으로 붙여 주기 때문
    - 다만 개발자의 의도와 엔진에서의 분석이 항상 일치하리라는 법이 없기 때문에 가급적이면 직접 붙여주는 것이 좋다
- 세미콜론 필수파와 선택파가 자주 대립한다
    - 다만 ESLint와 같은 정적 분석 도구와 TC39 (ECMAScript 기술 위원회) 도 권장하는 편

## 표현식인 문과 표현식이 아닌 문

- 표현식은 문의 일부일 수도 있고 아닐 수도 있습니다
- 값으로 평가될 수 있으면 표현식이고, 아니면 표현식이 아니다
    - 변수에 할당해 보았을 때 할당이 가능하면 표현식이고, 아니면 (값으로 평가할 수 없다는 뜻이므로) 표현식이 아니다
- 크롬 개발자 도구에서 표현식이 아닌 문을 실행하면 무조건 `undefined`를 출력하는데, 이는 표현식의 평가 결과가 아니라 단순히 완료를 알리는 값이므로 변수에 할당이 불가능하고 참조도 불가능하다

```tsx
var foo = var x;
```

- 위의 경우 어색하므로 변수 선언문은 표현식이 아닌 문이다

```tsx
var foo = (j === i);
```

- 위의 경우 `j`와 `i`가 같을 때와 다를 때 각각 boolean 값을 반환하므로 표현식이다
