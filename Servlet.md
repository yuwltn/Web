# Servlet이란?
> 클라이언트의 요청을 처리하고, 그 결과를 반환하는 Servlet 클래스의 구현 규칙을 지킨 자바 웹 프로그래밍 기술<br>
> 자바로 구현된 [CGI](https://github.com/yuwltn/-/blob/main/CGI.md)

서블릿이란 자바를 사용하여 웹을 만들기 위해 필요한 기술로 클라이언트가 어떠한 요청을 하면 그에 대한 결과를 다시 전송해주어야 하는데 이러한 역할을 하는 자바 프로그램이다.


### 💡 Servlet이 필요한 이유?
일반적인 웹서버는 정적인 페이지만을 제공한다. 정적인 웹 페이지의 문제점을 보완하여 나온 것이 동적 웹페이지를 구현하는 것이다.
동적인 페이지를 제공하기 위해서 웹서버는 다른 곳에 도움을 요청하여 동적인 페이지를 작성해야 한다.
여기서 웹서버가 동적인 페이지를 제공할 수 있도록 도와주는 어플리케이션이 서블릿이며, 동적인 페이지를 생성하는 어플리케이션이 CGI이다.

<br>

## Servlet 특징
<img src = "https://github.com/yuwltn/yuwltn/blob/7248ea989fb2b36069720c77927fd5523dd8767b/servlet.PNG" width = "700" height = "280" >

* 클라이언트의 요청에 대해 동적으로 작동하는 웹 어플리케이션 컴포넌트
* html을 사용하여 요청에 응답한다.
* Java Thread를 이용하여 동작한다.
* MVC 패턴에서 Controller로 이용된다.
* HTTP 프로토콜 서비스를 지원하는 javax.servlet.http.HttpServlet 클래스를 상속받는다.
* UDP보다 처리 속도가 느리다.
* HTML 변경시 Servlet을 재컴파일해야 하는 단점이 있다.

<br>

## Servlet 동작 방식
1. 클라이언트(사용자)가 URL을 입력하면 HTTP Request가 Servlet Container로 전송한다.
2. 요청을 전송받은 Servlet Container는 HttpServletRequest, HttpServletResponse 객체를 생성한다.
3. web.xml을 기반으로 사용자가 요청한 URL이 어느 서블릿에 대한 요청인지 찾는다.
4. 해당 서블릿에서 service 메소드를 호출한 후 클라이언트의 GET, POST 여부에 따라 doGet() 또는 doPost()를 호출한다.
5. doGet() or doPost() 메소드는 동적 페이지를 생성한 후 HttpServletResponse 객체에 응답을 보낸다.
6. 응답이 끝나면 HttpServletRequest, HttpServletResponse 두 객체를 소멸시킨다.

<br>

# Servlet Container
> 서블릿을 관리해주는 컨테이너

서블릿 컨테이너는 클라이언트의 요청(Request)을 받아주고 응답(Response)할 수 있게, 웹서버와 소켓으로 통신한다.<br>
대표적인 예로 톰캣(Tomcat)이 있다. 톰캣은 실제로 웹 서버와 통신하여 JSP(자바 서버 페이지)와 Servlet이 작동하는 환경을 제공해준다.

## Servlet Container 역할
1. 웹 서버와의 통신 지원<br>
  Servlet Container는 Servlet과 웹 서버가 손쉽게 통신할 수 있게 해준다. 일반적으로 우리는 소켓을 만들고 listen, accept 등을 해야하지만 Servlet Container는 이러한 기능을 API로 제공하여 복잡한 과정을 생략할 수 있게 해준다. 그래서 개발자가 Servlet에 구현해야 할 비즈니스 로직에 대해서만 집중할 수 있게 도와준다.

2. Servlet 생명주기(Life Cycle) 관리<br>
  Servlet Container는 Servlet의 탄생과 죽음을 관리한다. Servlet 클래스를 로딩하여 인스턴스화하고, 초기화 메소드를 호출하고, 요청이 들어오면 적절한 Servlet 메소드를 호출한다.<br>
  또한 Servlet이 생명을 다하는 순간에는 적절하게 Garbage Collection을 진행하여 편의를 제공한다.

3. 멀티스레드 지원 및 관리<br>
  Servlet Container는 요청이 올 떄마다 새로운 자바 스레드를 하나 생성하는데 HTTP 서비스 메소드를 실행하고 나면 스레드는 자동으로 죽게된다. 원래는 스레드를 관리해야하지만 서버가 다중스레드를 생성 및 운영해주니 스레드의 안전성에 대해서 걱정하지 않아도 된다.
  
4. 선언적인 보안 관리<br>
  Servlet Container를 사용하면 개발자는 보안에 관련된 내용을 Servlet 또는 자바 클래스에 구현해 놓지 않아도 된다. 일반적으로 보안관리는 XML 배포 서술자에 기록하므로 보안에 대해 수정할 일이 생겨도 자바 소스 코드를 수정하여 다시 컴파일 하지 않아도 보안관리가 가능하다.
  
 
## Servlet 생명주기


