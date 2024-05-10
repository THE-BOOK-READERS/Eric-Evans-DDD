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
> Query access to aggregates expressed in the ubiquitous language.

- 유비쿼터스 언어로 표현된 aggregates에 대한 쿼리 액세스이다.


> Proliferation of traversable associations used only for finding things muddles the model. In mature models, queries often express domain concepts. Yet queries can cause problems.

- 객체를 찾는 데만 사용되는 순회 가능한 연관성이 확산은 모델을 혼란스럽게 만든다.
- 성숙한 모델에서는 쿼리가 종종 도메인 개념을 표현한다.
- 그러나, 쿼리들은 문제를 일으킬 수 있다.


> The sheer technical complexity of applying most database access infrastructure quickly swamps the client code, which leads developers to dumb-down the domain layer, which makes the model irrelevant.

- 대부분의 데이터베이스 액세스 인프라를 적용하는 데서 발생하는 기술적인 복잡성은 클라이언트 코드를 빠르게 압도한다.
- 이로 인해 개발자들이 도메인 레이어를 단순화하게 되는데, 이는 모델을 관련 없게 만든다.


> A query framework may encapsulate most of that technical complexity, enabling developers to pull the exact data they need from the database in a more automated or declarative way, but that only solves part of the problem.

- 쿼리 프레임워크는 대부분의 기술적 복잡성을 캡슐화하고, 개발자가 좀더 자동화된 또는 좀더 선언적인 방식으로 데이터베이스에서 필요한 정확한 데이터를 가져올 수 있도록 돕지만, 이것은 문제의 일부만 해결한다.


> Unconstrained queries may pull specific fields from objects, breaching encapsulation, or instantiate a few specific objects from the interior of an aggregate, blindsiding the aggregate root and making it impossible for these objects to enforce the rules of the domain model. Domain logic moves into queries and application layer code, and the entities and value objects become mere data containers.

- 구속받지 않는 쿼리는 객체들로부터 특정 필드를 가져오거나, 캡슐화를 위반하거나, aggregate의 내부로부터 몇 가지 특정 객체를 인스턴스화하거나, aggregate root를 속이거나, 그러한 객체들이 도메인 모델의 규칙을 강제로 적용하는 것을 불가능하게 한다.
- 도메인 로직이 쿼리와 application 레이어 코드로 이동하고, 엔티티 및 값 객체는 단순한 데이터 컨테이너가 된다.


Therefore:


> For each type of aggregate that needs global access, create a service that can provide the illusion of an in-memory collection of all objects of that aggregate’s root type. Set up access through a well-known global interface. Provide methods to add and remove objects, which will encapsulate the actual insertion or removal of data in the data store. Provide methods that select objects based on criteria meaningful to domain experts. Return fully instantiated objects or collections of objects whose attribute values meet the criteria, thereby encapsulating the actual storage and query technology, or return proxies that give the illusion of fully instantiated aggregates in a lazy way. Provide repositories only for aggregate roots that actually need direct access. Keep application logic focused on the model, delegating all object storage and access to the repositories.

- 글로벌 액세스가 필요한 각 유형의 aggregate를 위해, 해당 aggregate를의 루트 유형에 대한 모든 객체의 인-메모리 컬렉션처럼 보이는 서비스를 만들어라. (-> 무슨 말이지?)
- 잘 알려진 글로벌 인터페이스를 통해 액세스를 설정해라.
- 실제 데이터 저장소에 데이터를 삽입하거나 제거하는 것을 캡슐화하는, 객체 추가 및 제거 메서드를 제공해라.
- 도메인 전문가에게 의미있는 기준에 따라 객체를 선택하는 메서드를 제공해라. (-> 예, 회원ID로 회원조회, 회원 닉네임으로 회원조회?)
- 속성값이 기준에 충족하는 완전히 인스턴스화된 객체 또는 객체 컬렉션을 반환하여 실제 저장소와 쿼리 기술을 캡슐화하거나, lazy한 방식으로 완전히 인스턴스화된 aggregates을 가장한 프록시를 반환한다. (-> 무슨 말이지?)
- 실제로 직접적인 액세스가 필요한 aggregate 루트만을 위한 repositories를 제공해라.
- application 로직을 모델에 집중시키고, 모든 객체 저장 및 액세스를 repositories에 위임해라.


## 2.10 Factories
> When creation of an entire, internally consistent aggregate, or a large value object, becomes complicated or reveals too much of the internal structure, factories provide encapsulation.

- 전체 또는 내부적으로 일관된 aggregate, 큰 value object 의 생성이 복잡해지거나 내부 구조를 너무 많이 드러낼 때, factories는 캡슐화를 제공한다.


> Creation of an object can be a major operation in itself, but complex assembly operations do not fit the responsibility of the created objects. Combining such responsibilities can produce ungainly designs that are hard to understand. Making the client direct construction muddies the design of the client, breaches encapsulation of the assembled object or aggregate, and overly couples the client to the implementation of the created object.

- 객체의 생성은 그 자체가 주요 작업이 될 수 있지만, 복잡한 조립 작업은 생성된 객체의 책임에 적합하지 않다.
- 이러한 책임을 결합하는 것은 이해하기 어려운 불편한 설계를 만들어낸다.
- 클라이언트가 직접 구성하도록 하면, 클라이언트의 디자인을 혼란스럽게 만들고, 조립된 객체나 aggregate의 캡슐화를 위반하고, 생성된 객체의 구현에 클라이언트를 과도하게 연결하게 된다.


Therefore:


> Shift the responsibility for creating instances of complex objects and aggregates to a separate object, which may itself have no responsibility in the domain model but is still part of the domain design. Provide an interface that encapsulates all complex assembly and that does not require the client to reference the concrete classes of the objects being instantiated. Create an entire aggregate as a piece, enforcing its invariants. Create a complex value object as a piece, possibly after assembling the elements with a builder.

- 복잡한 객체와 집합의 aggregates 생성 책임을 별도의 객체로 이동시켜라. 이 object 자체는 도메인 모델 내에서 책임이 없지만 여전히 도메인 설계의 일부이다.
- 클라이언트가 인스턴스화된 object의 구체적인 클래스를 참조할 필요가 없으면서, 모든 복잡한 조립을 캡슐화하는 인터페이스를 제공해라.
- 내부 불변성을 강제하는 전체 aggregate을 한 조각으로 생성해라.
- 가능하다면 빌더를 사용하여 요소를 조립한 다음, 복잡한 value object를 생성해라.





