# HTTP (Hypertext Transfer Protocol)

- 서버-클라가 인터넷에서 데이터를 주고받기 위한 프로토콜(통신 규약)
- 이미지, 동영상, 텍스트 등 데이터 종류 상관없이 전송 가능
- 가장 보편적으로 사용하는 버전은 http 1.1 (현재 2까지 나옴)
- 기본 포트는 80

## HTTP 특징
- 클라에서 서버에게 요청 -> 서버에서 요청을 받아 처리후 응답
- 서버가 클라의 요청을 처리하고나면 연결을 끊기 때문에 상태를 전혀 알수 없음  
-> 무상태(stateless)  
-> 이때문에 정보를 유지하기 위해 쿠키가 생김

## URL
- 특정 웹 서버의 파일(또는 리소스)에 접근하기 위한 주소

## HTTP 구조
### request (요청)
- 요청 헤더 - 요청 메소드(GET, POST 등), 요청 URL
- 요청 바디 - 서버에 보낼 리소스 (GET은 보통 바디에 안넣고 URL로만 보내고, POST를 쓸 때 바디에 데이터 같이 넣어서 보냄)
### response (응답)
- 응답 헤더 - 응답 코드, 응답 메시지 (ex] 404 not found)  
- 응답 바디 - HTTP 바디에 응답 데이터가 함께 보내짐

## HTTP 버전별 특징
### http 0.9  
- request -> GET /page.html  
- response -> html 바디 (헤더 존재x)

### http 1.0  
- request 에 http 버전 표기, response에 헤더 추가 (응답 코드, 메시지, Content-Type 등)  
- 연결 한번당 1 request 1 response 방식 -> 속도 느림, 서버 비용 증가

### http 1.1  
- 1.0 에서 파이프라이닝(Pipelineing) 기법 추가  
- 하나의 연결에서 요청을 연속적으로 보내서 순차적으로 처리하여 응답을 보냄  
- 첫번째 요청의 처리가 너무 오래 걸리면 자연적으로 뒤의 요청도 밀리기 때문에 속도 저하 가능성 있음 (Head Of Line Blocking)
- 헤더 중복

### http 2.0  
- 1.1 에서 성능 향상을 목적으로 함  
- 보내는 데이터(헤더, 바디)를 텍스트가 아닌 바이너리 프레임으로 분할하여 전송  
└> 전송속도 올라감, 오류 가능성 적어짐  
- 요청/응답시 바이너리 프레임 단위로 보내기 때문에 프레임 단위로 응답에 끼어들 수 있음  
└> 1.1에서 발생했던 Head Of line Blocking 해결  
- 리소스간 우선순위 지정 가능  
- 헤더 압축  



# HTTPS (Hypertext Transfer Protocol Secure)
- HTTP의 보안이 강화된 버전
- SSL 인증서를 통해 신뢰할 수 있는 http 통신을 보장
- SSL은 두가지 암호화 기법을 사용 - 대칭키, 공개키  

※ 대칭키, 공개키를 이용한 암호화 통신 방식은 아래 유튜브를 참고하장

참고 - https://www.youtube.com/watch?time_continue=42&v=dabaJY3Q3Og&feature=emb_logo&ab_channel=%EC%83%9D%ED%99%9C%EC%BD%94%EB%94%A9




