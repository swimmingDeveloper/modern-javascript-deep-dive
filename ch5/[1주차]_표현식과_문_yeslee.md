# 표현식과 문

## 값(value)

- 표현식이 평가되어 생성된 결과

## 리터럴(literal)

- 사람이 이해할 수 있는 문자 또는 약속된 기호를 사용해 값을 생성하는 표기법(notation)
- 숫자 리터럴 42를 코드에 적으면, 자바스크립트 엔진은 숫자 값 42를 생성한다.

## 표현식(expression)

- 값으로 평가될 수 있는 문(statement)으로 표현식이 평가되면 새로운 값을 생성하거나 기존 값을 참조한다.

  ```javascript
  var num = 42;
  ```

## 문(statement)

- 프로그램을 구성하는 기본 단위, 최소 실행 단위로 여러 토큰으로 구성된다.

  > 토큰(token)? 문법적으로 더 이상 나눌수 없는 코드의 기본 요소

  ```javascript
  // token: var, opt, =, 40, +, 2
  var opt = 40 + 2; // statement
  ```

- 프로그램은 문의 집합이며, 프로그래밍은 문을 작성하고 순서에 맞게 나열한 것이다.

### 표현식 vs 문?

- 변수에 할당하는 것으로 판단할 수 있다.

  ```javascript
  var foo = var x; // SyntaxError: Unexpected token var

  var foo = 100;
  ```

- 완료 값(completion value): 표현식이 아닌 문을 실행하면 항상 `undefined`를 출력하는데 이는 표현식의 평가 결과는 아니다.

## 세미콜론(;)

- 문의 종료를 나타내며 자바스크립트 엔진은 세미콜론으로 문이 종료된 위치를 파악한다.
- 세미콜론 자동 삽입 기능(ASI; automatic semicolon insertion): 자바스크립트 엔진은 소스코드 해석 시 문의 끝이라고 예측되는 지점에 세미콜론을 자동으로 붙여준다.
