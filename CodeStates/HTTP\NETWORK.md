
학습 목표
클라이언트-서버 아키텍처를 이해할 수 있다.
HTTP를 이용한 클라이언트-서버 통신을 이해할 수 있다.
API의 개념을 이해할 수 있다.


1. client server architecture
> 2 Tier Architecture
<리소스를 사용하는 앱> <--인터넷--- <리소스가 존재하는 곳>
클라이언트                      서버

<클라이언트> --요청->  <서버>
<클라이언트> <-응답--  <서버>

> 3 Tier Architecture

<프론트앤드>         <백앤드>
<리소스를 사용하는 앱> <리소스를 전달해주는 앱> <리소스저장공간>
<클라이언트> --요청->  <서버> --> <데이터베이스>
<클라이언트> <-응답--  <서버> <-- <데이터베이스>

2. 클라이언트 서버 통신과 API
클라이언트와 서버가 서로 HTTP라는 프로토콜을 사용해 대화를 나눈다
HTTP를 이용해 주고받는 메시지는 "HTTP 메시지"라고 부릅니다.
`OSI 7 Layers`
HTTP
HTTPS
FTP
SMTP
SSH
RDP
WebSocket

TCP
UDP

2-1. API
API(Application Programming Interface)입니다. 서버는 클라이언트에게 리소스를 잘 활용할 수 있도록 인터페이스(interface)를 제공해 줘야 합니다. 이것을 API라고 합니다.

쉽게 스타벅스를 예를 들어 생각해 보면, 메뉴판과 같은 역할을 한다고 볼 수 있습니다. 

클라이언트가 스타벅스가 제공하는 자원의 종류(아메리카노, 콜드브루, 프라푸치노 등)를 모른다고 가정할 경우, 엉뚱한 메뉴(예를 들어 설렁탕)를 시키지 않도록 도와주어야 합니다. 

마찬가지로 서버가 리소스 전달을 위한 메뉴판, 즉 API를 구축해놓아야 클라이언트가 이를 활용할 수 있습니다. 

보통 인터넷에 있는 데이터를 요청할 때에는 HTTP라는 프로토콜을 사용하며, 주소(URL, URI)를 통해 접근할 수 있게 됩니다.

여기 스타벅스 API 서버가 제공하는 적절한 URL 디자인 예제를 첨부합니다. 파라미터를 사용하기 위해 물음표(?)와 & 기호를 사용하는 것을 참고하세요.

요청  URL 디자인 (ex)
아메리카노 한 잔 주세요 /coffee/americano
망고 프라푸치노 한 잔 주세요 /frappuccino/manggo
콜드브루 두 잔 주새요   /coffee/coldbrew?quantity=2
아메리카노 두 잔 전부 헤이즐넛 시럽 넣어주세요 /coffee/americano?quantity=2&syrup=hazelnet

quantity=2 syrup=hazelnet 이런 옵션들을 파라미터라고 부름

기억해야 할 다섯 가지 메서드
GET, POST, PUT(또는 PATCH), DELETE 
각각 조회, 추가, 갱신, 삭제와 관련이 있습니다. 메서드 설명은 MDN "HTTP 요청 메서드"를 참고

https://koreanjson.com



학습 목표
브라우저의 작동 원리를 이해할 수 있다.
보이지 않는 곳의 통신을 이해할 수 있다.
URL과 URI의 차이를 이해할 수 있다.
- URL은 Uniform Resource Locator의 줄임말로, 네트워크 상에서 웹 페이지, 이미지, 동영상 등의 파일이 위치한 정보를 나타냅니다. URL은 scheme, hosts, url-path로 구분할 수 있습니다.

- URI는 Uniform Resource Identifier의 줄임말로, 일반적으로 URL의 기본 요소인 scheme, hosts, url-path에 더해 query, bookmark를 포함

