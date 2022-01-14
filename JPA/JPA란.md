## JPA(JAVA Persistence api)

- Connection pool: DB의 connection에 대한 객체를 일정량 모아둔 Pool을 생성하고 재활용하는 방식
  - JNDI lookup(Connection객체의 이름을 가짐)을 통해서 DB와 연관된 datasource를 얻는다
  - datasource(Connection pool을 관리하는 목적으로 사용되는 객체)에 맞는 connection을 connection pool에 요청한다
  - conncetion pool에서 connection과 관련된 어플리케이션을 실행
- Api: 서버와 서버 사이를 연결해주는 interface
  - 인터페이스: 상하관계가 존재하는 약속
  - 프로토콜: 동등한 관계에서의 약속
- ORM: 객체(클래스)와 관계형 데이터베이스(테이블)를 자동으로 mapping해주는 것
- 반복적인 CRUD작업을 줄여줌(함수를 이용함)
- context: 대상에대한 모든 정보를 가지고 있는것
  - 영속성 context와 db는 동기화
- oop관점에서 모델링을 가능하게 해준다(상속, composition, 연관관계)

- sql mapper와의 비교

  |            | SQL Mapper                      | JPA                                                |
  | ---------- | ------------------------------- | -------------------------------------------------- |
  | RDB의 종류 | 특정 DB에 종속적임              | 종속적이지 않아 쿼리에 집중할 필요없음             |
  | 난이도     | 세부적인 SQL 쿼리를 사용해 쉬움 | 어려움                                             |
  | 수정       | 설정 변경시 수정사항이 많다     | 기본적인 CRUD의 제공으로 비즈니스 로직에 집중 가능 |

  

