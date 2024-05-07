# 4장. 전략적 설계를 위한 Context Mapping
## 4.1 개요
### 4.1.1 bounded context
> A description of a boundary (typically a subsystem, or the work of a particular team) within which a particular model is defined and applicable.

- 어떤 모델이 정의되고 적용되는 경계에 대한 설명이다.
- 전형적으로, 서브시스템이나 특정 팀의 작업과 관련된 영역을 나타낸다.

### 4.1.2 upstream-downstream
> A relationship between two groups in which the “upstream” group’s actions affect project success of the “downstream” group, but the actions of the downstream do not significantly affect projects upstream. (e.g. If two cities are along the same river, the upstream city’s pollution primarily affects the downstream city.)

- upstream 그룹의 액션은 downstream 그룹의 액션에 영향을 주지만, downstream 그룹의 액션은 upstream 그룹의 액션에 큰 영향을 미치지 않는 2개의 그룹 사이의 관계이다.

> The upstream team may succeed independently of the fate of the downstream team.

- upstream 팀은 downstream 팀의 운명과 관계없이 성공할 수 있다.

### 4.1.3 mutually dependent (상호 의존적)
> A situation in which two software development projects in separate contexts must both be delivered in order for either to be considered a success. (When two systems each rely on information or functionality of the other - something we would generally try to avoid - naturally we see the projects that build them as interdependent. Yet there are also mutually dependent projects where system dependencies run only one direction. When the depended-on system has little value without the dependent system and the integration with that system -perhaps because this is the only place it is used - then a failure to deliver the dependent system would be a failure of both projects.)

- 서로 분리된 맥락에서 2개의 소프트웨어 개발 프로젝트가 둘다 성공 delivery되어야 하는 상황이다.
- (일반적으로 우리가 피하려는 상황이지만) 2개의 시스템이 서로 다른 시스템의 정보나 기능에 의존할 때, 우리는 자연스럽게 그들이 구축한 프로젝트를 상호 의존적인 것으로 볼 수 있다.
- 하지만, 시스템의 종속성이 한 방향으로만 실행되는 상호 의존적 프로젝트들 또한 있을 수 있다.
- 종속 시스템이 해당 시스템과 해당 시스템과의 통합 없이는 가치가 거의 없는 경우, (아마도 이것이 사용되는 유일한 장소이기 때문에) 종속 시스템을 delivery하지 못한 다면, 두 프로젝트 모두 실패하게 된다.

### 4.1.4 free (자유)
> A software development context in which the direction, success or failure of development work in other contexts has little effect on delivery.

- 다른 context에서의 개발 작업 방향, 성공 또는 실패가 delivery에 거의 영향을 미치지 않는 소프트웨어 개발 컨텍스트

> delivery 란 무엇인가?
>
> - 제품이나 소프트웨어가 최종적으로 사용자에게 전달되는 것


## 4.2 Context Map
> To plot strategy, we need a realistic, large-scale view of model development extending across our project and others we integrate with.

- 전략을 세우기 위해서, 우리는 우리 프로젝트 전체와 우리 프로젝트랑 통합되는 다른 프로젝트 전반에 걸쳐, 확장되는 모델 개발에 대해, 현실적이고 대규모적 관점이 필요하다.

> An individual bounded context leaves some problems in the absence of a global view. The context of other models may still be vague and in flux.

- 개별적인 bounded context 는 전체적인 관점이 없으면, 몇 가지 문제를 남긴다. 다른 모델의 맥락은 여전히 모호하고 유동적일 수 있다.

> People on other teams won’t be very aware of the context boundaries and will unknowingly make changes that blur the edges or complicate the interconnections. When connections must be made between different contexts, they tend to bleed into each other.

- 다른 팀의 사람들이 context boundaries를 잘 알지 못하거나 자신도 모르게 edge 부분을 흐리게 하는 변경작업을 수행할 수도 있고, 상호 연결을 복잡하게 만들 수도 있다. 다른 맥락 사이에서 연결이 만들어져야 할 때, 그들은 서로 고통 받을 수 있다.

> Even when boundaries are clear, relationships with other contexts place constraints on the nature of model or pace of change that is feasible. These constraints manifest themselves primarily through non-technical channels that are sometimes hard to relate to the design decisions they are affecting.

