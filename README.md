# 주개말발 Convention

Http Method : GET, POST만 사용

Controller Layer : service layer호출 및 response 반환

request dto + @Valid

reponse dto를 받아서 반환 -> controller layer에서 response dto 변환 X

Service Layer : 비즈니스 로직 처리 및 repository layer와 연결

데이터 유효성 검사 + 트랜잭션 관리

request dto -> entity, repository dto -> response dto

## [DTO]

XxxReqDto, XxxResDto, XxxRepoDto : Xxx(table name)

inner class로 사용

dto naming 규칙은 CRUD 네이밍을 따른다. 최대한 의미가 반영되게 한다.

불필요한 롬복 어노테이션 추가 X

@Setter 사용 지양, builder 패턴 사용

## [CRUD]

C : createXxx

R : findXxx

U : updateXxx

D : deleteXxx


## [예외처리]

예외처리 시, ApiException(임시)을 던져 ApiResponse 생성
에러 코드는 ENUM으로 관리
