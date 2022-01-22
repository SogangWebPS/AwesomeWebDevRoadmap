## Domain Name

```js
- 125.209.222.142
- 216.58.197.206
```

👉 위 두 가지 주소는 어디일까요?

- 바로 네이버와 구글의 ip 주소입니다.

- 인터넷 상에서 다른 단말에 접근하기 위해서는 고유 IP주소를 알아야하죠

- 하지만 보시다시피 바로 알아볼 수 없고 불편합니다.
    👍 그래서 기억하기 쉬운 영문, 숫자, 구분자(.)로 이루어진 `Domain Name이 등장`하게 되었어요.
    

### 도메인 네임 정의

- 넓은 의미 : 네트워크 상에서 `컴퓨터를 식별하는 호스트명`입니다.
- 좁은 의미 : 도메인 레지스트리에게서 등록된 이름입니다.
    - 도메인 레지스트리 : 최상위도메인에 등록된 모든 도메인 네임의 DB

## 도메인 구조

<img src="https://user-images.githubusercontent.com/32920566/150520071-8b1aa287-e207-4aad-a6bc-bda8461c2361.png" width="500"/>

<br>

> 1단계: 최상위 도메인 (TLD, Top-Level Domain)
 
  - 👍 도메인 레벨 중에 가장 높은 단계에 있는 도메인입니다. 도메인의 목적, 종류, 국가를 나타냅니다.
  - 상업적인 목적의 도메인(commercial → com),
  - 국가(kr)
  - 공인 단체(org)

> 2단계: 차상위 도메인 (SLD, Second-Level Domain)

  - 👍 호스트, 서브 도메인으로 불리기도 합니다. 보조 도메인으로써, URL로 전송하거나 계정 내의 IP주소나 디렉토리로 포워딩되는 도메인 이름의 확장자입니다.

> 3단계: 도메인 이름 (Domain Name)

  - 👍 임의로 지정할 수 있는 사이트의 이름입니다. google, naver 등 사용자에게 쉽게 기억될 수 있도록, 보통 서비스명으로 도메인명을 지정해 사용합니다.

---

## DNS (Domain Name Service)

- 출처 : <a href="https://opentutorials.org/course/3276/20303](https://opentutorials.org/course/3276/20303"> 생활코딩 </a>

### DNS란?

> Domain Name으로 IP 주소를 찾아주는 시스템입니다.

### DNS 동작 과정

> naver.com 을 브라우저에 입력하는 상황을 생각해봅시다.

<img src="https://user-images.githubusercontent.com/32920566/150520498-12fe1116-a9c2-4d31-bfec-c8744e53cfe4.png" width="500"/>

1. 브라우저에 naver.com을 입력합니다.

2. 로컬 DNS 서버에서 naver.com이라는 도메인 네임이 캐싱되어 있는지 확인합니다. 있으면 IP주소를 알려줍니다.

3. 캐싱이 되어 있지 않다면 Root DNS 서버에 도메인 네임 확인을 요청합니다.

4. Root DNS 서버는 해당하는 Top-Level 서버를 찾아줍니다.

5. Top-Level 서버는 해당하는 Second-Level 서버를 찾아줍니다.

6. Second-Level 서버는 해당하는 Sub DNS 서버에서 IP를 찾아서 알려줍니다.

7. 해당하는 도메인을 다시 방문하면 빠르게 찾기위하여 naver.com이라는 서버의 IP를 로컬 DNS 서버에 캐싱합니다.

---

## 요약

- URL 입력 후 사용자에게 보여지기 까지의 과정을 잘 표현한 이미지입니다.

<img src="https://user-images.githubusercontent.com/32920566/150520942-7d9efd26-8df3-4bad-ab92-47255efe7819.png" width="500" />