- 경계가 명확한 경우에도, 다른 맥락과의 관계는 모델의 특성 또는 실행할 수 있는 변화의 속도에 제약을 가한다. 이러한 제약은 주로 그들이 영향을 미치는 설계 결정과 관련시키기는 것이 때론 어려운 비기술적인 채널을 통해 나타난다.

> Therefore:

> Identify each model in play on the project and define its bounded context. This includes the implicit models of non-object-oriented subsystems. Name each bounded context, and make the names part of the ubiquitous language.

- 프로젝트에서 사용 중인 각 모델을 식별해라. 그리고 그것들의 bounded context를 정의해라. 이것은 객체지향이 아닌 하위 시스템의 암시적 모델을 포함한다. 각 bounded context의 이름을 지정하고, 해당 이름을 유비쿼터스 언어의 일부로 만들어라.

> Describe the points of contact between the models, outlining explicit translation for any communication, highlighting any sharing, isolation mechanisms, and levels of influence.

- 모든 communication에 대한 명시적인 번역을 outline 하고, 공유 및 격리 매커니즘과 영향력 수준을 강조하면서, 모델 간의 contact 지점을 설명해라.

> Map the existing terrain. Take up transformations later.

- 기조 terrain을 매핑해라.
- 나중에 transformations를 수행해라.

> This map can be a basis for realistic design strategy.
- 이 맵은 현실적인 디자인 전략의 기초가 될 수 있다.

> The characterization of relationships is made more concrete in the following pages, with a set of common patterns of relationships between bounded contexts.

- 관계들의 특징은 bounded context 간 관계의 공통 패턴 세트를 사용하여, 다음 페이지에서 좀더 구체화된다.


## 4.3 Partnership


## 4.4 Shared Kernel





## 4.5 Customer/Supplier Development



## 4.6 Conformist

## 4.7 Anticorruption Layer

## 4.8 Open-host Service

## 4.9 Published Language
> The translation between the models of two bounded contexts requires a common language.

- 두 개의 제한된 컨텍스트 모델 간의 번역에는 공통 언어가 필요하다.


> Direct translation to and from the existing domain models may not be a good solution. Those models may be overly complex or poorly factored. They are probably undocumented. If one is used as a data interchange language, it essentially becomes frozen and cannot respond to new development needs.

- 이미 존재하는 도메인 모델과의 직접적인 translation은 좋은 해결책이 아닐 수 있다.
- 이러한 모델들은 지나치게 복잡하거나 잘못된 요소로 구성될 수 있다.
- 아마도 문서화되지 않은 것 같다.
- 이러한 모델이 데이터 교환 언어로 사용된다면, 본질적으로 고정되어 새로운 개발 요구에 대응할 수 없게 된다.


> Therefore:

> Use a well-documented shared language that can express the necessary domain information as a common medium of communication, translating as necessary into and out of that language.

- 필요에 따라 해당 언어로 번역할 수 있으면서, 일반적인 의사소통 매체로서 필요한 도메인 정보를 표현할 수 있는, 잘 문서화된 고융 언어를 사용해라.


> Many industries establish published languages in the form of data interchange standards. Project teams also develop their own for use within their organization.

- 많은 산업 분야에서는 데이터 교환 표준의 형태로 Published language를 설정한다.
- 프로젝트 팀도 자체적으로 조직 내에서 사용하기 위해 개발하기도 한다.


> Published language is often combined with open-host service.

- Published language 는 종종 open-host service와 결합된다.



## 4.10 Separate Ways
> We must be ruthless when it comes to defining requirements. If two sets of functionality have no significant relationship, they can be completely cut loose from each other.

- 우리는 요구사항을 정의할 때, 무자비해야 한다.
- 만약, 두 기능 집합이 유의미한 관련이 없다면, 그것들은 서로 완전히 분리할 수 있다.
  
> Integration is always expensive, and sometimes the benefit is small.
- 통합은 항상 비용이 많이 들고, 떄로는 이득이 작을 수 있다. (-> 따라서, 억지로 통합하려고 하지 말고, 분리해라?) 

> Therefore:

> Declare a bounded context to have no connection to the others at all, allowing developers to find simple, specialized solutions within this small scope.

- 개발자가 이 작은 범위 내에서 간단하고 특화된 해결책을 찾을 수 있도록, bounded context를 다른 bounded context와 전혀 연결되지 않도록 선언해라.



## 4.11 Big Ball of Mud


