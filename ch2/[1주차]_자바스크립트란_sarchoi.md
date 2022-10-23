# 02장. 자바스크립트란?

## 2.1 자바스크립트의 탄생

- 1996년 3월, 넷스케이프 내비게이터2 브라우저에 탑재
- 넷스케이프 커뮤니케이션즈사의 브렌던 아이크(Brendan Eich)
- 웹페이지의 보조 기능을 수행하기 위한 경량 프로그래밍 언어로써 개발

## 2.2 자바스크립트의 표준화

- 1996년 8월: 마이크로소프트가 JScript를 인터넷 익스플로러에 탑재
	- 크로스 브라우징 이슈
- 1996년 11월: 넷스케이프가 표준화 요청
- 1997년 7월: ECMA-262(ECMAScript 1 Specification)
- 1998년: ECMAScript 2
	- ISO/IEC 16262 규격 적용
- 1999년: ECMAScript 3(ES3)
- 2009년: ECMAScript 5(ES5)
	- HTML5와 함께 출시
- 2015년: ECMAScript 6(ES6, ECMAScript 2015)
	- 범용 프로그래밍 기능 대거 도입
- 이후 매년 기능 추가

## 2.3 자바스크립트 성장의 역사

- 초기 브라우저: HTML과 CSS 단순 렌더링

### 2.3.1 Ajax

- Ajax(Asynchronous JavaScript and XML)
	- 1999년
	- 비동기(asynchronous) 통신
- XMLHttpRequest 객체
- 변경이 필요한 부분만 렌더링 가능
	- 웹 애플리케이션의 성능 향상, 부드러운 화면 전환 가능

### 2.3.2 jQuery

- DOM(Document Object Model) 쉽게 조작
- 크로스 브라우징 이슈 지원

### 2.3.3 V8 자바스크립트 엔진

- 빠른 성능
	- 서버 사이드의 로직들이 클라이언트 사이드로 이동

### 2.3.4 Node.js

- 2009년 라이언 딜(Ryan Dahl)
- 구글 V8 자바스크립트 엔진 기반의 런타임 환경
- 자바스크립트 엔진을 브라우저에서 독립시킨 실행 환경
- 특징
	- 빌트인 API: 모듈, 파일 시스템, HTTP 등
	- 비동기 I/O
	- 단일 스레드 이벤트 루프 기반
		- 요청 처리 성능 좋음
		- I/O 많은 SPA에 적합
- 프론트엔드와 백엔드 영역에서의 동형성
- 크로스 플랫폼

### 2.3.5 SPA 프레임워크

- AngularJS, React, Vue.js, Svelte 등
- CBD(Component-Based Development) 방법론
- SPA(Single Page Application)

## 2.4 자바스크립트와 ECMAScript

- ECMAScript: 자바스크립트의 표준 사양, ECMA-262
	- 핵심 문법 규정
	- 제조사는 이 사양을 준수해서 브라우저의 엔진 구현
- 자바스크립트: ECMAScript + 브라우저 API
	- 브라우저 API: DOM, BOM, Canvas, XMLHttpRequest, Fetch, requestAnimationFrame, SVG, Web Storage, Web Component, Web Worker 등
- 클라이언트 사이드 Web API는 W3C에서 사양 관리
- [Web API - MDN Web Docs](https://developer.mozilla.org/ko/docs/Web/API)

## 2.5 자바스크립트의 특징

- 기존 프로그래밍 언어의 영향
	- 기본 문법: C, 자바
	- 프로토타입 기반 상속: Self
	- 일급 함수: Scheme
- 인터프리터 언어
	- 모던 JS 엔진은 인터프리터와 컴파일러의 장점을 결합하여 속도 문제 해결
- 멀티 패러다임 프로그래밍 언어 **프로토타입 기반 객체지향 언어**
	- 명령형
	- 함수형
	- 프로토타입 기반
	- 객체지향 프로그래밍

## 2.6 ES6 브라우저 지원 현황

- https://kangax.github.io/compat-table/es6/
- Babel: ES6+ 소스코드를 ES5 이하로 변환해주는 트랜스파일러
	- https://babeljs.io/
