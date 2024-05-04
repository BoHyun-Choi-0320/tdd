# TDD 예제 코드 작성

- 참고 사이트 : https://mangkyu.tistory.com/183

[ 문제 설명 ]
- 멤버십 적립 서비스
- 네이버, 카카오, 라인 3가지 멤버십 존재, 멤버십 등록 가능
- 포인트 적립비율은 결제금액의 1%로 고정되며, 추후에 고정 금액(1000원)으로 확장하여 적립될 수 있어야 함
- REST API를 자유롭게 정의하고, TDD방식 구현

[ 기능 요구사항 ]
- 멤버십 연결하기, 나의 멤버십 조회, 멤버십 연결끊기, 포인트 적립 API
- 사용자 식별값은 문자열 형태이며 “X-USER-ID”라는 HTTP Header로 전달되며, 포인트 적립할 때 바코드 대신 사용
- Content-Type 응답 형태는 application/json(JSON) 형식을 사용
- 각 기능 및 제약사항에 대한 개발을 TDD, 단위테스트를 기반으로 진행

[ 상세 기술 구현 사항 ]
- 나의 멤버십 등록 API
    - 기능 : 나의 멤버십을 등록
    - 요청 : 사용자 식별값, 멤버십 이름, 포인트
    - 응답 : 멤버십 ID, 멤버십 이름


- 나의 멤버십 전체 조회 API
    - 기능 : 내가 가진 모든 멤버십을 조회
    - 요청 : 사용자 식별값
    - 응답 : {멤버십 ID,  멤버십 이름, 포인트, 가입일시}의 멤버십 리스트


- 나의 멤버십 상세 조회 API
    - 기능 : 나의 1개 멤버십을 상세 조회
    - 요청 : 사용자 식별값, 멤버십 ID
    - 응답 : 멤버십 ID, 멤버십 이름, 포인트, 가입일시


- 나의 멤버십 삭제 API
    - 기능 : 나의 멤버십을 삭제
    - 요청 : 사용자 식별값, 멤버십 번호
    - 응답 : X


- 멤버십 포인트 적립 API
    - 기능 : 나의 멤버십 포인트를 결제 금액의 1%만큼 적립
    - 요청 : 사용자 식별값, 멤버십 ID, 사용 금액을 입력값으로 받음
    - 응답 : X

[ 기술 요구 사항 ]
- 개발 언어 : Java 22
- Framework : Spring Boot
- ORM : JPA
- DB : MySQL/H2

