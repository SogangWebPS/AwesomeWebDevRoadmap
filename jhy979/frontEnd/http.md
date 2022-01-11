- **HTTP Request 종류와 HTTP Response 종류에 대해 학습하고 정리한다.**
# HTTP

## HTTP vs HTTPS

> 💡 **HTTP** (Hypertext Transfer Protocol)

- 서로 다른 시스템들 사이에서 통신을 주고받게 해주는 가장 기초적인 프로토콜입니다. 

- 웹 서핑을 할 때 **서버에서 유저의 브라우저로 데이터를 전송**해 주는 용도로 가장 많이 사용됩니다. 

- 인터넷의 초기에 모든 웹사이트에서 기본적으로 사용되었던 프로토콜이기도 합니다.

> 💡 **HTTPS(Hypertext Transfer Protocol Secure)**
- 일반 HTTP 프로토콜의 문제점은 서버에서부터 브라우저로 전송되는 정보가 암호화되지 않는다는 것입니다.

- **HTTPS 프로토콜은 SSL(보안 소켓 계층)을 사용함**으로써 이 문제를 해결했습니다.

- SSL은 서버와 브라우저 사이에 안전하게 암호화된 연결을 만들 수 있게 도와주고, 서버 브라우저가 민감한 정보를 주고받을 때 이것이 도난당하는 것을 막아줍니다.

---

## HTTPS의 장점

> 👉 보안성
    
- **SSL 인증서**는 사용자가 사이트에 제공하는 정보를 암호화하는데, 쉽게 말해서 **데이터를 암호**로 바꾼다고 생각하면 쉽습니다. 

- 이렇게 전송된 데이터는 중간에서 누군가 **훔쳐 낸다고** 하더라도 데이터가 암호화되어있기 때문에 **해독할 수 없습니다.** 

- **TLS(전송 계층 보안) 프로토콜**을 통해서도 보안을 유지합니다. 

- TSL은 데이터 **무결성을 제공**하기 때문에 데이터가 전송 중에 **수정**되거나 **손상**되는 것을 **방지**하고, 사용자가 자신이 의도하는 웹사이트와 통신하고 있음을 입증하는 **인증 기능**도 제공하고 있습니다.

> 👉 검색엔진 최적화(SEO)
    
- 구글이 HTTPS 웹사이트에 가산점을 주기 때문입니다.

- 사용자들이 안전하다고 생각하는 사이트를 더 많이 방문하기 때문이기도 합니다.
    
> 👉 가속화된 모바일 페이지(AMP, Accelerated Mobile Pages)
    
- 💡 AMP는 모바일 기기에서 훨씬 **빠르게 콘텐츠를 로딩** 하기 위한 방법으로 구글이 만든 것입니다.
    
- HTML에서 **불필요**한 부분을 **없앤 것**이라고 볼 수 있습니다. 

- 구글의 SERP(검색 결과 페이지)를 보면 스마트폰과 태블릿의 사용자들이 **모바일에서** 사용하기 편하도록 **AMP 콘텐츠**들이 두드러져 보이는 것을 볼 수 있습니다

- **모바일 친화**적인 웹사이트를 만드는 것과 모바일 검색순위 및 지역에 SEO를 증가시키는 것이 점점 **더 중요**해지고 있는 요즘, HTTP를 **HTTPS로 전환하는 것이 필수**라고 볼 수 있습니다.

(출처 : [http://blog.wishket.com/http-vs-https-차이-알면-사이트의-레벨이-보인다/](http://blog.wishket.com/http-vs-https-%EC%B0%A8%EC%9D%B4-%EC%95%8C%EB%A9%B4-%EC%82%AC%EC%9D%B4%ED%8A%B8%EC%9D%98-%EB%A0%88%EB%B2%A8%EC%9D%B4-%EB%B3%B4%EC%9D%B8%EB%8B%A4/))

---

## HTTP Resquest란?

<img src="https://user-images.githubusercontent.com/32920566/148895127-876cce31-a351-4a4e-b895-83a92d1272b3.png" width="400"></img>

> 💡 클라이언트가 웹 서버에게 사용자 요청의 목적/종류를 알리는 수단입니다.

---

## HTTP Request Method 종류

> 대표적으로 GET, POST가 있습니다.

- GET : URL속 정보를 검색하기 위한 요청

- POST:  URL에 폼 입력을 처리하기 위해 데이터 부분에 요청 정보 삽입을 한 요청

- HEAD: GET과 유사하지만 돌려받는 데이터는 헤더뿐 

- OPTIONS: 지원되는 메소드 체크

- PUT: POST와 유사, 헤더 이외 정보 받음

- DELETE: 원격 웹 서버에 파일을 삭제

- TRACE: 원격 서버에 Loopback 메세지를 호출

- CONNECT: 웹 서버에 프록시 기능을 요청

---

## HTTP Response Code 종류

|status code|설명|예시|
|--|--|--|
|1??|	처리 중|	100 Continue|	
|2??|	성공|	200 OK	|
|3??|	리다이렉트|	300 Mutiple Choices	|
|4??|	클라이언트 오류|	400 Bad Request|	
|5??|	서버 오류|	500 Internal Server Error|	

> 우리가 자주보는 404 에러는 `서버 오류라고 생각하시는 분들도 계시겠지만, 해당 오류는 서버 자체는 존재하지만 서버에서 요청한 것을 찾을 수 없을 때 나타납니다.`

---

## HTTP Proxy
    
> 💡 클라이언트와 서버 사이에 위치하여 HTTP 메세지의 중개인 역할을 합니다.

<img src="https://user-images.githubusercontent.com/32920566/148895366-d9079307-9c48-4e9c-becd-edd48012c7ff.png" width="500"></img>

- 빠른 속도

- 보안 Good

- 접속 우회 가능
    
---

## HTTP/2 vs HTTP/3 규격

> 출처 : [https://cottonblue.tistory.com/29](https://cottonblue.tistory.com/29)


👉 HTTP/2 와 HTTP/3 의 가장 큰 차이점은 기존 HTTP/2가 TCP 위에서 동작한 것과 달리 HTTP/3 은 `UDP` 에서 동작한다는 것입니다.

👉 구글에서 TCP로 인해 생긴 병목을 해결하기 위해 만든 UDP 기반의 QUIC 이 HTTP/3 으로 들어오면서 생긴 변화입니다.