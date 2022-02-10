## Spring

- FrameWork라서 사용자가 일정한 가이드라인을 지켜서 개발하기 쉽게 도와줌

- IOC 스프링 컨테이너가 의존성의 주입 객체의 life cycle을 관리함

  - Class: 설계도(class character)
  - Object: 실체화가 가능한 것(추상 클래스를 특정 클래스로 상세화)
  - Instance: 메모리에 올라간 것(new)

- DI: 이러한 의존성의 주입을 스프링 컨테이너가 하는것

- 어노테이션 기반으로하여 컴파일시에 오류 체크 가능, 런타임시 특정 기능을 실행하도록 정보를 제공한다

- Filter vs Interceptor

  ![image-20220113110531237](C:\Users\gi718\AppData\Roaming\Typora\typora-user-images\image-20220113110531237.png)

  ![image-20220113110516760](C:\Users\gi718\AppData\Roaming\Typora\typora-user-images\image-20220113110516760.png)

  - Filter: **디스패처 서블릿에 요청이 전달**되기 전/후에 url 에 맞는 모든 요청, 응답에 대한 부가작업을 처리
  - Interceptor: 디스패처 서블릿이 **컨트롤러를 호출**하기 전/후에 요청, 응답을 가공
  - 실행순서: filter -> interceptor -> aop

| 대상               | 필터                                         | 인터셉터                                                  |
| ------------------ | -------------------------------------------- | --------------------------------------------------------- |
| 관리되는 컨테이너  | 웹 컨테이너                                  | 스프링 컨테이너                                           |
| 요청 조작 가능여부 | o                                            | x                                                         |
| 용도               | 보안관련 모든작업<br />모든 요청에 대한 로깅 | 인증/인가같은 작업<br />controller로 넘겨주는 정보의 가공 |

- Message Converter를 가지고 있다
  - java object -> Json or xml -> python object 이렇게 json 등 으로 바꿔주는 라이브러리(jackson databind)
- @responsebody - > bufferedwriter, @requestbody -> bufferedreader를 변환하여 사용
- reflection api가 가능하다
  - **구체적인 클래스 타입을 알지 못해도** 런타임에 static영역을 참조하여 클래스의 정보(메서드, 타입, 변수 등등)에 접근할 수 있게 해주는 자바 API
  - 동적으로 클래스를 사용할 수 있게 해주어 DI가 가능하게 해주는 API

```
	Sample sample = new Sample();
    sample.doSomething();

    // Reflection
    Class sampleClazz = Class.forName("클래스명(Sample)");
    Method sampleMethod = sampleClazz.getMethod("doSomething");
    sampleMethod.invoke();
```

- 아파치 서버: web server로 client의 요청을 받아 이를 처리하여 정적인 data 처리를 진행하는 서버
- 톰캣: web application server로 java로 된 file을 client가 읽을 수 있도록 html로 변경하거나, db 트랜잭션과 같은 동적인 처리를 해준다(서블릿 컨테이너)
  - 아파치서버와 톰캣을 연동하여 쓰는이유? was인 톰캣만을 이용하여 서버를 구현하였을때 정적, 동적데이터를 모두 처리해야 하기때문에 사용자의 요청에의한 응답이 느려지게 될것이다

