# DDD Reference - Definitions and Pattern Summaries
## 1장. 모델 활용하기
- 실제 비즈니스 세계 뿐만 아니라 그 비즈니스 세계를 소프트웨어에 녹여내는 것은 굉장히 복잡하다.
- 따라서, 이 복잡한 세계에서 소프트웨어이 필요한 개념들을 추상화시켜 모델링 할 수 있다.
- 이런 방법론을 모델 주도 설계([Model-Driven Design](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch1.md#15-model-driven-design))라고 한다.
- 이때, 복잡한 비즈니스 세계를 하나의 덩어리로 만들다 보면, 그 복잡성 또한 증가하게 된다.
- 따라서, 그렇게 증가하는 복잡성을 해결하기 위해, 도메인에 따라 또는 회사 사정에 따라 쪼갤 수 있는데, 이때 쪼개진 영역을 [Bounded Context](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch1.md#12-bounded-context)라고 부른다.
- 이는 도메인 모델의 명확한 경계를 설정하여 혼란을 방지할 수 있다.
- 또한, 동일한 개념이더라도, Bounded Context에 따라 다르게 정의될 수 있다.
- 예를 들면, 회원이라는 모델을 주문 Bounded Context에서는 주문자로 부르는 반면, QnA Bounded Context에서는 질문자로 부를 수 있다.
- 또한, 같이 일을 하더라도, 서로 다른 용어를 사용해서 커뮤니테이션 비용을 증가하거나 엉뚱한 기능이 만들어지기도 한다.
- 이것은 서로 사용하는 `언어의 복잡성`이 초래하는 문제인데, 이를 해결하기 위해 팀 전체에 공유하는 일관된 언어인 [Ubiquitous Language](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch1.md#13-ubiquitous-language)를 정의되어지고 사용되어진다.
- 이렇게 만들어진 Ubiquitous Language 는 모든 문서와 대화에서 사용되고, 도메인 모델을 만들 때에도 사용된다.
- 이런 Ubiquitous Language는 도메인과 관련된 이해관계자들([Hands-on Modelers](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch1.md#16-hands-on-modelers%EB%AA%A8%EB%8D%B8%EC%9D%84-%EB%A7%8C%EB%93%A4%EA%B1%B0%EB%82%98-%EA%B0%9C%EB%B0%9C%ED%95%98%EB%8A%94-%EA%B3%BC%EC%A0%95%EC%97%90%EC%84%9C-%EC%A7%81%EC%A0%91%EC%A0%81%EC%9C%BC%EB%A1%9C-%EC%B0%B8%EC%97%AC%ED%95%98%EB%8A%94-%EC%82%AC%EB%9E%8C%EB%93%A4))이 함께 지식 탐구에 의해 정의되기도 하고, 발견하기도 하고, 수정되기도 한다.
- 이 Ubiquitous Language를 사용해서 도메인 모델을 만든다.
- 이렇게 만들어진 유비쿼터스 언어와 도메인 모델은  [Continuous Integration](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch1.md#14-continuous-integration)와 더 깊은 통찰을 위한 리팩토링 과정([Refactoring Toward Deeper Insight](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch1.md#17-refactoring-toward-deeper-insight%EB%8D%94-%EA%B9%8A%EC%9D%80-%ED%86%B5%EC%B0%B0%EB%A0%A5%EC%9D%84-%ED%96%A5%ED%95%9C-%EB%A6%AC%ED%8C%A9%ED%84%B0%EB%A7%81))을 통해 점점 더 심층적인 형태로 발전하게 된다.
- 처음부터 완벽한 유비쿼터스 언어와 도메인 모델를 만들면 좋겠지만, 현실적으로 불가능하기도 하고, 비즈니스가 진행됨에 따라 변하기도 하기 때문에, 유연하게 대응하기 위해 도구들이 필요하다.
- 그 도구들 중 하나가 CI와 리팩토링이다.
- CI을 통해 모델의 지속적인 품질 개선과 오류를 신속하게 발견할 수 있고, 더 깊은 통찰을 위한 리팩터링를 통해 도메인 모델을 개선하고 진화시켜 나갈 수 있다.


## 2장. 모델 주도 설계의 구성 요소
- 도메인 주도 설계를 효과적으로 구현하기 위해 여러 가지 구성 요소와 패턴이 있다.
- 여기서, 모든 패턴을 사용해야만 하는 건 아니고, 팀 상황에 맞게 사용하면 좋을 것 같은 것들을 적용시켜보면 좋다.


### 1. 패턴 (Patterns)
#### (1) [레이어드 아키텍처 (Layered Architecture)](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch2.md#22-layered-architecture)
##### What
- 복잡한 프로그램을 서로 독립저인 계층으로 분리한 아키텍처 스타일.

##### Why
- 각 계층에 명확한 책임을 부여 분리함으로써, 코드의 복잡성을 줄일 수 있기 때문에, -> 관심사 분리를 하는 이유와 비슷

#### How (추후에 추가 작성)
- 이때, 각 계층은 응집력 있으면서 아래 레이어에만 의존하게 설계하는 것이 중요하다.


#### (2) [팩토리 (Factories)](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch2.md#210-factories)
##### What
- 객체나 애그리게잇의 생성 로직을 관심사 분리를 통해 따로 관리하고 싶을 때 사용하는 패턴

##### Why
- 생성 로직을 중앙 집중화시킴으로써 객체 생성의 복잡성을 줄이기 위해


#### How (추후에 추가 작성)
- 


#### (3) [레포지토리 (Repositories)](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch2.md#29-repositories)
##### What
- 엔티티나 애그리게잇을 저장하고 검색하는 작업을 추상화하는 패턴

##### Why
- 도메인 로직과 데이터 접근 로직을 분리함으로서 로직의 복잡성을 줄이기 위해

#### How (추후에 추가 작성)
- 


#### (4) [애그리게잇 (Aggregates)](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch2.md#28-aggregates)
##### What
- 일관성 있는 변경을 보장하기 위해 함께 그룹화된 관련 객체들(예 : 값 객체 또는 엔티티)의 집합

##### Why
-  일관성 있는 변경을 보장하기 위해
-  따라서, 트랜잭션 경계를 정의할 수도 있다.


#### How (추후에 추가 작성)
1. 작게 만들어라.
2.  




### 2. 구성 요소 (Components)

#### (1) [엔티티 (Entities)](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch2.md#23-entities)
##### What
- 도메인 모델에서 고유한 식별자를 가지며, 동일성을 기준으로 구분되는 객체
- 식별자를 통해 다른 객체와 구분되며, 이는 객체의 속성 값이 변하더라도 동일성을 유지하는 기준이 됩니다.

##### Why
- 객체의 동일성을 관리하기 위함.
- 객체의 경우 다양한 속성값을 가질 수 있다.
- 이때, 속성값 중 1가지가 변화하더라도, 동일한 객체가 아닌 것은 아니다.
- 따라서, 객체의 속성값이 바뀌더라도, 동일한 객체로 간주할 수 있게 식별자를 통해 동일성을 관리한다.

#### How (추후에 추가 작성)
- 


#### (2) [값 객체 (Value Objects)](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch2.md#24-value-objects)
##### What
- 값을 표현하는 객체
- 예를 들어, 주소라는 데이터가 있다고 했을 때, 이걸 그냥 String으로 저장할 수도 있지만, Address라는 클래스로 만들어서 사용할 수도 있다.
- 어떤 것이 더 좋을지는 도메인마다, 팀의 합의에 따라 다르다.
- 나같으면, 도메인에서 주소라는 개념이 중요하면, 값 객체로 만들어 사용할 것이고, 아니라면 그냥 String으로 할 것이다.

##### Why
1. 값을 객체화 함으로써, 그 값이 만든 의도를 드러낼 수 있기 때문에
2. 자주 사용되는 값을 재활용 할 수 있다는 장점도 있어서,

#### How (추후에 작성)
- 동일성을 기준으로 구분되는 개체가 아니라, 그 속성 값에 의해 구분되는 객체이므로, 불변으로 구현하는 것이 중요하다. 


> 엔티티 vs 값 객체의 차이는 무엇인가요?
> - 식별성 유무의 차이이다.
> - 식별성이 있다면, 엔티티로 만들고, 식별성이 없다면 값 객체로 만들어라.


#### (3) [도메인 이벤트 (Domain Events)](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch2.md#25-domain-events-)
##### What
- 도메인 내에서 발생하는 의미 있는 사건을 나타내는 객체
- 예를 들어, "주문완료됨" 등의 사건을 도메인 이벤트로 만들 수 있다.

> 엔티티나 값 객체 vs 도메인 이벤트
> - 상태 변경을 직접적으로 하냐 아니냐의 차이
> - 엔티티나 값 객체의 경우, 직접적으로 상태를 변경하지만, 도메인 이벤트의 경우, 다른 객체에게 상태 변경을 알리는 역할을 한다.

##### Why
- EDA 구조에서 데이터 일관성을 위해, 엔티티 또는 값 객체, 애그리게이트 등의 상태 변경을 알리기 위해 필요하다.

#### How (추후에 추가 작성)
- 

 
#### (4) [서비스 (Services)](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch2.md#26-services)
##### What
- 도메인 로직을 캡슐화하고 관리하는데 사용하는 객체

##### Why
1. 비즈니스 로직에는 여러 객치의 상호 작용이 필요한 복잡한 로직이 필요할 때가 있다. 이때 사용하면 좋다.
2. 서비스는 트랜잭션의 시작과 종료를 관리할 수 있다. 여러 개의 엔티티나 값 객체 등를 변경하는 작업을 하나의 트랜잭션으로 묶어 일관성을 유지할 수 있다.

#### How (추후에 추가 작성)
- 

> 서비스 vs 값 객체 vs 엔티티
> - 상태를 아예 갖지 않는건, `서비스`,
> - 상태를 가지만, 불변성 있게 관리되는 건, `값 객체`,
> - 상태를 가지면서도, 가변성 있게 관리되는 건, `엔티티`


#### (5) [모듈 (Modules)](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch2.md#27-modules)
##### What
- 관련된 도메인 개념을 논리적으로 그룹화하는 방법

##### Why
- 시스템의 복잡성을 줄이기 위해

#### How (추후에 추가 작성)
- 


## 3장. 유연한 설계
### Intention-Revealing Interfaces 
### Side-Effect-Free Functions 
### Assertions
### Standalone Classes
### Closure of Operations 
### Declarative Design
### Drawing on Established Formalisms
### Conceptual Contours

## 4장. 전략적 설계를 위한 Context Mapping
- 비즈니스가 발전함에 따라 시스템은 점점 거대해지고 복잡해진다.
- 이렇게 복잡해진 시스템을 Bounded Context로 정의해서 분리하여, 문제 영역을 작은 단위로 만든다. (이때, 분리하는 기준은 도메인마다 또는 같은 도메인이라도 회사 상황에 따라 다르다.)
- 이렇게 나눠진 Bounded Context들간의 관계와 상호작용을 시각적으로 표현해놓는게 필요하다.
- 이때, [Context Map](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch4.md#42-context-map)이라는 도구를 활용하면 좋다.
- 그리고, 이렇게 나눠진 Bounded Context들간의 관계에는 다양한 관계가 존재할 수 있다.
- 또한, 이들 간의 어떤 메시지를 어떻게 주고 받을지에 대해서도 정의해야 하는데, 이렇게 정의해 놓은 것이 [Published Language](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch4.md#49-published-language)이다.
- 여기서, Bounded Context들간의 관계에 대해서 크게 7가지 형태를 살펴보자.


  ### 1. [Partnership](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch4.md#43-partnership)
  - Bounded Context들간의 관계가 성공과 실패를 함께하는 관계일 경우에 사용하는 패턴
  - 예를 들면, 추천 시스템과 마케팅 시스템의 관계가 있다.
  - 추천 시스템의 알고리즘이 마케팅 시스템에 활용되고, 마케팅 시스템의 데이터가 추천 시스템의 알고리즘에 영향을 주는 관계이기 때문이다.
  
  ### 2. [Shared Kernel](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch4.md#44-shared-kernel)
  - 여러 Bounded Context들 간의 공통으로 사용하는 모델이 있는 경우에 사용하는 패턴
  - 이때, 진짜! 진짜로! 공통으로 사용하는 것들만 Shared Kernel로 채택하는게 중요하다.
  - 그러기 위해서는 작게 단위로 유지하는 것이 좋다.
  - 예를 들어, 회원 도메인이 가장 흔한 예이다.   
  
  ### 3. [Customer/Supplier Development](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch4.md#45-customersupplier-development)
  - Bounded Context들간의 관계가 수요자(Customer)에 요구사항에 따라 공급자(Supplier)가 공급해 주는 관계인 경우에 사용하는 패턴
  - 예를 들면, 상품 도메인(Supplier)과 주문 도메인(Customer)의 관계가 있다.
  
  ### 4. [Conformist](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch4.md#46-conformist)
  - Bounded Context들간의 관계가 한쪽 도메인이 무조건적으로 다른 한쪽의 모델과 정책을 따를 수밖에 없는 경우에 사용하는 패턴
  - 따라서, 주로 다운스트림 컨텍스트이 업스트림 컨텍스트에 대한 영향력이 없고, 업스트림 컨텍스트의 변경 사항을 수용해야 하는 경우에 발생한다.
  - 예를 들어, 공공 데이터를 활용하는 경우가 있을 수 있다.
  - 공공데이터를 활용하는 경우, 공공데이터 제공자가 제공해 준대로 공공데이터를 사용할 수 있을 뿐, 공공데이터를 사용자가 이 데이터 달라고 요구하는 관계가 아니다. (물론, 건의 게시판에 글을 쓸 수는 있다ㅎㅎ)
  - 이떄, 공공 데이터 제공자를 `업스트림 컨텍스트`로 보고, 공공 데이터 사용자를 `다운스트림 컨텍스트`로 본다.   
  
  ### 5. [Anticorruption Layer](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch4.md#47-anticorruption-layer%EB%B6%80%ED%8C%A8-%EB%B0%A9%EC%A7%80-%EB%A0%88%EC%9D%B4%EC%96%B4---%ED%98%91%EC%97%85%EC%9D%B4-%EC%96%B4%EB%A0%A4%EC%9A%B4-%ED%8C%80%EC%97%90%EC%84%9C-%EC%82%AC%EC%9A%A9%ED%95%A0-%EC%88%98-%EC%9E%88%EB%8A%94-%EA%B8%B0%EC%88%A0) :
  - Bounded Context들간의 관계가 서로 연관이 있지만, A Context의 영향을 B Context에 최소화하고 내부 모델을 보호하기 위해 사용하는 패턴 
  - 예를 들면, 다음과 같은 상황에서 사용할 수 있다.
    #### 경우 1. 한 회사가 기존의 레거시 시스템을 현대화하여 새로운 마이크로서비스 아키텍처로 전환하고 있는 상황에서, 새로운 시스템은 기존 레거시 시스템의 데이터를 사용해야 하지만, 레거시 시스템의 데이터 구조와 비즈니스 로직은 새로운 시스템의 도메인 모델과 맞지 않은 경우
    #### 경우 2. A 시스템이 B 시스템의 데이터를 사용해야 하는데, A시스템의 팀과 B 시스템의 팀이 서로 협력하기 어려운 경우
    #### 경우 3. A 시스템이 B 시스템의 데이터를 사용해야 하는데, A시스템의 팀과 B 시스템의 팀의 개발속도가 차이가 나는 경우
    #### 경우 4. 공공데이터를 사용하고 있는데, 우리 프로젝트의 서비스에 맞게 사용하고 싶을 경우
  - 시스템 버전의 어댑터 패턴 같은 느낌이다.
  
  ### 6. [Open-host Service](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch4.md#48-open-host-service)
  - 업스트림 서비스가 다수의 다운스트림 서비스에 데이터를 제공해야 할 때 유용하게 사용하는 패턴
  - 예를 들어, 상품 도메인이 업스트림이고 추천 도메인, 주문 도메인, 재고 도메인이 다운스트림인 이커머스 시나리오에서 Open-host Service 패턴을 적용해볼 수 있다.
  - 이때, 업스트림과 다운스트림의 관계는 주로 Customer/Supplier Development 관계이다.
  - 또한, 다운 스트림의 팀은 업스트림의 팀의 모델이 자신의 도메인 모델에 영향을 주지 않도록 안티코럽션 계층(Anticorruption Layer)을 활용할 수 있다.

  ### 7. [Separate Ways](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch4.md#410-separate-ways) 
  - Bounded Context들간의 관계가 각자도생의 경우이거나 그러고 싶을 때 사용하는 패턴
  - 예를 들면, 월급을 산정할 때,고객과 관련된 요소(예 : 고객 만족도나 참여하는 고객의 수 등)가 포함되지 않는 경우, 월급 관리 시스템과 고객 관리 시스템간의 관계를 예로 들 수 있다.
  - 단, 월급이 고객의 어떤 요소(예 : 고객 만족도나 참여하는 고객의 수 등)에 의해 결정되는 직원(예 : 영업사원, CS 사원 등)이라면, 다른 패턴을 사용할 수 있다.
  
  >Conformist 패턴과 Customer/Supplier Development 패턴이 서로 상하 관계에 있는 것 같은데, 어떤 차이가 있는 걸까?
  > - 다운스트림의 요구사항이 업스트림에 반영할 수 있느냐의 차이가 있다.
  > - 다운스트림의 요구사항이 업스트림에 반영할 수 있으면, Customer/Supplier Development
  > - 다운스트림의 요구사항이 업스트림에 반영할 수 없으면, Conformist
  
  > Customer/Supplier Development 패턴과 Partnership 패턴 둘다 의존관계가 있는 것 같은데, 어떤 차이가 있는 걸까?
  > - 양방향 의존적이냐 한방향 의존적이냐의 차이
  > - 서로의 성공과 실패가 영향을 주면, Partnership
  > - Customer의 성공과 실패가 Supplier의 영향을 안주면, Customer/Supplier Development
   

- 경우에 따라서, 위의 처럼 Bounded Context를 나누지 않고, [Big Ball of Mud](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch4.md#411-big-ball-of-mud) 상태로 놔두는 것이 더 나을 때가 있다.
- 예를 들면, Big Ball of Mud 상태의 시스템이 코드의 비즈니스 가치가 낮은 경우, 또는 Big Ball of Mud 상태의 시스템을 리팩토링 하는 것보다 새로 만드는 것이 더 효율적인 경우가 있다.



## 5장. 전략적 설계를 위한 Distillation
- 프로젝트에 투입될 수 있는 자원(예 : 시간, 돈, 사람 등)은 한정되어 있다.
- 따라서, 비즈니스의 핵심 요소([Core Domain](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch5.md#52-core-domain))와 그렇지 않은 요소([Generic Subdomains](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch5.md#53-generic-subdomains))를 구별하여 자원을 효율적으로 배분하기 위한 방법이 필요하다.
- 이럴 때, 핵심 요소를 추출해 내는 것을 `Distillation`이라고 한다.
- Distillation을 통해 중요한 부분에 집중하고, 그렇지 않은 부분은 간소화하거나 외부에 위임할 수 있다.
- 이때, 어떤 것이 중요하고, 그렇지 않은지에 대한 기준을 정할 수 있게 해주는 문서들이 있는데, [Domain Vision Statement(약 1p 분량)](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch5.md#54-domain-vision-statement-%EB%8F%84%EB%A9%94%EC%9D%B8-%EB%B9%84%EC%A0%84-%EC%84%A0%EC%96%B8%EB%AC%B8)과 [Highlighted Core(약 3~7p 분량)](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch5.md#55-highlighted-core)이다.
- 그리고, 이렇게 분리할 때, 응집력 있게 분리해야된다. ([Cohesive Mechanisms](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch5.md#56-cohesive-mechanisms%EC%9D%91%EC%A7%91%EB%A0%A5-%EC%9E%88%EB%8A%94-%EB%A9%94%EC%BB%A4%EB%8B%88%EC%A6%98))
- 그 결과, 분리된 핵심 도메인([Segregated Core](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch5.md#57-segregated-core))을 발견할 수 있다.
- 이렇게 분리된 코어조차도 상세한 내용이 많아서 전체적인 그림을 전달하는 것이 어려울 수 있다.
- 그럴때에는 추상화 시켜라.([Abstract Core](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch5.md#58-abstract-core))

> 핵심, 지원, 일반 도메인 예시

<img width="573" alt="스크린샷 2024-05-20 오후 1 37 25" src="https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/assets/60481383/bdd86f01-b374-423b-b68c-4cd7fdf95b52">

## 6장. 전략적 설계를 위한 대규모 구조
- 비즈니스가 발전함에 따라 시스템은 점점 거대해지고 복잡해진다.
- 따라서, 시스템의 큰 틀을 파악하기 위해 `대규모 구조`가 필요하다.
- 대규모 구조가 없다면, 개발자는 시스템 전체를 이해해야만 특정 부분을 이해할 수 있게 되어 비효율적이다.
- 각 부분의 책임에 대한 자세한 지식 없이도 전체 시스템 내에서 각 부분의 위치와 역할을 이해할 수 있도록 하는 것이 중요하다.
- 또한, 시스템은 시간이 지남에 따라 변화하므로 유연하게 설계해야 한다 ([Evolving Order](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch6.md#62-evolving-order%EC%A7%84%ED%99%94%ED%95%98%EB%8A%94-%EC%A7%88%EC%84%9C)).
- 대규모 구조는 최소한의 단위로 설정하는 것이 좋다. 부적합한 구조는 없는 것보다 더 나쁠 수 있다.
- 이러한 대규모 구조를 설계하기 위해 4가지 주요 패턴이 있다 (-> 이 4가지 패턴을 모두다 사용하는게 대규모 구조가 아니라, 필요한 패턴만 적용시켜도 대규모 구조 도구를 활용한 것?)
1. [System Metaphor](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch6.md#63-system-metaphor) : 시스템의 전반적인 이해를 돕는 은유를 사용하는 패턴 (예: 이미지 썸네일 생성 "파이프라인").
2. [Responsibility Layers](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch6.md#64-responsibility-layers) : 관심사 분리를 통해 시스템을 계층 구조로 나누는 패턴(예 : 인프라 계층, 도메인 계층 등)
3. [Knowledge Level](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch6.md#65-knowledge-level) : 대규모 구조를 표현하고 이해하는 방법을 제공하는 패턴.
4. [Pluggable Component Framework](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch6.md#66-pluggable-component-framework) : 독립적으로 개발되고 교체 가능한 컴포넌트를 통해 시스템을 모듈화하는 패턴(예: JDBC).

