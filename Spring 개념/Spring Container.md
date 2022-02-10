## Spring Container

개발자를 대신해서 Bean의 생성 / 소멸의 전반적인 life cycle을 관리한다.

#### Bean

- Spring framework에서 기본적인 객체를 의미
- 기본으로 scope는 singleton, @scope("prototype")을 지정할 경우 매번 새로운 객체를 할당



Container의 초기화: bean 객체의 생성, 의존 주입(+자동 주입), 초기화

Container의 종료: bean 객체의 소멸

