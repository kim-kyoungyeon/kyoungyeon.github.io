설날에도 공부하는 나 칭찬해
![](https://images.velog.io/images/ww3ysq/post/64ae498a-2c0a-4690-8ce7-3189a71df839/image.png)

~~백수라 그런지 집에선 나이 대신 욕이나 처먹고 있다~~

# 학습목표

- 토큰의 개념을 안다
- jwt 토큰의 의의/ 종류를 파악한다
- oauth와의 차이를 파악한다
- server에서 sign in signout 등의 기능 구현에 대해 파악한다

## 토큰?

통행증 회원증 입장 티켓권 (뜯어서 준다)
회원이 반을 갖고 서버가 나머지 반을 갖는개념
클라이언트로 로그인시 서버에서 인증을 거친후 토큰을 내어준다
다음부터 서버에 요청시 토큰을 같이 보내어 인증을 가진다
가장 대표적인 토큰기반 jwt
accesstoken refreshtoken 등이 있다.

## jwt 종류

accesstoken 짧다 (exp)

> 권한을 가질수 있게 해주는 부여에 사용
> 클라잉너트가 처음 인증을 받게 될 때 사용 (로그인시)

refresh token(위 어세슷 토큰 이중보안) 길다 (exp)

> 만료시 로그인 풀림
> 액세스 토큰을 새로 발급
> 유저는 다시 로그인 할 필요 없다

jwt 구조

> 3구조
> header/ payload/signature
> header : 어떤종류의 토큰? sha256로 암호화할 algo 가 적혀있따.

> payload : 기타 정보 ( 정보 접근 가능한지 대한 권한을 담는다)
> 사용자의 유저이름 등 필요데이터 이곳에 담아 암호화
> 암호화 (헤더에서 정의)가 될 정보, 민감한 정보는 되도록 X

> signature : base64 인코딩 된 첫번째, 그리고 두번째 부분이 완성시 원하는 비밀 키 (암호화에 추가할 salt)를 사용해 암호화한다.

## 인증 정보 어디 저장됨?

session -> server 세션스토어 + 클라이언트 session id 가 담긴 쿠키 에 저장
token -> 클라이언트 authorization header에 저장

토큰 파생 특징
서버 여러대 -> 서비스가 수평확장 / 로드 밸런싱인 경우 -토큰 유리 ( 확장성이 좋다)
로드밸런싱?

새션 -> 인증정보 여러서버가 공유해야함 /클라이언트 인증시 서버의 부담이 없다

어떻게 jwt 안전한가?
signature : 서명 salt 포함해 토큰 암호화

서버가 해야할 일 : salt , 서버검정 verify 가능해야함

## 토큰기반 인증 장점

1 ) stateless , scalablity 무상태 /확장성
서버 클라이언트 에대한 저장 X 토큰을 decoding한다
클라이언트 는 새로운 요청 보낼때마다 토큰을 헤더에 포함하기만 하면 ok
서버를 여러개 가진 서비스라면 더더욱 빛을 발함 (같은 토큰으로 여러 서버에서 인증가능 - 공동인증서 같은?)

2 ) 안전하다
암호화 한 토큰 사용, 암호화 키를 노출할 필요가 없다 publickey 개념 cert.pem

3. 어디서나 생성 && 다양한 활용
   토큰을 확인하는 서버가 토큰을 만들어야 하는 법 없음 / 토큰 생성용 서버를 만들거나 다른 회사에서 토큰 관련 작업을 맡기는 등..

4. 권한 부여에 용이
   토큰의 payload (내용물)jwt 중간/ 안에 어떤 정보에 접근 가능한지 정할수 있다. (서비스 사진과 연락처사용권한만 부여가능)