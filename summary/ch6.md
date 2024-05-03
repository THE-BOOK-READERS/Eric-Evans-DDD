# 6장. 전략적 설계를 위한 대규모 구조
## 6.1 개요

> In a large system without any overarching principle that allows elements to be interpreted in terms of their role in patterns that span the whole design, developers cannot see the forest for the trees. We need to be able to understand the role of an individual part in the whole without delving into the details of the whole.

- 전체 설계에 걸쳐 있는 패턴의 역할을 해석할 수 있는 포괄적인 원칙이 없는 대규모 시스템에서는 개발자는 나무를 위한 숲을 볼 수 없다.
- 우리는 전체의 세부 사항에 대해 깊게 파고들지 않고도 전체에서 개별 부분의 역할을 이해할 수 있어야 한다.

> A “large-scale structure” is a language that lets you discuss and understand the system in broad strokes. A set of high-level concepts or rules, or both, establishes a pattern of design for an entire system. This organizing principle can guide design as well as aid understanding. It helps coordinate independent work because there is a shared concept of the big picture: how the roles of various parts shape the whole.

- "대규모 구조"는 시스템을 폭넓게 논의하고 이해할 수 있는 언어이다.
- 일련의 고수준 개념이나 규칙 또는 둘 다는 전체 시스템에 대한 설계 패턴을 확립한다.
- 이러한 구조화된 원칙은 설계를 안내하고 이해를 도울 수 있다.
- 다양한 부분의 역할이 전체를 어떻게 형성하는지에 대한 큰 그림에 대해 공유된 개념이 있기 때문에, 독립적인 작업을 조율하는데 도움이 된다.


Therefore:

> Devise a pattern of rules or roles and relationships that will span the entire system and that allows some understanding of each part’s place in the whole—even without detailed knowledge of the part’s responsibility.

- 전체 시스템에 걸쳐 각 부분의 책임에 대한 자세한 지식 없이도 전체에서 각 부분의 위치를 어느 정도 이해할 수 있도록 하는 규칙이나 역할 및 관계의 패턴을 고안해라.


## 6.2 Evolving Order(진화하는 질서)
> Design free-for-alls produce systems no one can make sense of as a whole, and they are very
difficult to maintain. But architectures can straitjacket a project with up-front design assumptions and take too much power away from the developers/designers of particular parts of the application. Soon, developers will dumb down the application to fit the structure, or they will subvert it and have no structure at all, bringing back the problems of uncoordinated development.

- free-for-alls 설계는 전체적으로 이해하기 어려운 시스템을 만들어내며, 이는 유지보수하기 매우 어렵다.
- 그러나, 아키텍처는 프로젝트에 전반적인 설계 가정을 미리 내재화함으로써 특정 부분의 개발자/설계자로부터 너무 많은 권한을 빼앗아 버릴 수 있다.
- 곧 개발자들은 구조에 맞추기 위해 애플리케이션을 단순화하거나, 그것을 교란하고 구조 자체가 없게 되어 조율되지 않은 개발 문제를 다시 가져올 것입니다.

Therefore:

> Let this conceptual large-scale structure evolve with the application, possibly changing to a completely different type of structure along the way. Don’t over constrain the detailed design and model decisions that must be made with detailed knowledge.

- 이 개념적 대규모 구조를 애플리케이션과 함께 발전시키게 하여, 그 과정에서 완전히 다른 유형의 구조로 변경될 수도 있도록 한다.
- 상세한 지식을 바탕으로 내려야 하는 세부 설계 및 모델을 과도하게 제한하지 마라.
  

> Large-scale structure should be applied when a structure can be found that greatly clarifies the system without forcing unnatural constraints on model development. Because an ill- fitting structure is worse than none, it is best not to shoot for comprehensiveness, but rather to find a minimal set that solves the problems that have emerged. Less is more.

