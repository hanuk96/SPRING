database를 jdbc를 이용하여 사용하는 방법

1. DB 서버 접속을 위해 JDBC 드라이버를 로드한다.
2. DB 접속 정보와 DriverManager.getConnection() Method를 통해 DB Connection 객체를 얻는다.
3. Connection 객체로 부터 쿼리를 수행하기 위한 PreparedStatement 객체를 받는다.
4. executeQuery를 수행하여 그 결과로 ResultSet 객체를 받아서 데이터를 처리한다.
5. 처리가 완료되면 처리에 사용된 리소스들을 close하여 반환한다.

이때 가장 시간이 오래걸리는 부분은 db에 최초에 연결되어 connection 객체를 생성하는 부분



db connection pool이란?

1. WAS가 실행되면서 미리 일정량의 DB Connection 객체를 생성하고 `Pool` 이라는 공간에 저장해 둔다.
2. HTTP 요청에 따라 필요할 때 Pool에서 Connection 객체를 가져다 쓰고 반환한다.
3. 이와 같은 방식으로 HTTP 요청 마다 DB Driver를 로드하고 물리적인 연결에 의한 Connection 객체를 생성하는 비용이 줄어들게 된다.



WAS의 Thread는 Connection Pool의 갯수보다 여유있게 설정하는 것이 좋다.

Connection Pool은 시스템의 환경에 따라 다르지만 보통 40~50개로 지정하면 Thread는 이보다 10개 정도 더 지정하는 것이 바람직하다. 하지만 최적의 성능의 위해서는 실제 요청이 얼마나 들어오는지 파악하는게 중요하며 가장 좋은 방법은 앞서 말한것 처럼 성능 테스트를 통해 최적화된 값을 구하는 것이다.
