# 2장. 모델 주도 설계의 구성 요소
## 2.1 개요
> These patterns cast widely held best practices of object-oriented design in the light of domain-driven design. They guide decisions to clarify the model and to keep the model and implementation aligned with each other, each reinforcing the other’s effectiveness. Careful crafting the details of individual model elements gives developers a steady platform from which to explore models and to keep them in close correspondence with the implementation.

- 이러한 패턴들은 DDD의 시각에서 OOP의 널리 알려진 best practices들을 제시한다. 
- 이러한 패턴들은 모델을 명확히 하고, 모델과 구현을 서로 일치시켜 서로의 효율성을 강화하기 위한 결정을 가이드한다.
- 개별 모델 요소의 세부 사항을 주의 깊게 작성하는 것은 개발자들에게 모델을 탐색하고 구현과 밀접하게 일치시키는 안정된 플랫폼을 제공합니다.

## 2.2 Layered Architecture
## 2.3 Entities 
## 2.4 Value Objects
## 2.5 Domain Events * 
## 2.6 Services 
## 2.7 Modules

## 2.8 Aggregates
> It is difficult to guarantee the consistency of changes to objects in a model with complex associations. Objects are supposed to maintain their own internal consistent state, but they can be blindsided by changes in other objects that are conceptually constituent parts. Cautious database locking schemes cause multiple users to interfere pointlessly with each other and can make a system unusable. Similar issues arise when distributing objects among multiple servers, or designing asynchronous transactions.

- 복잡한 연관 관계를 갖는 모델에서 객체에 대한 변경을 일관성 있게 보장하는 것은 어렵다.
- 객체는 자체적으로 내부 상태의 일관성을 유지해야 하지만, 개념적으로 구성 요소인 다른 객체의 변경으로 인해 예상치 못한 영향을 받을 수 있다.
- 조심스러운 DB locking 방식은 여러 사용자가 서로 무의미하게 간섭하게 하고, 시스템을 사용할 수 없게 만들 수 있다.
- 여러 서버에 객체를 배포하거나 비동기 트랜잭션을 설계할 때도 비슷한 문제가 발생한다.


Therefore:


> Cluster the entities and value objects into aggregates and define boundaries around each. Choose one entity to be the root of each aggregate, and allow external objects to hold references to the root only (references to internal members passed out for use within a single operation only). Define properties and invariants for the aggregate as a whole and give enforcement responsibility to the root or some designated framework mechanism.

- 엔터티와 값 객체를 집단화하여 집합체로 구성하고 각각 주변에 boundaries를 정의한다.
- 각 집합체의 루트 엔터티를 선택하고 외부 객체가 루트에 대한 참조만 보유하도록 허용한다 (단일 작업 내에서만 사용하기 위해 전달된 내부 멤버에 대한 참조).
- 전체적으로 aggregate에 대한 속성과 불변성을 정의하고, root 또는 일부 지정된 프레임워크 메커니즘에게 시행 책임을 부여해라.


> Use the same aggregate boundaries to govern transactions and distribution.

- 트랜잭션 및 분산을 관리하기 위해 동일한 aggregate boundaries를 사용해라.


> Within an aggregate boundary, apply consistency rules synchronously. Across boundaries, handle updates asynchronously.

- aggregate boundary 내에서, 일관성 규칙을 동기적으로 적용해라.
- boundary를 넘어서면, 비동기적으로 업데이트를 처리해라.


> Keep an aggregate together on one server. Allow different aggregates to be distributed among nodes.

- 한 서버에서 aggregate를 함께 유지해라.
- 서로 다른 aggregate가 다양한 노드 간에 분산되도록 허용해라.


> When these design decisions are not being guided well by the aggregate boundaries, reconsider the model. Is the domain scenario hinting at an important new insight? Such changes often improve the model’s expressiveness and flexibility as well as resolving the transactional and distributional issues.

- 이러한 설계 결정이 aggregate boundaries에 제대로 가이드되지 않은 경우 모델을 다시 생각해봐라.
- 도메인 시나리오가 중요한 새로운 통찰력을 제시하고 있는가?
- 이러한 변경은 종종 모델의 표현력과 유연성을 향상시키고, 트랜잭션 및 배포 이슈 문제를 해결한다.


## 2.9 Repositories
## 2.10 Factories