|부분|명칭|설명|
| - | -| - |
| file://, http://, https://	| scheme	| 통신 프로토콜 |
| 127.0.0.1, www.google.com	| hosts |	웹 페이지, 이미지, 동영상 등의 파일이 위치한 웹 서버, 도메인 또는 IP |
| :80, :443, :3000	| port |	웹 서버에 접속하기 위한 통로 |
| /search, /Users/username/Desktop	| url-path |	웹 서버의 루트 디렉토리로부터 웹 페이지, 이미지, 동영상 등의 파일이 위치까지의 경로 |
| q=JavaScript	|  query |	웹 서버에 전달하는 추가 질문 |

IP 주소와 PORT에 대해 이해할 수 있다.
- 네트워크에 연결된 특정 PC의 주소를 나타내는 체계를 IP address(Internet Protocol address, IP 주소)라고 합니다. 이번 콘텐츠에서는 네트워크 상에서 특정 PC를 나타내는 IP 주소와 그 주소에 진입할 수 있는 정해진 통로, PORT(포트)에 대해 학습

네 덩이의 숫자로 구분된 IP 주소체계를 IPv4라고 합니다. IPv4는 Internet Protocol version 4의 줄임말로, IP 주소체계의 네 번째 버전을 뜻함
000.000.000.000

PORT
로컬 PC의 IP 주소인 127.0.0.1 뒤에 :3000과 같은 숫자가 표현됩니다. 이 숫자는 IP 주소가 가리키는 PC에 접속할 수 있는 통로(채널)를 의미

22 : SSH
80 : HTTP
443: HTTPS

DNS와 IP 주소의 관계를 설명할 수 있다.

도메인 : www.codestates.com
IP주소 : 3.34.153.168

브라우저의 검색창에 도메인 이름을 입력하여 해당 사이트로 이동하기 위해서는 해당 도메인 이름과 매칭된 IP 주소를 확인하는 작업이 반드시 필요합니다. 네트워크에는 이것을 위한 서버가 별도로 있는데 이를 DNS(Domain Name System)이라고 합니다.

DNS는 호스트의 도메인 이름을 IP 주소로 변환하거나 반대의 경우를 수행할 수 있도록 개발된 데이터베이스 시스템입니다. 만약 브라우저의 검색창에 naver.com을 입력한다면, 이 요청은 DNS에서 IP 주소(ex.125.209.222.142)를 찾습니다. 그리고 이 IP 주소에 해당하는 웹 서버로 요청을 전달하여 클라이언트와 서버가 통신할 수 있도록 합니다

크롬 브라우저의 에러 메시지를 통해 문제를 파악할 수 있다.
| Error Message | Description |
| - | - |
|"Aw, Snap!" ("앗, 이런!")	|Chrome 브라우저에서 페이지를 로드하는 데 문제가 발생했습니다. |
|ERR_NAME_NOT_RESOLVED	|호스트 이름(웹 주소)이 존재하지 않습니다.|
|ERR_INTERNET_DISCONNECTED |	사용 중인 기기가 인터넷에 연결되지 않았습니다.|
|ERR_CONNECTION_TIMED_OUT ERR_TIMED_OUT	| 페이지에 연결하는 데 시간이 너무 오래 걸립니다. 인터넷 연결이 너무 느리거나, 웹페이지에 접속한 사용자가 많아서 발생할 수 있습니다. |
|ERR_CONNECTION_RESET	|웹페이지 연결을 방해하는 요소가 어딘가에 발생했습니다. |
|ERR_NETWORK_CHANGED	|웹페이지를 로드하는 중에 기기의 네트워크 연결이 해제되었거나, 새로운 네트워크에 연결되었습니다. |
|ERR_CONNECTION_REFUSED |	웹페이지에서 Chrome 브라우저의 연결을 허용하지 않았습니다. |
|ERR_CACHE_MISS |	웹페이지로부터 이전에 입력한 정보를 다시 한번 제출하도록 요청받았습니다. |
|ERR_EMPTY_RESPONSE	|웹페이지에서 데이터를 전혀 전송하지 않았으며, 데이터를 전송할 서버가 다운되었을 수 있습니다. |
|ERR_SSL_PROTOCOL_ERROR	|페이지에서 전송된 데이터를 Chrome 브라우저가 해석하지 못했습니다. |
|ERR_BAD_SSL_CLIENT_AUTH_CERT|	클라이언트 인증서(은행 또는 회사 내부 웹사이트 등)에 오류가 발생하여 웹페이지에 로그인할 수 없습니다.|


