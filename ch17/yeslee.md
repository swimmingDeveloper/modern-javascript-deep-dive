# 생성자 함수에 의한 객체 생성

## Object 생성자 함수

- `new` 연산자와 함께 호출하여 객체(instance)를 생성하는 함수다.

  > 인스턴스(instance)? 생성자 함수에 의해 생성된 객체.

- 반드시 사용하여 빈 객체를 생성하지 않아도 된다 → 객체 리터럴을 사용하는 것이 더 간편!

## 생성자 함수(constructor)

### 객체 리터럴에 의한 객체 생성 방식의 문제점

```js
const circle1 = {
  radius: 5,
  getDiameter() {
    return 2 * this.radius;
  },
};

console.log(circle1.getDiameter()); // 10

const circle2 = {
  radius: 10,
  getDiameter() {
    return 2 * this.radius;
  },
};

console.log(circle2.getDiameter()); // 20
```

- 직관적이고 간편하지만 단 하나의 객체만을 생성한다. → _동일한 프로퍼티를 갖는 객체를 여러 개 생성해야하는 경우_ 같은 프로퍼티를 여러 번 기술해야하기 때문에 비효율적이다.

  > - 객체는 **프로퍼티**를 통해 객체 고유의 상태(state)를 표현한다.
  >
  > - **메서드**를 통해 프로퍼티를 참조하고 조작하는 동작(behavior)를 표현한다.

### 생성자 함수에 의한 객체 생성 방식의 장점

- 생성자 함수를 사용하여 프로퍼티 구조가 동일한 객체 여러 개를 간편하게 생성할 수 있다.

```js
// constructor
function Circle(radius) {
  // construct 내의 this는 constructor가 생성할 인스턴스를 가리킨다.
  this.radius = radius;
  this.getDiameter = function () {
    return 2 * this.radius;
  };
}

// new 연산자와 함께 호출하면 해당 함수(Circle)는 생성자 함수로 동작한다.
const circle1 = new Circle(5);
const circle2 = new Circle(10);

console.log(circle1.getDiameter()); // 10
console.log(circle2.getDiameter()); // 20
```

> **this**
>
> - 객체 자신의 프로퍼티나 메서드를 참조하기 위한 자기 참조 변수(self-referencing variable).
>
> - this 바인딩은 *함수 호출 방식*에 따라 동적으로 결정된다.
>
> | 함수 호출 방식                    | this가 가리키는 값(this 바인딩)                                  |
> | --------------------------------- | ---------------------------------------------------------------- |
> | 일반 함수로서 호출                | - 전역 객체<br>- `window`(브라우저 환경), `global`(Node.js 환경) |
> | 메서드로서 호출                   | 메서드를 호출한 객체                                             |
> | 생성자 함수(constructor)로서 호출 | 생성자 함수가 생성할 인스턴스                                    |

### 생성자 함수의 인스턴스 생성 과정

- 생성자 함수의 역할

  - 인스턴스를 생성한다.
  - 생성된 인스턴스를 초기화(인스턴스 프로퍼티 추가 및 초기값 할당)한다.

1. 생성자 함수가 생성한 빈 객체(인스턴스)가 암묵적으로 생성되고 this에 바인딩된다.

   > **바인딩(name binding)?** 식별자와 값을 연결하는 과정
   >
   > → this에 바인딩된다 = this가 가리킬 객체를 바인딩한다.
