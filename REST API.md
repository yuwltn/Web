# REST(Representational State Transfer)
자원을 이름으로 구분하여 해당 자원의 상태를 주고 받는 것을 의미한다.

1. HTTP URI(Uniform Resource Identifier)를 통해 자원(Resource)을 명시하고,
2. HTTP Method(POST, GET, PUT, DELETE)를 통해
3. 해당 자원(URI)에 대한 CRUD Operation을 적용하는 것을 의미한다.

## REST 구성 요소
1. 자원(Resource) : HTTP URI
2. 자원에 대한 행위(Verb) : HTTP Method
3. 자원에 대한 행위의 내용 : (Representations) : HTTP Message Pay Load

## REST의 특징
1. Server-Client(서버-클라이언트 구조)<br>
  REST 서버는 API 제공, 클라이언트는 사용자 인증이나 컨텍스트(세션, 로그인 정보) 등을 직접 관리하는 구조로 
  각각의 역할이 확실하게 구분되기 때문에 클라이언트와 서버에서 개발해야 할 내용이 명확해지고 서로간 의존성이 줄어들게 된다. 
  
2. Stateless(무상태)<br>
  작업을 위한 상태정보를 따로 저장하고 관리하지 않아서 들오는 요청만들 단순히 처리하면 된다.
  서비스의 자유도가 높아지고 서버에서 불필요한 정보를 관리하지 않음으로써 구현이 단순해진다.

3. Cacheable(캐시 처리 가능)<br>
  HTTP라는 기존 웹 표준을 그대로 사용하기 때문에 웹에서 사용하는 기존 인프라를 그대로 활용 가능하다.
  따라서 HTTPrk 가진 캐싱기능이 적용 가능하다. HTTP 프로토콜 표준에서 사용하는 Last-Modified태그나 E-Tag를 이용하면 캐싱 구현이 가능하다.

4. Layered System(계층화)<br>
  REST 서버는 다중 계층으로 구성될 수 있으며 보안, 로드 밸런싱, 암호화 계층을 추가해 구조상의 유연성을 둘 수 있고 
  Proxy, 게이트웨이 같은 네트워크 기반의 중간매체를 사용할 수 있게 한다.
  
5. Uniform Interface(인터페이스 일관성)<br>
  URI로 지정한 리소스에 대한 조작을 통일되고 한정적인 인터페이스로 수행하는 아키텍처 스타일

<br>

# REST API란?
REST의 원리를 따르는 API를 의미한다.

<br>

## REST API 설계 규칙
1. URI는 동사보다는 명사를, 대문자보다는 소문자를 사용하여야 한다.
2. 마지막에 슬래시(/)를 포함하지 않는다.
3. 언더바 대신 하이픈을 사용한다.
4. 파일확장자는 URI에 포함하지 않는다.
5. 행위를 포함하지 않는다.
