# 쓰기쉬운 코드보단 읽기 쉬운코드

![증사.jpeg](img/%EC%A6%9D%EC%82%AC.jpeg)

### Contact.

Email. k01066624566**@gmail.com**

Phone. **010-6662-4566**

### Channel.

GitHub. [https://github.com/dolong2](https://github.com/dolong2)

**portfolio.** [https://deadpan-climb-1a7.notion.site/fefd8a72c3694f2bacb5f5bef91af748](https://www.notion.so/fefd8a72c3694f2bacb5f5bef91af748)

---

# Introduce.

- spring boot를 사용해 java와 kotlin으로 개발하는걸 좋아합니다.
- 개발자가 편하게 작성하는 코드보다 편리하게 사용하는 코드를 작성하기 위해 노력합니다.
- 꾸준하게 성장하는것에 가치를 둡니다.
- 조직이 발전할 수 있는 토의하는걸 좋아합니다.
- 끈기가 사람을 성장 시킨다고 생각합니다.

---

# Work Experience.

## [GAuth](https://gauth.co.kr)

> GAuth는 새로운 서비스가 나올때마다 학생들이 새로운 계정을 만들어야하는 불편함을 해결하는 서비스입니다.
> 

> 해당 프로젝트를 진행하면서 OAuth시스템에대한 이해를 높일 수 있었습니다.
해당 프로젝트에선 github actions를 이용해서 ci/cd를 구축했습니다.
빌드와 배포가 자동화가 됨에 따라
> 

[GAuth Backend](https://github.com/GSM-MSG/GAUTH_BackEnd)

2022.07.29 - 2023.01.29

- 예외 처리
    - BasicException을 만들고 이를 상속한 하위 exception들을 개발
        - 이렇게 하면 `@ExceptionHandler(BasicException.class)` 인 exceptionHandler만 만들어도 BasicException하위 exception들을 쳐리할 수 있다
- excelParsing
    - admin권한을 가진 유저만 실행할 수 있는 API
    - 학생정보를 채우기 위해 학생정보 엑셀을 파싱할 수 있는 로직 개발
- 메일 인증
    - redis로 구현
    - 코드를 uuid기반으로 생성한 코드가 있는 uri로 요청보내는 버튼을 메일로 보낸다
    - 서버에선 요청(메일인증)온 코드가 유효한지 확인하고 유효하면 해당메일을 인증됨 상태로 변경
    - 이미 인증된 메일은 다시 못 보내게끔 개발
- 로그를 남길수 있게 해주는 커스텀 어노테이션
    - java reflection과 spring eventListener를 사용해서 해당 클래스에 있는 log라는 이름의 필드에 Logger를 주입 시켜주는 어노테이션
    - @Transactional이 붙으면 AOP때문에 안되는듯
- Oauth2.0적용
    - 클라이언트에서 oauth로그인 요청이 오면 email이랑 password비교해서 code발급
    - 클라이언트는 발급받은 code로 accessToken요청
    - accessToken과 refreshToken발급
    - 일반 accessToken과 refreshToken과 oauth 전용 accessToken과 refreshToken을 분리
- S3를 이용해서 프로필 업로드 기능 개발
    - 프로필 이미지도 있으면 좋을거 같다는 의견을 반영해서 이미지 업로드 추가
- 비밀번호 찾기(재설정) 개발
    - 비밀번호를 재설정하는 api 개발
        - 로그인이 되어있을때
        - 로그인이 안되어있을때
- 리소스 서버 개발
- 자바 기반 환경에서 사용할 수 있는 라이브러리 개발
- GAuth accessToken으로 토큰을 발급해주는 API
    - 프론트에서 자동 로그인을 하기위한 API

---

## [GAuth-sdk-java](https://github.com/GSM-MSG/GAuth-SDK-Java)

> GAuth를 자바 기반에서 이용할 수 있게끔 만든 라이브러리
> 

> 해당 프로젝트를 진행하면서
> 

[GAuth-SDK-JAVA v1.0.0](https://github.com/GSM-MSG/GAuth-SDK-Java/releases/tag/v1.0.0)

2023.01.02 - 2023.01.20
- 코드 발급
    - 이메일과 비밀번호를 매게변수로 받아서 코드를 발급한다
- 토큰 발급
    - 코드, 클라이언트 id, 클라이언트 시크릿, 리다이렉트 uri를  사용해서 토큰을 발급한다.
    - 이메일, 비밀번호, 클라이언트 id, 클라이언트 시크릿, 리다이렉트 uri를  사용해서 토큰을 발급한다.
        - 내부에서 코드발급 메서드 호출
- 토큰 재발급(리프레시)
    - 발급받은 리프레시 토큰으로 토큰을 재발급 받는다.
- 유저 정보 가져오기
    - 발급받은 엑세스 토큰으로 유저정보를 받아온다.

[GAuth-SDK-JAVA v1.0.1](https://github.com/GSM-MSG/GAuth-SDK-Java/releases/tag/v1.0.1)

2023.01.25
- 상태코드를 담아서 예외를 던지도록 수정

[GAuth-SDK-JAVA v2.0.0](https://github.com/GSM-MSG/GAuth-SDK-Java/releases/tag/v2.0.0)

2023.01.25
- GAuth를 인터페이스와 구현체로 분리
    - 플로우가 완전히 바뀌었기 때문에 2.0.0으로 버전업
    - 테스트하는데 불편함이 있다는 의견을 반영해서 분리함
    

---

## GAuth-resource (private)

> GAuth 리소스 서버
> 

V1

2022.11.21 - 2022.12.30

- 유저 정보를 가져오는 API
    - GAuth 서버에서 발급받은 oauth토큰으로 유저 정보를 가져옴
    - 요청하면 토큰 검증후 해당 유저 정보를 반환
    

---

## [GCMS](https://gcms.msg-team.com/)

> GCMS는 GSM Club Management Service의 약자로 교내 동아리 신청이나 방과후 신청을 관
리할 수 있는 서비스입니다
> 

Back-end-V1

2022.03.19 - 2022.06.30

- 간단하게 코드 리뷰와 코드 리펙토링에 참여
- 개발은 끝냈지만 동아리 신청 기간이 아니라 배포할 시기를 놓쳐서 유지보수 후 다음 연도에 배포를 기약

[Back-end-V2](https://github.com/GSM-MSG/GCMS-BackEnd)

2023.01.25 - ing

- v2는 기존에 spring(java) + nest.js로 작성되어있던 백엔드 코드를 spring(kotlin)으로 마이그레이션하는 작업부터 시작
- SecurityContext에서 가져온 인증객체로 유저 가져오는 객체 개발
- 동아리 생성 API 개발
    - 자율/전공 동아리 구성원은 생성할 수 없어야 한다는 요구사항
        - 동아리를 따로 따로 구성했으면 자율 전공 동아리 생성 로직에만 추가하면 되지만, 동아리 분류가 enum으로 되어있어서 곤란했음
    - 테스트 코드 작성
        - kotest
        - mockk
- 유저 id를 binary(16)으로 변경
    - mysql에서 uuid는 binary(16)으로 저장함
    - jpa에서는 BINARY(255)로 저장함
    - 유저 id를 `@Column(columnDefinition = BINARY(16))` 으로 설정
- 동아리 수정 API 개발
    - toEntity할때 id 없이 엔티티를 생성해서 동아리가 복사되는 버그가 있었음
        - 내부 테스트에서 발견하고 수정함
- 동아리 신청 마감 API 개발
- 동아리 탈퇴 API 개발
- 동아리 삭제 API 개발
- 부장 위임 API 개발
    - 부원 목록이 `mutableList`라면 `.add` 메서드와 `.remove` 메서드를 사용해서 편하게 할 수 있었지만 `list` 로 작성해서 부원 엔티티를 save시켜서 db에 저장하는 방식으로 작성
- 동아리 신청 API 개발
- 동아리 신청 취소 API 개발
- 동아리 구성원을 엑셀로 보내는 API 개발
    - poi라이브러리 사용
    - 반마다 학생들이 어떤 동아리에 소속되어있는지 볼 수 있는 엑셀
    - 동아리마다 어떤 학생들이 소속되어있는지 볼 수 있는 엑셀
- 다중 로그인 구현
    - 기존 RefreshToken엔티티는 userId를 @Id로 잡고 있어서 다른 플렛폼에서 로그인을 진행하면 기존의 refreshToken값은 사라지고 새로 만든 refreshToken으로 업데이트 시켰음
    - 하지만 플랫폼이 3개인 gcms특성상 다중로그인이 필요했음
    - @Id를 token value값에 설정해서 로그인과 리프레시 요청이 들어올때마다
- fcm으로 푸시알람 구현
    - https://github.com/GSM-MSG/GCMS-BackEnd/issues/178
    - 해당 케이스에서 푸시 알람을 보내도록 구현
    - 이때 웹 프론트에선 토큰이 없어서 null일때 처리를 해줘야 됨
        - 해당 유저의 토큰이 비어있으면 메세지 보내지 않기
        - 해당 유저의 디바이스 토큰이 없다고 예외x (404로 반환하면 클라이언트 예외처리가 힘들어짐)

---

## [Dotori](https://dotori-gsm.com/home)

> gsm 기숙사 관리 시스템
> 

[V1](https://github.com/Team-Ampersand/Dotori-server)

2021.07.10 - ing

- 자습에 왔는지 확인하는 기능
    - 권한별로 컨트롤러를 분리해서 처리
    - 기숙사 자치위원이 종이에 체크하는게 불편하다는 건의 사항이 있어서 자습 내려간 학생들을 체크할 수 있게끔 변경
    - query dsl사용
        - 더티 체킹을 할수도 있었지만 변경된 필드가 하나밖에 없어서 쿼리를 날리는게 더 좋다 생각함
- 모든 에러가 500으로 처리되던 버그 수정
    - 어느날 f12로 네트워크 로그를 보던중 모든 exception이 500으로 처리되는걸 확인
    - 로컬에선 정상적으로 처리가 되어서 배포 환경쪽 문제인줄 알고 계속 확인했지만 원인을 못찾음
    - 원인을 찾기위해 코드를 보던중 RestControllerAdvice 어노테이션이 달려있는 객체가 2개라는 걸 발견하고 order 어노테이션으로 우선순위 지정해서 해결

[V2](https://github.com/Team-Ampersand/Dotori-server-V2)

자바를 코틀린으로 마이그레이션

2022.11.22 - ing

- 회원 인증 관련된 기능
    - 이메일 인증, 로그인, 비밀번호 변경 등등….
- 자습
    - 자습신청
        - 동시성 이슈때문에 쿼리에 락걸어서 적용
    - 자습 조회
        - 학년, 반 별로 조회
        - 이름으로 조회
        - 기본 조회(신청순)
    - 자습 체크
        - 자습 신청하고 자습실에 내려왔는지 체크
    - 자습 취소
        - 신청하고 취소한 사람은 그날 자습을 다시 신청할 수 없다
    - 자습 정보 조회
        - 신청인원과 현재 유저의 신청 상태를 조회
    - 스케줄
        - @Schedule을 사용해서 월~금 10시마다 자습금지가 풀린 학생과 신청한 학생과 신청 취소한 학생들을 신청가능한 상태로 변경
- 메인 페이지
    - 유저 정보 조회
        - 학번, 이름, 성별
- 안마의자
    - 안마의자 신청
        - 자습신청과 같이 쿼리에 락설어서 적용
    - 안마의자 신청 취소
        - 신청하고 취소한 사람은 그날 자습을 다시 신청할 수 없다
    - 안마의자 조회
        - 기본조회
            - 인원(5명)이 적기때문에 딱히 학년, 반 조회나 이름으로 조회는 없다

---

# Skills.

## Backend

- java, kotlin, Spring Boot
- jpa
- java script, Express

## Data Base

- mysql, mariaDB
- h2
- redis
- mongoDB

## infra

- ec2, s3, rds
- cloud type

## **Cooperation**

- Git, GitHub
- notion
- slack

---

# Certificate.

- 정보처리산업기사
- 정보처리 기능사
- SQLD