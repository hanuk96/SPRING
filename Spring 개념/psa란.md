## PSA(Portable Service Abstraction)

**PSA란 추상화 계층을 사용하여 어떠한 기술을 내부에 숨기고 개발자에게는 편의성을 제공해 주는것을 의미한다.**



스프링은 서블릿기반 웹 어플리케이션임에도 불구하고 서블릿이 전혀 존재하는 것 처럼 보인다. 

실제로는 내부적으로 서블릿 기반으로 코드가 동작하지만 서블릿 기술은 추상화 계층에 의해 숨겨져 있다.

요청을 처리하는 controller의 경우 @Controller 애노테이션이 붙어있는 클래스에서 @GetMapping, @PostMapping과 같은 @RequestMapping 애노테이션을 사용해서 요청을 매핑한다.

- 즉 HttpServlet을 상속받고 doGet(), doPost()를 구현하는 등의 작업을 직접 하지 않아도 된다.



트랜잭션의 처리의 경우 commit, rollback, connection 등을 명시적으로 호출해야 한다. 그러나 spring이 제공하는 @Transactional 애노테이션을 사용하면 트랜잭션 처리가 간단해진다.

- 또한 다양한 기술스택으로 구현체를 쉽게 바꿀 수 있다.
- JDBC, MY-BATIS, JPA, HIBERNATE 등 엔티티와 객체의 관계를 매핑하는 여러 라이브러리들을 유연하게 바꿔서 사용할 수 있다.



