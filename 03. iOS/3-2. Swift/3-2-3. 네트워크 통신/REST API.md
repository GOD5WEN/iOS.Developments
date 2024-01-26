# Rest API 의 개념

> REST는 HTTP 프로토콜을 기반으로 하며, 클라이언트와 서버간의 통신을 위한 규칙을 정의 합니다.

<span style="color:red"> [GET] </span> http:// api.example.com :80<span style="color:green"> /users </span> 

<span style="color:red"> HTTP Methods </span> : REST API에서는 HTTP Methods 를 사용해 자원을 다뤄줍니다.

- GET : 자원을 읽기 위해서 사용 (ex.유저를 조회하기 위해)
- POST : 새로운 자원을 생성하기 위해 (ex.신규유저가 가입하여 생성되는경우) 멱등하지않음 = 여러번 요청할시 다른 자원을 생성
- PUT : 기존 자원을 업데이트 (ex.기존 유저에 대한 정보를 수정) 멱등함 = 여러번 요청해도 동일한 자원을 생성
- DELETE : 자원을 삭제하기 위해 (ex.유저가 탈퇴시)

- 이외에도 여러가지가 있다.

<span style="color:green"> Resources </span> : REST API에서 모든 데이터가 자원으로 표현된다. 이러한 자원은 고유한 식별자를 가지게 되는데 URI 로 표현한다. 일반적으로 웹사이트에 사용자 프로필,글,이미지,동영상 등은 각각의 고유한 자원으로 표현될수있음. URI는 자원을 찾을수 있는 주소를 나타냄

* URI과URL의 차이 : URI는 리소를를 식별하기 위한 일반적인 용어, URL은 리소스의 위치를 나타내는 구체적인 형태의 URI임 (URI가 큰 범주 URI의 주소를 URL로 표현)