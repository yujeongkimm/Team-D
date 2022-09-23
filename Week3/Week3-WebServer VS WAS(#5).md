# [백엔드 스터디 in 큐시즘 - D조] Week 3: 스프링의 전반적인 이해
## #5. Web server와 WAS의 차이는 무엇인가

### Static Pages(정적 페이지)

- 항상 동일한 페이지를 반환한다
- image, html, css 파일 등과 같이 컴퓨터에 저장되어 있는 파일들

### Dynamic Pages(동적 페이지)

- 동적인 contents를 반환한다
- 웹 서버에 의해서 실행되는 프로그램을 통해서 만들어진 결과물

### Web Server

- 웹 브라우저 클라이언트로부터 HTTP 요청을 받아 정적인 컨텐츠를 제공하는 컴퓨터 프로그램
- HTTP프로토콜을 기반으로 하여 클라이언트의 요청을 서비스하는 기능을 담당
- 기능
    - 정적인 컨텐츠를 제공하고, WAS를 거치지않고 바로 자원을 제공한다
    - 동적인 컨텐츠 제공을 위한 요청을 전달한다. 클라이언트의 요청(Request)을 WAS에 전달하고 WAS의 응답(Response)을 클라이언트에게 전달한다.

### Web Application Server(WAS)

- DB 조회 등과 같이 다양한 로직 처리를 요구하는 동적인 컨텐츠를 제공하기 위해 만들어진 Application Server
- HTTP를 통해 컴퓨터나 장치에 애플리케이션을 수행해주는 미들웨어이다
- Web Server + Web Container의 역할을 한다
- Container란 JSP, Servlet등을 실행시킬 수 있는 소프트웨어를 말하고, 현재는 WAS가 가진 Web Server도 정적인 컨텐츠를 처리하는데 성능상 큰 차이가 없다.
- 기능
    - 프로그램 실행 환경과 DB접속 기능 제공
    - 여러개의 트랜잭션 관리 가능
    - 업무를 처리하는 비즈니스 로직 수행

### Web Server 와 WAS를 분리하는 이유

- 기능을 분리하여 서버 부하 방지
    - WAS는 DB조회 등과 같이 다양한 로직 처리를 수행하는 역할이 크기 때문에 정적 컨텐츠는 Web Server에서 관리하는 것이 좋다
- 물리적으로 보완하여 보완 강화
- 여러대의 WAS를 연결 가능
- Web Server를 WAS앞에 두면 효율적인 분산 처리가 가능하다
- 정리하면, 자원 이용의 효율성 및 장애 극복, 배포 및 유지보수의 편의성을 위해 둘을 분리한다