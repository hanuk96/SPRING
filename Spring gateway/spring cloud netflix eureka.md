Spring cloud gateway를 이용하게되면 각각의 마이크로서비스들은 서로의 포트 번호를 몰라도 된다.

netty 서버를 내장한 web flux 기반 gateway



spring eureka server를 통해서 micro service들을 등록하고 이를 가져다 사용할 수 있다



- Front 에서는 요청을 Gateway로만 보내면 되기 때문에 Gateway 포트만 알면 모든 요청을 수행할 수 있다.
- 모든 요청은 Gateway 를 거치기 때문에 로그를 쉽게 다룰 수 있다.
- Gateway 가 요청의 진입점이므로 통합 인증을 수행할 수 있다.
- same origin policy 등 보안, 인증 관련 issue들을 한번에 처리할 수 있다.