# 자바스크립트 개발 환경과 실행 방법

- 모든 브라우저와 Node.js는 자바스크립트 엔진을 내장하고 있어 브라우저에서 동작하는 코드는 Node.js 환경에서도 동일하게 동작한다.
- 브라우저와 Node.js는 DOM API를 제공하느냐의 여부에 따라 용도가 다르다.

  > DOM(Document Object Model) API?
  >
  > - 파싱한 HTML 요소를 선택하거나 조작하는 기능의 집합

  - 브라우저는 HTML, CSS, 자바스크립트 실행해 웹페이지를 브라우저 화면에 렌더링하고 클라이언트 사이드 Web API를 지원한다.
  - Node.js는 브라우저 외부에서 자바스크립트 실행 환경을 제공하고 ECMAScript와 Node.js 고유의 API를 지원한다.

  > 웹 크롤링(Web crawling)
  >
  > - 서버에서 웹사이트의 콘텐츠를 수집하기 위해 웹사이트에서 HTML 문서를 가져와 가공하여 필요한 데이터만 추출하는 과정을 일컫는다.
  >
  > - 서버에서 DOM API를 제공하지 않으므로 DOM 라이브러리(cheerio(JavaScript), BeautifulSoup(Python) 등)을 사용해 HTML 문서를 가공한다.

## 개발자 도구(DevTools)

> Windows: F12 혹은 Ctrl + Shift + I
>
> macOS: F12 혹은 command + option + I

- **Elements**: 로딩된 웹페이지의 DOM과 CSS 편집해서 렌더링된 뷰를 확인할 수 있다.
- **Console**: 로딩된 웹페이지의 에러를 확인하거나 자바스크립트 소스코드에 작성한 console.log 메서드의 실행 결과를 확인할 수 있다.
- **Sources**: 로딩된 웹페이지의 자바스크립트 코드를 디버깅할 수 있다.
- **Network**: 로딩된 웹페이지에 관련된 네트워크 요청(request) 정보와 성능을 확인할 수 있다.
- **Application**: 웹 스토리지, 세션, 쿠키를 확인하고 관리할 수 있다.

- [개발자 도구에서 디버깅하기](https://developer.chrome.com/docs/devtools/javascript/reference/)

## npm

- 자바스크립트 패키지 매니저로 Node.js에서 사용할 수 있는 모듈들을 패키지화해 모아둔 저장소 역할과 패키지 설치 및 관리를 위한 CLI를 제공한다.
