# security

## [CORS](https://developer.mozilla.org/ko/docs/Web/HTTP/CORS) 교차 출처 리소스 공유

- 웹 페이지 상의 제한된 리소스를 최초 자원이 서비스된 도메인 밖의 다른 도메인으로부터 요청할 수 있게 허용하는 구조이다.

## [https](https://ko.wikipedia.org/wiki/HTTPS)

- HTTPS는 소켓 통신에서 일반 텍스트를 이용하는 대신에, SSL이나 TLS 프로토콜을 통해 세션 데이터를 암호화한다. 따라서 데이터의 적절한 보호를 보장한다. HTTPS의 기본 TCP/IP 포트는 443이다.

## Authentication, 인증

### jwt

- JSON 형식의 데이터를 저장하는 토큰입니다.
- 구성요소
  - 헤더: 토큰 종류와 해시 알고리즘
  - 페이로드: 토큰 내용물이 인코딩된 부분
  - 시그니처: 문자열, 시그니처를 통해 토큰 변조 여부를 확인
- 단점: 용량이 큼
- [jwt nhn 클라우드 설명](https://meetup.toast.com/posts/239)

## 공격

### XSS, 크로스 사이트 스크립팅

- 웹사이트 관리자가 아닌 사람이 웹 페이지에 악성 스크립트를 삽입할 수 있는 취약점이다.
- 주로 게시판에 악성 스크립트가 담긴 글을 올리는 형태이다.
- 크래커가 사용자 정보가 담긴 쿠키나 세션을 탈취하고 자동으로 비정상적인 기능을 수행하도록 한다.
- cookie는 httponly로 해결 가능

### XSRF, 사이트 간 요청 위조

- 크로스 사이트 요청 위조
- 사용자가 자신의 의지와 무관하게 공격자가 의도한 행위를 특정 웹사이트에 용청하는 공격이다.
- 크래커는 가짜 웹사이트를 만들어 사용자가 로그인하게 한 뒤 쿠키를 탈취하는 행위를 말하낟.
- expressjs에서 csurf 모듈을 사용하거나 쿠키 설정에 samesite 설정을 한다.

### helmet 모듈

- helmet을 이용하면 HTTP 헤더를 적절히 설정하면 몇가지 잘 알려진 웹 취약성으로부터 앱을 보호 할 수 있습니다. 미들웨어 함수는 9개 입니다.

### nestjs validator pipe

- whitelist: If set to true, validator will strip validated (returned) object of any properties that do not use any validation decorators. 데코레이터가 없는 속성이 들어오면 해당 속성은 제거하고 받아들입니다.
- forbidNonWhitelisted: If set to true, instead of stripping non-whitelisted properties validator will throw an exception. DTO에 정의되지 않은 값이 넘어오면 request 자체를 막습니다.

### nestjs validator guard

- 인증과 권한에 관련이 있는 미들웨어입니다. 인증 토큰을 확인하는 작업에 유용하게 사용됩니다.