- 대규모 구조는 모델 개발에 부자연스러운 제약을 강요하지 않으면서도, 시스템을 크게 명확하게 하는 구조가 발견될 때 적용해야 한다.
- 부적합한 구조는 없는 것보다 나쁘기 때문에, 포괄성을 목표로 삼기보다는 발생한 문제를 해결하는 최소한의 집합을 찾는 것이 가장 좋다. 적을수록 더 좋다.


> What follows is a set of four particular patterns of large-scale structure that emerge on some projects and are representative of this kind of pattern.

- 다음은 일부 프로젝트에서 나타나고 이러한 종류의 패턴을 대표하는 대규모 구조의 4가지 특정 패턴 세트입니다.

## 6.3 System Metaphor
> Metaphorical thinking is pervasive in software development, especially with models. But the Extreme Programming practice of “metaphor” has come to mean a particular way of using a metaphor to bring order to the development of a whole system.
Software designs tend to be very abstract and hard to grasp. Developers and users alike need tangible ways to understand the system and share a view of the system as a whole.

- 은유적 사고는 소프트웨어 개발, 특히 모델에 널리 퍼져 있다.
- 그러나 "은유"라는 익스트림 프로그래밍 방식은 전체 시스템 개발에 질서를 부여하기 위해 은유를 사용하는 특별한 방식을 의미하게 되었다.
- 소프트웨어 디자인은 매우 추상적이고 이해하기 어려운 경향이 있다.
- 개발자와 사용자 모두 시스템을 이해하고 시스템 전체에 대한 관점을 공유할 수 있는 실질적인 방법이 필요하다.

Therefore:

> When a concrete analogy to the system emerges that captures the imagination of team members and seems to lead thinking in a useful direction, adopt it as a large-scale structure. Organize the design around this metaphor and absorb it into the ubiquitous language. The system metaphor should both facilitate communication about the system and guide development of it. This increases consistency in different parts of the system, potentially even across different bounded contexts. But because all metaphors are inexact, continually reexamine the metaphor for overextension or inaptness, and be ready to drop it if it gets in the way.

- 팀 구성원의 상상력을 포착하고 사고를 유용한 방향으로 이끄는 것처럼 보이는 시스템에 대한 구체적인 비유가 나타나면 이를 대규모 구조로 채택한다.
- 이 은유를 중심으로 설계을 구성하고 이를 유비쿼터스 언어로 흡수한다.
- 시스템 은유는 시스템에 대한 의사소통을 촉진하고 시스템 개발을 안내해야 한다.
- 이는 잠재적으로 서로 다른 bounded context 전반에 걸쳐 시스템의 여러 부분에서 일관성을 향상시킨다.
- 그러나 모든 은유는 정확하지 않기 때문에 은유의 과도한 확장이나 부적절함을 지속적으로 재검토하고 방해가 된다면 버릴 준비를 해라.


## 6.4 Responsibility Layers
> In object-oriented design, individual objects are assigned narrow sets of related responsibilities. Responsibility-driven design also applies to larger scales.


- 객체 지향 디자인에서는 개별 객체에 관련 책임의 좁은 집합이 할당된다.
- 책임 중심 설계는 더 큰 규모에도 적용된다.

> When each individual object has handcrafted responsibilities, there are no guidelines, no uniformity, and no ability to handle large swaths of the domain together. To give coherence to a large model, it is useful to impose some structure on the assignment of those responsibilities.

- 각 개별 객체마다 수작업으로 책임을 부여하는 경우, 지침도 없고 통일성도 없으며 도메인의 넓은 범위를 함께 처리할 수 있는 능력도 없다.
- 대규모 모델에 일관성을 부여하려면, 이러한 책임 할당에 일부 구조를 적용하는 것이 유용하다.


Therefore:

> Look at the conceptual dependencies in your model and the varying rates and sources of change of different parts of your domain. If you identify natural strata in the domain, cast them as broad abstract responsibilities. These responsibilities should tell a story of the high-level purpose and design of your system. Refactor the model so that the responsibilities of each domain object, aggregate, and module fit neatly within the responsibility of one layer.

