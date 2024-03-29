# study-objects
# OBJECTS 스터디

## 1. 티켓 판매 애플리케이션

https://swimlanes.io/d/gJfeudDgf

https://swimlanes.io/d/R76K8W3-_


## 4. 설계 품질과 트레이드오프

- 역할, "책임", 협력
- 객체의 상태가 아닌 객체의 "행동"에 초점을 마춰라.

> 데이터 중심의 설계 : 일단 하긴 했는데...


###  4-2. 설계 트레이드 오프
- 캡슐화 : 변경 가능성이 높은 부분을 객체 내부로 숨기는 추상화 기법
- 응집도 : 모듈 내부 요소들이 연관돼 있는 정도
- 결합도 : 의존성의 정도

> 결국 "설계를 변경하기 쉽게"

- SRP : Single Responsibility Principle : 모듈의 응집도가 변경과 연관이 있다.

### 4-4. 자율적인 객체를 향해 = 결국 캡슐화
- 너비높이변경(인스턴스, 인자) {} -> 인스턴스.너비높이변경 {} 으로~
-> 코드 중복, 변경 쉬워짐

## 5. 책임할당하기 = 책임주도 설계
- GRASP (General Responsibility Assignment Software Pattern, 일반적인 책임 할당을 위한 소프트웨어 패턴)
- 도메인 개념 (올바른 도메인 모델 같은 것은 없음)
> 
- 전문가에게 책임을 할당하라. (Informattion Export Pattern)
- 메시지를 전송할 객체는 무엇을 원하는가? (누구인가가 아님)
- 메시지를 수신할 적합한 객체는 누구인가?
* 정보 전문가는 정보를 '저장'하고 있을 필요는 없다. 대신 도움을 받거나, 계산해서 제공하면 된다.
> 
> **주:** 명사, 동사 나열법. ERD 도식과 비슷.
> - "Actor" 를 결정하고 "Activity" 를 도출한다. (Use Case Diagram, Activity Diagram, 순서도)
> - Activity 를 캡슐화 한다. = 클래스 도출
> - Activity 간의 flow 를 결정한다. (Sequence Diagram)


- Information Expoert Pattern
- Low Coupling Pattern
- Hign Cohesion Pattern
- Creator Pattern
- Polymorphism Pattern
- Protected Varations Pattern : 변경될 가능성이 높은가? 그렇다면 캡슐화하라. 안정적인 인터페이스로.

## 6. 메시지와 인터페이스
- 클라이언트-서버 모델
- 메시지, 메시지 전송
- 메시지, 메서드
- 퍼블릭 인터페이스, 오퍼레이션
- 시그니처

### 6-2. 인터페이스와 설계 품질
> **디미터 법칙:**
> - 낯선 자에게 말하지 말라
> - 오직 인접한 이웃하고만 말하라
> - 오직 하나의 도트만 사용하라
> - 기차 충돌 지양

> **묻지말고 시켜라 :** 책임 수행원에게 지시
> - "절차적인 코드는 정보를 얻은 후에 결정한다. 객체지향 코드는 객체에게 그것을 하도록 시킨다"

> **의도를 드러내는 인터페이스**
> - 메서드 명명법 : 무엇(what)과 어떻게(How)의 차이.
> - 의도를 드러내는 선택자(Intention Revealing Selector)
> - 의도를 드러내는 인터페이스는 의도를 드러내는 선택자의 확장 버전
* 명령-쿼리 분리

6-3. 원칙의 함정
- 디미터 법칙은 하나의 도트를 강제하는 규칙은 아니다. (예 : stream())
- 상태를 물어본 후 반환된 상태를 기반으로 결정을 내리고 그 결정에 따라 객체의 상태를 변경하는 코드는 묻지 말고 시켜라 스타일로 변경해야 한다.
예) Audience.Buy 의 도출
그러나...
periodCondition.isSatisfiedBy 는? : "책임"으로 판단하는게 더 좋다.

- TradeOff : 전체 영화의 가격 계산은???
- 디미터 법칙 : 객체(o), 자료 구조(x).

6-4. 명령-쿼리 분리
- 루틴 
- 프로시저 - 함수(부수효과와 반환값의 유무로 판별)
==> 부수효과 격리.
- 참조 투명성 : 어떤 표현식 e=f(x)가 있을 때 e=f(x)의 값(value)으로 e가 나타나는 모든 위치를 교체하더라도 결과가 달라지지 않는 특성

- 불변성, immutability

- 명령형 프로그래밍, 함수형 프로그래밍
