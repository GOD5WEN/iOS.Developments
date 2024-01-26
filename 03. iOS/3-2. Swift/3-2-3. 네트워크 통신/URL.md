# URL 의 구성 요소

 >[!example]
 ><span style="color:red"> http:// </span>  <span style="color:orange"> api.example.com </span> <span style="color:#ffd33d"> :80 </span>   <span style="color:green"> /users </span>   <span style="color:blue"> ?page=2$sort=desc </span>

 <span style="color:red"> Protocol </span> : 일반적으로 http 혹은 https 두가지 프로토콜을 가지고 있다. <br> 클라이언트와 서버간의 통신 방법 지정하는 요소 

<span style="color:orange"> Domain </span> : api 서버가 호스팅되는 서버의 주소

<span style="color:#ffd33d"> Port </span> : 서버에서 api 요청을 수신하는 포트 http는 80, https는 443을 사용한다. (URL에서 일반적으로 생략함)

<span style="color:green"> Path </span> : 경로를 나타냄, 서버에서 요청된 자원이나, 위치를 나타냄. 경로는 엔드포인트와 연관되어 특정 자원이나 서비스를 식별한다.

<span style="color:blue"> Query Parameters </span> : 쿼리 매개변수. URL의 추가정보를 전달하기 위해 사용됨, 위예시는 사용자가 원하는 페이지 번호나 정렬 방법을 서버에 전달하여 리소스를 가져올수 있음
