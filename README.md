# HTTP (HyperText Transfer Protocol)

텍스트 기반의 통신 규약으로 인터넷에서 데이터를 주고받을 수 있는 프로토콜이다. 이렇게 규약을 정해두었기 때문에 모든 프로그램이 이 규약에 맞춰 개발해서 서로 정보를 교환할 수 있게 되었다.

### HTTP 동작
클라이언트 즉, 사용자가 브라우저를 통해서 어떠한 서비스를 url을 통하거나 다른 것을 통해서 요청(request)을 하면 서버에서는 해당 요청사항에 맞는 결과를 찾아서 사용자에게
응답(response)하는 형태로 동작한다.

- 요청: client -> server
- 응답: server -> client

HTML 문서만이 HTTP 통신을 위한 유일한 정보 문서는 아니다.
Plain text로 부터 JSON 데이터 및 XML과 같은 형태의 정보도 주고 받을 수 있으며, 보통은 클라이언트가 어떤 정보를 HTML 형태로 받고 싶은지, JSON 형태로 받고 싶은지 명시해주는 경우가 많다.

### HTTP 특징 `(무상태, 비 연결성)`

- HTTP 메세지는 HTTP 서버와 HTTP클라이언트에 의해 해석이 된다.
- TCP / IP를 이용하는 응용 프로토콜이다.
- HTTP는 연결 상태를 유지하지 않는 비연결성 프로토콜이다. (무상태 : stateless)
- HTTP는 연결을 `유지하지 않는 프로토콜`이기 때문에 `요청/응답` 방식으로 동작한다. 
- 단순함, 확장 가능하다.

![post-images_surim014_e0aa5520-2d59-11ea-86da-fb3b00230640_image](https://user-images.githubusercontent.com/117972533/222147557-5cc0778d-cf1d-45b1-94ac-b5bb4372b0a1.png)

### Request (요청)
```
GET https://velog.io/moka31 HTTP/1.1	                        // 시작줄
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) ...			  // 헤더
Upgrade-Insecure-Requests: 1
```

#### 시작줄
시작줄은 `메서드, 구조, 버전` 으로 구성되었다.
- GET : HTTP Method
- https://velog.io/moka31 : 사이트 주소
- HTTP/1.1 : HTTP 버전

#### 헤더 (두 번쨰 줄부터)
두번째 줄부터는 헤더이며 `요청에 대한 정보`를 담고 있다. User-Agent, Upgrade-Insecure-Requestes 등등이 헤더에 해다되며 헤더의 종류는 매우 많다.

#### 본문 (헤더에서 한 줄 띄고)
본문은 `요청을 할 때 함께 보낼 데이터를 담는 부분`이다. 현재 예시에는 단순히 주소로만 요청을 보내고 있고 따로 데이터를 담아 보내지 않기 때문에 본문이 비어있다.

### Response (응답)
server가 요청에 대한 답변을 client에게 보내는 것을 응답이라고 한다.
```
HTTP/1.1 200 OK														// 시작줄
Connection: keep-alive												 // 헤더
Content-Encoding: gzip												 
Content-Length: 35653
Content-Type: text/html;

<!DOCTYPE html><html lang="ko" data-reactroot=""><head><title...
```

#### Status Code (상태 코드)
상태 코드에는 굉장히 많은 종류가 있다. 모두 숫자 세 자리로 이루어져 있으며, 아래와 같이 크게 다섯 부류로 나눌 수 있다.

- 1XX (조건부 응답) : 요청을 받았으며 작업을 계속한다.
- 2XX (성공) : 클라이언트가 요청한 동작을 수신하여 이해했고 승낙했으며 성공적으로 처리했음을 알린다.
- 3XX (리다이렉션 완료) : 클라이언트는 요청을 마치기 위해 추가 동작을 취해야 한다.
- 4XX (요청 오류) : 클라이언트에 오류가 있음을 나타낸다.
- 5XX (서버 오류) : 서버가 유효하 요청을 명백하게 수행하지 못했음을 나타낸다.


---
참조
- https://velog.io/@geeneve/2021-%EB%B0%B1%EC%97%94%EB%93%9C-%EA%B0%9C%EB%B0%9C%EC%9E%90-%EB%A1%9C%EB%93%9C%EB%A7%B5
