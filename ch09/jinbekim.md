# 타입 변환과 단축 평가

### falsy
* false
* undefined
* null
* 0, -0
* NaN
* ''

### 단축 평가
* `'Cat' && 'Dog' // 'Dog'`
* `'Cat' || 'Dog' // 'Cat'`
* 옵셔널 체이닝 연산자, 좌항의 피연산자가 null 또는 undefined인 경우 undefined를 반환
* null 병합 연산자, 좌항의 피연산자가 null 또는 undefined인 경우 우항의 피연산자를 반환
* `var foo = null ?? 'default string'; // 'default string'`