1. HTTP의 동작 방식을 이해할 수 있다.

HTTP Messages는 클라이언트와 서버 사이에서 데이터가 교환되는 방식입니다. HTTP Messages에는 다음과 같은 두 가지 유형이 있습니다.

요청(Requests)
응답(Responses)

2. HTTP Messages의 구조를 설명할 수 있다.
요청(Requests)과 응답(Responses)은 다음과 같은 유사한 구조를 가집니다.

start line : start line에는 요청이나 응답의 상태를 나타냅니다. 항상 첫 번째 줄에 위치합니다. 응답에서는 status line이라고 부릅니다.
HTTP headers : 요청을 지정하거나, 메시지에 포함된 본문을 설명하는 헤더의 집합입니다.
empty line : 헤더와 본문을 구분하는 빈 줄이 있습니다.
body : 요청과 관련된 데이터나 응답과 관련된 데이터 또는 문서를 포함합니다. 요청과 응답의 유형에 따라 선택적으로 사용합니다.
이 중 start line과 HTTP headers를 묶어 요청이나 응답의 헤드(head)라고 하고, payload는 body라고 이야기합니다.

Stateless는 말 그대로 상태를 가지지 않는다는 뜻입니다. HTTP로 클라이언트와 서버가 통신을 주고받는 과정에서, HTTP가 클라이언트나 서버의 상태를 확인하지 않습니다. 사용자는 쇼핑몰에 로그인하거나 상품을 클릭해서 상세 화면으로 이동하고, 상품을 카트에 담거나 로그아웃할 수도 있습니다. 클라이언트에서 발생한 이런 모든 상태를 HTTP 통신이 추적하지 않습니다. 만약 쇼핑몰에서 카트에 담기 버튼을 눌렀을 때, 카트에 담긴 상품 정보(상태)를 저장해둬야 합니다. 그러나 HTTP는 통신 규약일 뿐이므로, 상태를 저장하지 않습니다. 따라서 필요에 따라 다른 방법(쿠키-세션, API 등)을 통해 상태를 확인할 수 있습니다. 이 방법은 섹션 3에서 보다 자세하게 다룹니다.

지금은 Stateless(무상태성)가 HTTP의 큰 특징이라고 기억하는 것으로 충분합니다.

3. HTTP Requests와 Responses를 구분할 수 있다.

HTTP Requests는 클라이언트가 서버에게 보내는 메시지입니다. 

Start line에는 세 가지 요소가 있습니다.

1. 수행할 작업(GET, PUT, POST 등)이나 방식(HEAD or OPTIONS)을 설명하는 HTTP method를 나타냅니다. 예를 들어 GET method는 리소스를 받아야 하고, POST method는 데이터를 서버로 전송합니다.
2. 요청 대상(일반적으로 URL이나 URI) 또는 프로토콜, 포트, 도메인의 절대 경로는 요청 컨텍스트에 작성됩니다. 이 요청 형식은 HTTP method 마다 다릅니다.
- origin 형식 : '?'와 쿼리 문자열이 붙는 절대 경로입니다. GET, POST, HEAD, OPTIONS 등의 method와 함께 사용합니다.
POST / HTTP 1.1
GET /background.png HTTP/1.0
HEAD /test.html?query=alibaba HTTP/1.1
OPTIONS /anypage.html HTTP/1.0
- absolute 형식 : 완전한 URL 형식으로, 프록시에 연결하는 경우 대부분 GET method와 함께 사용합니다.
GET http://developer.mozilla.org/en-US/docs/Web/HTTP/Messages HTTP/1.1
- authority 형식 : 도메인 이름과 포트 번호로 이루어진 URL의 일부분 입니다. HTTP 터널을 구축하는 경우, CONNECT와 함께 사용할 수 있습니다.
CONNECT developer.mozilla.org:80 HTTP/1.1
- asterisk 형식 : OPTIONS 와 함께 별표(*) 하나로 서버 전체를 표현합니다.
OPTIONS * HTTP/1.1

