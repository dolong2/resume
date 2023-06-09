# 저는 조재영입니다.

### Contact.

Email. jjy006546@gmail.com

Phone. **010-6662-4566**

### Channel.

GitHub. [https://github.com/dolong2](https://github.com/dolong2)

**portfolio.** [https://deadpan-climb-1a7.notion.site/fefd8a72c3694f2bacb5f5bef91af748](https://www.notion.so/fefd8a72c3694f2bacb5f5bef91af748)

---

# Introduce.
>쓰기 쉬운 코드보다 읽기 쉬운 코드
>
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
해당 프로젝트에선 github actions와 cloud type을 이용해서 ci/cd를 구축했습니다.
빌드와 배포가 자동화가 됨에 따라 업무 효율성이 높아졌습니다.
> 

[GAuth Backend](https://github.com/GSM-MSG/GAUTH_BackEnd)

2022.07.29 - 2023.01.29

- 예외 처리
    - RuntimeException을 상속해서 커스텀 예외를 만들면 똑같이 예외처리하는 로직이 많이지기 때문에 줄여야될 필요성을 느낌
    - BasicException을 만들고 이를 상속한 하위 exception들을 개발
        - 이렇게 하면 `@ExceptionHandler(BasicException.class)` 인 exceptionHandler만 만들어도 BasicException하위 exception들을 쳐리할 수 있다
- excelParsing
    - 선생님들이 수동으로 학생들의 정보를 채우기엔 새 학년이 들어왔을 경우에는 선생님들이 할 일이 너무 많아짐
    - admin권한을 가진 유저만 실행할 수 있는 API
    - 학생정보를 채우기 위해 학생정보 엑셀을 파싱할 수 있는 로직 개발
    - 쿼리 최적화
        - 기존에 2n + 1 개의 쿼리가 나가던 가지던 로직을 in 키워드를 이용해서 n+1개의 쿼리만 나가게끔 수정
- 메일 인증
    - 사용자가 인증코드를 받고 입력하는 과정이 불편하게 느껴져서 개발하게 됨
    - 메일은 버튼이 보내지고 그 버튼을 누르면 인증이 완료되는 플로우로 개발하면 사용자가 훨씬더 편해질 수 있어서 해당 플로우로 개발함
        
        ![스크린샷 2023-03-20 오후 12.29.59.png](./img/sample.png) {: width="80" height="80"}
        
    - redis로 구현
    - 코드를 uuid기반으로 생성한 코드가 있는 uri로 요청보내는 버튼을 메일로 보낸다
    - 서버에선 요청(메일인증)온 코드가 유효한지 확인하고 유효하면 해당메일을 인증됨 상태로 변경
    - 이미 인증된 메일은 다시 못 보내게끔 개발
- 로그를 남길수 있게 해주는 커스텀 어노테이션
    - lombok을 안써서 @Slf4j를 못씀
        - lombok을 추가하기엔 @Slf4j를 제외한 다른 어노테이션은 사용 되지 않음
    - java reflection과 spring eventListener를 사용해서 해당 클래스에 있는 log라는 이름의 필드에 Logger를 주입 시켜주는 어노테이션
    - @Transactional이 붙으면 AOP때문에 안됨
    - Spring AOP를 사용해서 어노테이션이 붙은 메서드가 실행될때 logger에 값을 주입해서 실행하는 방식으로 변경
- Oauth2.0적용
    - 클라이언트에서 oauth로그인 요청이 오면 email이랑 password비교해서 code발급
    - 클라이언트는 발급받은 code로 accessToken요청
    - accessToken과 refreshToken발급
- S3를 이용해서 프로필 업로드 기능 개발
- 리소스 서버 개발
    - 같은 서버에서 돌아가는것 보다 다른 서버에서 돌아가는 것이 성능 향상에 도움이 될거같아서 리소스 서버를 따로 구축
- GAuth accessToken으로 토큰을 발급해주는 API
    - GAuth 웹뷰에서 자동로그인을 하기위해서 GAuth에서 사용하는 accessToken으로 Oauth Code를 발급

---

## [GAuth-sdk-java](https://github.com/GSM-MSG/GAuth-SDK-Java)

> GAuth API를 자바 기반에서 이용할 수 있게끔 만든 라이브러리
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
- 상태코드를 담아서 예외를 던지도록 수정해서 사용자가 예외처리를 할 수 있게끔 개발

[GAuth-SDK-JAVA v2.0.0](https://github.com/GSM-MSG/GAuth-SDK-Java/releases/tag/v2.0.0)

2023.01.25
- GAuth를 인터페이스와 구현체로 분리
    - 플로우가 완전히 바뀌었기 때문에 2.0.0으로 버전업
    - 테스트하는데 불편함이 있다는 의견을 반영해서 분리함
        - mocking을 하기위해서 Interface로 분리
        - static 키워드를 없애면 mocking 가능하긴함
    - 확장성도 좋아지기 때문에 인터페이스로 분리 선택
    

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

> GCMS는 GSM Club Management Service의 약자로 교내 동아리 신청이나 방과후 신청을 관리할 수 있는 서비스입니다
> 

Back-end-V1

2022.03.19 - 2022.06.30

- 간단하게 코드 리뷰와 코드 리펙토링에 참여
- 개발은 끝냈지만 동아리 신청 기간이 아니라 배포할 시기를 놓쳐서 유지보수 후 다음 연도에 배포하기로 미뤄짐

[Back-end-V2](https://github.com/GSM-MSG/GCMS-BackEnd)

2023.01.25 - ing

- v2는 기존에 spring(java) + nest.js로 작성되어있던 백엔드 코드를 spring(kotlin)으로 마이그레이션하는 작업
- kotest와 mockk를 사용해서 테스트 코드 작성
- 동아리 생성, 신청, 신청 마감, 동아리 탈퇴, 동아리 삭제, 동아리 신청, 동아리 신청 취소 API 개발
- 유저 id를 binary(16)으로 변경
    - mysql에서 uuid는 binary(16)으로 저장함
    - jpa에서는 BINARY(255)로 저장함
    - 유저 id를 `@Column(columnDefinition = BINARY(16))` 으로 설정
- 동아리 수정 API 개발
    - 엔티티의 정보가 val이기때문에 수정되는 동아리의 id값을 가지는 수정된 정보로 새로운 객체로 만들어서 save함
        - 이렇게 했을때 모든 필드를 수정할때 더티체킹처럼 모든 필드를 수정함
        - 해당 현상을 막기위해 엔티티에 @DynamicUpdate 적용
- 부장 위임 API 개발
    - 부원 목록이 `mutableList`라면 `.add` 메서드와 `.remove` 메서드를 사용해서 관계가 맺어지도록 개발할 수 있었지만,  `list` 로 작성했기때문에 부원 엔티티를 save시켜서 db상에서 관계가 맺어지도록 개발
- 동아리 구성원을 엑셀로 보내는 API 개발
    - 선생님들은 동아리 명단을 엑셀로 관리하고 있음
    - poi 라이브러리를 사용해서 db에서 가져온 데이터를 엑셀로 변환
        - 반마다 학생들이 어떤 동아리에 소속되어있는지 볼 수 있는 엑셀
        - 동아리마다 어떤 학생들이 소속되어있는지 볼 수 있는 엑셀
- 다중 로그인 구현
    - 기존 RefreshToken엔티티는 userId를 @Id로 개발해서 다른 플렛폼에서 로그인을 진행하면 기존의 refreshToken값은 사라지고 새로 만든 refreshToken으로 업데이트 됨
    - 하지만 플랫폼이 3개인 gcms특성상 다중로그인이 필요함
    - @Id를 token value값에 설정해서 로그인과 리프레시 요청이 들어올때마다 새로운 토큰이 생기게끔 수정
- fcm으로 푸시알람 구현
    - 사용자들이 본인의 동아리에 신청했는지 확인할려면 직접 앱에 들어가야 했음
    - 해당 불편함을 없애기 위해서는 동아리에 신청했을때, 동아리에 수락했을때, 동아리에 거절했을때, 등등의 경우에 푸시알람을 보내서 해결
    - https://github.com/GSM-MSG/GCMS-BackEnd/issues/178
    - 해당 케이스에서 푸시 알람을 보내도록 구현
    - deviceToken은 앱을 초기화하거나 재설치 하는게 아닌 이상 바뀌지 않음, 하지만 여러 플랫폼에서 로그인 할 수 있는 gcms의 특성상 가장 마지막에 로그인한 플랫폼의 deviceToken을 가지도록 구현

---

## [Dotori](https://dotori-gsm.com/home)

> gsm 기숙사 관리 시스템
> 

> 22년 10월부터 &mpersand 팀의 백엔드 리드와 부장을 담당
부장으로써 매번 동아리 시간마다 발표세션을 진행
또한 v2의 전반적인 일정과 주간 회의를 진행
백엔드 리드로써 v2 마이그레이션을 진행할때 사용할 기술 스택과 아키텍처를 결정
> 

[V1](https://github.com/Team-Ampersand/Dotori-server)

2021.07.10 - ing

- 자습에 왔는지 확인하는 기능
    - 권한별로 컨트롤러를 분리해서 처리
    - 기숙사 자치위원이 종이에 체크하는게 불편하다는 건의 사항이 있어서 자습 내려간 학생들을 체크할 수 있게끔 변경
    - query dsl사용
        - 더티 체킹을 할수도 있었지만 변경된 필드가 하나밖에 없어서 쿼리를 날리는게 더 좋다 생각함
- 모든 에러가 500으로 처리되던 버그 수정
    - f12로 네트워크 로그를 보던중 모든 exception이 500으로 처리되는걸 확인
    - 로컬에선 정상적으로 처리가 되어서 배포 환경의 문제인줄 알고 계속 확인했지만 원인을 못찾음
    - 원인을 찾기위해 코드를 보던중 RestControllerAdvice 어노테이션이 달려있는 객체가 2개라는 걸 발견하고 order 어노테이션으로 우선순위 지정해서 해결

[V2](https://github.com/Team-Ampersand/Dotori-server-V2)

자바를 코틀린으로 마이그레이션

2022.11.22 - ing
- 회원 인증 관련된 기능
    - 이메일 인증, 로그인, 비밀번호 변경 등등….
- 자습
    - 자습신청
        - Multi Thread 환경에서 자습신청 인원 수 count 관련 기능에서 자습신청 정원을 넘어 신청되는 동시성 문제가 발생하여, JPA 비관적 Lock을 이용하여 동시성 문제 해결
    - 자습 조회
        - 기존 v1에선 이름 조회와 학번조회가 따로 있었으나 v2의 기능명세서에서는 이름, 학번, 조회로 바뀜
            - 이에 따라 기존의 두개의 API를 하나로 합침
        - 기본 조회(신청순)
    - 자습 체크
        - 사감쌤과 기자위가 직접 종이에 내려온 학생 명단 체크를 하는것을 보고 dotori에서 관리하면 좋겠다는 생각이 들었음
        - 자습 신청하고 자습실에 내려왔는지 체크
    - 자습 취소
    - 자습 정보 조회
        - 신청인원과 현재 유저의 신청 상태를 조회
    - 스케줄
        - @Schedule을 사용해서 월~금 10시마다 자습금지가 풀린 학생과 신청한 학생과 신청 취소한 학생들을 신청가능한 상태로 변경
    - 자습 인원 조정
        - 기숙사 자치 위원회 회의나 특별한 행사같은 경우 때때로 자습인원이 조정될때가 있는데 그때마다 공지를 하고 더 신청하는지 안하는지 검사하거나 신청한 사람중 수용가능한 사람까지만 자습할 수 있게끔 했어야함
        - 기숙사 자치 위원이나 도토리 개발자, 사감쌤이 자습인원수를 변경할 수 있게끔 개발
        - 해당 기능이 있어도 몇명까지 자습이 가능하다는 공지는 작성해야 하지만 신청한 학생중 해당 순번의 학생까지 왔는지 검사할 필요가 사라짐
- 메인 페이지
    - 유저 정보 조회
        - 학번, 이름, 성별
- 안마의자
    - 안마의자 신청
        - 자습신청과 같이 쿼리에 락걸어서 적용
    - 안마의자 신청 취소
        - 신청하고 취소한 사람은 그날 안마의자를 다시 신청할 수 없음
    - 안마의자 조회
        - 기본조회
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