- 모델의 개념적 의존성과 도메인의 다양한 부분의 변화율과 변화 소스를 살펴봐라.
- 도메인에서 자연스러운 계층을 식별하는 경우, 이를 광범위한 추상적인 책임으로 캐스팅해라.
- 이러한 책임은 시스템의 고수준의 목적과 설계에 대한 이야기를 전달해야 한다.
- 각 도메인 개체, 집계 및 모듈의 책임이 한 계층의 책임 내에 깔끔하게 맞도록 모델을 리팩터링해라.


## 6.5 Knowledge Level
> A group of objects that describe how another group of objects should behave.
- 다른 그룹의 객체들이 어떻게 동작해야 하는지를 설명하는 객체 그룹이다.


> In an application in which the roles and relationships between entities vary in different situations, complexity can explode. Neither fully general models nor highly customized ones serve the users’ needs. Objects end up with references to other types to cover a variety of cases, or with attributes that are used in different ways in different situations. Classes that have the same data and behavior may multiply just to accommodate different assembly rules.

- 상황에 따라 엔터티 간의 역할과 관계가 달라지는 애플리케이션에서는 복잡성이 폭발적으로 증가할 수 있다.
- 완전히 일반적인 모델이나 고도로 맞춤화된 모델은 사용자의 요구 사항을 충족하지 못한다.
- 객체들은 다양한 경우를 포괄하기 위해 다른 유형을 대한 참조하거나, 다양한 상황에서 다양한 방식으로 사용되는 속성을 갖게 된다. 
- 데이터와 동작이 동일한 클래스들은 다른 조립 규칙을 수용하기 위해 증가할 수 있다.


Therefore:

> Create a distinct set of objects that can be used to describe and constrain the structure and behavior of the basic model. Keep these concerns separate as two “levels,” one very concrete, the other reflecting rules and knowledge that a user or super-user is able to customize.

- 기본 모델의 구조와 동작을 설명하고 제한할 수 있는 고유한 객체 집합을 만들어라.
- 이러한 관심사를 2개의 수준으로 분리하도록 유지해라.
- 하나는 매우 구체적이고, 다른 하나는 사용자 또는 슈퍼 사용자가 사용자 정의할 수 있는 규칙과 지식을 반영하는 것이다.



## 6.6 Pluggable Component Framework
> Opportunities arise in a very mature model that is deep and distilled. A pluggable component framework usually only comes into play after a few applications have already been implemented in the same domain.

- 기회는 깊고 정제된 매우 성숙한 모델에서 발생한다.
- 플러그형 컴포넌트 프레임워크는 일반적으로 동일한 도메인에서 몇 가지 애플리케이션이 이미 구현된 후에만 작동한다.

> When a variety of applications have to interoperate, all based on the same abstractions but designed independently, translations between multiple bounded contexts limit integration. A shared kernel is not feasible for teams that do not work closely together. Duplication and fragmentation raise costs of development and installation, and interoperability becomes very difficult.

- 다양한 애플리케이션이 모두 동일한 추상화를 기반으로 하지만, 독립적으로 설계되어 상호 운용되어야 하는 경우, 여러 bounded contexts 간의 번역으로 인해 통합이 제한된다.
- 긴밀하게 협력하지 않는 팀에게는 공유 커널이 적합하지 않다.
- 복제와 단편화로 인해 개발 및 설치 비용이 증가하고 상호 운용성이 매우 어려워진다.

Therefore:

> Distill an abstract core of interfaces and interactions and create a framework that allows diverse implementations of those interfaces to be freely substituted. Likewise, allow any application to use those components, so long as it operates strictly through the interfaces of the abstract core.

- 인터페이스와 상호 작용의 추상적인 핵심을 추출하고 해당 인터페이스의 다양한 구현을 자유롭게 대체할 수 있는 프레임워크를 만든다.
- 마찬가지로 추상 코어의 인터페이스를 통해 엄격하게 작동하는 한, 모든 애플리케이션에서 이러한 구성 요소를 사용할 수 있도록 허용해라.