요청의 Headers는 기본 구조를 따릅니다. 

- General headers : 메시지 전체에 적용되는 헤더로, body를 통해 전송되는 데이터와는 관련이 없는 헤더입니다.
- Request headers : fetch를 통해 가져올 리소스나 클라이언트 자체에 대한 자세한 정보를 포함하는 헤더를 의미합니다. User-Agent, Accept-Type, Accept-Language와 같은 헤더는 요청을 보다 구체화합니다. Referer처럼 컨텍스트를 제공하거나 If-None과 같이 조건에 따라 제약을 추가할 수 있습니다.
- Representation headers : 이전에는 Entity headers로 불렀으며, body에 담긴 리소스의 정보(콘텐츠 길이, MIME 타입 등)를 포함하는 헤더입니다.

 모든 요청에 body가 필요하지는 않습니다. GET, HEAD, DELETE, OPTIONS처럼 서버에 리소스를 요청하는 경우에는 본문이 필요하지 않습니다. POST나 PUT과 같은 일부 요청은 데이터를 업데이트하기 위해 사용합니다. body는 다음과 같이 두 종류로 나눌 수 있습니다.

- Single-resource bodies(단일-리소스 본문) : 헤더 두 개(Content-Type과 Content-Length)로 정의된 단일 파일로 구성됩니다.
- Multiple-resource bodies(다중-리소스 본문) : 여러 파트로 구성된 본문에서는 각 파트마다 다른 정보를 지닙니다. 보통 HTML form과 관련이 있습니다.


3. HTTP 버전에 따라 HTTP message의 구조가 달라집니다. 따라서 start line에 HTTP 버전을 함께 입력합니다.

4. HTTP의 응답 메시지를 찾아볼 수 있다.


## REST API

 1-1. REST

- Representational State Transfer

1-2. REST API

- 웹에서 사용되는 데이터나 자원(Resource)을 HTTP URI로 표현하고, HTTP 프로토콜을 통해 요청과 응답을 정의하는 방식

## REST 성숙도 모델

### 2-1. 0단계

- 단순히 HTTP 프로토콜을 사용하는 것

### 2-2. 1단계

- 개별 리소스(Resource)와의 통신을 준수
- 개별 리소스에 맞는 엔드포인트(Endpoint)를 사용해야하며 요청하고 받는 자원에 대한 정보를 응답으로 전달해야 한다는 것이 1단계의 핵심
- **엔드포인트** 작성 시에는 **명사** 형태의 단어로 작성하는 것이 바람직한 방법

### 2-3. 2단계

- CRUD(Create, Read, Update, Delete)에 맞게 적절한 HTTP 메서드를 사용하는 것에 중점
- 멱등([idempotent](https://developer.mozilla.org/en-US/docs/Glossary/Idempotent)) : 매 요청마다 같은 리소스를 반환하는 특징

참고 )

- 2단계까지 적용하면 대체적으로 잘 작성된 API
- 3단계까지 무조건적으로 모두 적용해야 하는 것은 아님.

### 2-4. 3단계

- **HATEOAS(Hypertext As The Engine Of Application State)** 하이퍼미디어 컨트롤을 적용
- 응답에는 리소스의 URI를 포함한 **링크**
 요소를 삽입하여 작성


## 3. Open API

- 누구에게나 열려있는 API
- 다. API마다 정해진 이용 수칙이 있고, 그 이용 수칙에 따라 제한사항(가격, 정보의 제한 등)이 있을 수 있음

## 4. API Key

- API를 이용하기 위해서는 **API Key**
가 필요
- API Key가 필요한 경우에는 로그인한 이용자에게 자원에 접근할 수 있는 권한을 API Key의 형태로 제공하고, 데이터를 요청할 때 API key를 같이 전달해야 원하는 응답을 받을 수 있음