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
> When teams in two contexts will succeed or fail together, a cooperative relationship often emerges.

- 두 개의 맥락에서 팀이 함께 성공하거나 실패할 때, 협력적인 관계가 종종 드러난다.


> Poor coordination of mutually dependent subsystems in separate contexts leads to delivery failure for both projects. A key feature missing from one system might make the other system undeliverable. Interfaces that do not match the expectations of the developers of the other subsystem could cause integration to fail. A mutually agreed interface might turn out to be so awkward to use that it slows the development of the client system, or so difficult to implement that it slows the development of the server subsystem. Failure brings both projects down.

- 서로 의존하는 서브시스템들의 부적절한 조정은 두 프로젝트 모두에게 delivery 실패로 이어진다. 
- 한 시스템에서 누락된 중요한 기능은 다른 시스템이 이용할 수 없게 만들 수 있다.
- 다른 시스템의 개발자들의 기대와 일치하지 않는 인터페이스는 통합을 실패하게 만들 수 있다.
- 상호 합의된 인터페이스가 사용하기에 너무 불편하여, 클라이언트 시스템의 개발 속도를 느리게 하거나, 구현하기 너무 어려워서 서버 서브시스템의 개발 속도가 느려질 수 있다.
- 실패는 두 프로젝트 모두를 망하게 만든다.


Therefore:


> Where development failure in either of two contexts would result in delivery failure for both, forge a partnership between the teams in charge of the two contexts. Institute a process for coordinated planning of development and joint management of integration.

- 두 맥락 중 하나의 맥락의 개발 실패가 두 시스템 모두의 delivery 실패로 이어질 경우, 두 맥락을 담당하는 팀 간의 파트너십을 구축해라.
- 개발의 조정된 계획과 통합의 공동 관리를 위한 프로세스를 확립해라.


> The teams must cooperate on the evolution of their interfaces to accommodate the development needs of both systems. Interdependent features should be scheduled so that they are completed for the same release.

- 팀은 두 시스템의 개발 요구 사항을 수용하기 위해 인터페이스의 진화에 대해 협력해야 한다.
- 상호 의존하는 기능들은 동일한 릴리스에 대해 완료되도록 일정을 계획해야 한다.


> It is not necessary, most of the time, for developers to understand the model of the other subsystem in detail, but they must coordinate their project planning. When development in one context hits obstacles, then joint examination of the issue is called for, to find an expeditious design solution that does not overly compromise either context.

- 대부분의 경우, 개발자들이 다른 서브시스템의 모델을 자세히 이해할 필요는 없지만, 그들은 (서브시스템을 고려하여) 프로젝트 계획을 조정해야 한다.
- 어느 한쪽 맥락에 지나치게 치우지지 않는, 신속한 설계 솔루션을 찾기 위해, 이슈에 대해 공동 조사가 필요하다.


> Also, a clear process is needed to govern integration. For example, a special test suite can be defined that proves the interface meets the expectations of the client system, which can be run as part of continuous integration on the server system.

- 또한, 명확한 프로세스는 통합을 관리하기 위해 필요하다.
- 예를 들어, (서버 시스템에서 CI의 일부분으로 실행될 수 있는) 클라이언트 시스템의 기대를 충족시키는 인터페이스를 증명하는 특별한 테스트 suit를 정의할 수 있다.


## 4.4 Shared Kernel
> Sharing a part of the model and associated code is a very intimate interdependency, which can leverage design work or undermine it.

- 모델의 일부와 그와 관련된 코드를 공유하는 것은 매우 밀접한 상호 의존성을 가지며, 이 의존성은 설계 작업을 활용하거나 약화시킬 수 있다.


> When functional integration is limited, the overhead of continuous integration of a large context may be deemed too high. This may especially be true when the team does not have the skill or the political organization to maintain continuous integration, or when a single team is simply too big and unwieldy. So separate bounded contexts might be defined and multiple teams formed.

- 기능적 통합이 제한되면, 대규모 컨텍스트의 CI의 오버헤드는 너무 높다고 간주될 수 있다.
- 특히, 팀이 CI를 유지할 능력이나 정치적 조직력이 없는 경우, 또는 단일 팀이 단순히 너무 커서 다루기 어려울 때, 특히 그렇다.
- 따라서, 별도의 bounded context는 정의되고, 여러 팀이 형성될 수 있다.


> Once separate, uncoordinated teams working on closely related applications can go racing forward for a while, but what they produce may not fit together. Even partner teams can end up spending a great deal on translation layers and retrofitting, meanwhile duplicating effort and losing the benefits of a common ubiquitous language.

- 밀접하게 관련된 애플리케이션에 대해 작업하지만, 일단 따로 분리되어 서로 조율하지 않는 팀은 잠시 동안 빠르게 나아갈 수 있겠지만, 그들이 생산하는 것이 서로 맞지 않을 수 있다.
- 심지어, 파트너 팀 조차도 translation 레이어와 retrofitting(개조)에 많은 비용이 들 수 있는 동시에, 노력이 중복되고 공통 유비쿼터스 언어의 이점을 잃을 수 있다.


Therefore:


> Designate with an explicit boundary some subset of the domain model that the teams agree to share. Keep this kernel small.

- 팀이 공유하기로 동의한 도메인 모델의 일부 하위 집합을 명시적 boundary로 지정해라.
- 이 커널을 작게 유지해라.


> Within this boundary, include, along with this subset of the model, the subset of code or of the database design associated with that part of the model. This explicitly shared stuff has special status, and shouldn’t be changed without consultation with the other team.

- 이 boundary 내에서, 이 모델의 하위 집합과 함께, 모델의 해당 부분과 관련된 코드 또는 데이터베이스 설계의 하위 집합을 포함시켜라.
- 명시적으로 공유되는 이러한 항목은 특별한 상태를 가지며, 다른 팀과 협의 없이 변경해서는 안 된다.


> Define a continuous integration process that will keep the kernel model tight and align the ubiquitous language of the teams. Integrate a functional system frequently, though somewhat less often than the pace of continuous integration within the teams.

- 커널 모델을 긴밀하게 유지하고, 팀의 유비쿼터스 언어를 align하는 CI 프로세스를 정의해라.
- 비록, 팀 내의 CI보다 더 자주는 아니지만, 자주 기능적 시스템을 통합해라.


## 4.5 Customer/Supplier Development
> When two teams are in an upstream-downstream relationship, where the upstream team may succeed independently of the fate of the downstream team, the needs of the downstream come to be addressed in a variety of ways with a wide range of consequences.

- 두 팀이 업스트림-다운스트림 관계에 있는 경우, 업스트림 팀이 다운스트림 팀의 운명과 무관하게 독립적으로 성공할 수 있을 때, 다운스트림의 요구 사항은 다양한 결과와 함께 다양한 방식으로 다양한 방법으로 해결된다.


> A downstream team can be helpless, at the mercy of upstream priorities. Meanwhile, the upstream team may be inhibited, worried about breaking downstream systems. The problems of the downstream team are not improved by cumbersome change request procedures with complex approval processes. And the freewheeling development of the upstream team will stop if the downstream team has veto power over changes.

- 다운스트림 팀은 업스트림의 우선 순위에 도움을 못받은 채로 남겨질 수 있다.
- 한편, 업스트림 팀은 다운스트림 시스템을 망가뜨리지 않을까 걱정하며 제약을 받을 수 있다.
- 다운스트림 팀의 문제는 복잡한 승인 프로세스와 번거로운 변경 요청 절차로 해결되지 않는다.
- 또한, 만약, 다운스트림이 변경에 대한 거부권을 가지고 있다면, 업스트림 팀의 자유로운 개발은 멈출 것이다.


Therefore:


> Establish a clear customer/supplier relationship between the two teams, meaning downstream priorities factor into upstream planning. Negotiate and budget tasks for downstream requirements so that everyone understands the commitment and schedule.

- 업스트림의 계획에 다운스트림의 우선순위가 반영될수 있도록, 두 팀 간에 명확한 고객/공급자 관계를 설정해라.
- 모든 이해 관계자가 의뢰와 일정을 이해할 수 있도록, 다운스트림의 요구 사항에 대한 작업을 협상하고 예산을 배정해라.


> Agile teams can make the downstream team play the customer role to the upstream team, in planning sessions. Jointly developed automated acceptance tests can validate the expected interface from the upstream. Adding these tests to the upstream team’s test suite, to be run as part of its continuous integration, will free the upstream team to make changes without fear of side effects downstream.

- 애자일 팀은 계획 세션에서 다운스트림 팀이 업스트림 팀에 대한 고객 역할을 수행할 수 있도록 할 수 있다.
- 공동 개발된 자동 acceptance 테스트는 업스트림으로부터 예상되는 인터페이스를 검증할 수 있다.
- CI의 일부로 실행되도록, 업스트림 팀의 테스트 suit에 이런 테스트(위에서 말한 `acceptance 테스트`?)를 추가하면, 업스트림 팀이 다운스트림의 side effect에 대한 두려움 없이 자유롭게 변경할 수 있다.


## 4.6 Conformist
> When two development teams have an upstream/down-stream relationship in which the upstream has no motivation to provide for the downstream team’s needs, the downstream team is helpless. Altruism may motivate upstream developers to make promises, but they are unlikely to be fulfilled. Belief in those good intentions leads the downstream team to make plans based on features that will never be available. The downstream project will be delayed until the team ultimately learns to live with what it is given. An interface tailored to the needs of the downstream team is not in the cards.

- 두 개발 팀이 업스트림/다운스트림 관계에 있고 업스트림이 다운스트림 팀의 요구 사항을 충족할 동기가 없는 경우, 다운스트림 팀은 도움을 받을 수 없게 된다.
- 이타주의는 업스트림 개발자가 약속을 하도록 동기 부여할 수 있지만, 그 약속이 이행될 가능성이 적다.
- 이런 좋은 의도에 대한 믿음은 다운스트림 팀이 결코 이용할 수 없는 기능을 기반으로 계획을 세우가 만든다.
- 이로 인해 다운스트림 프로젝트는 팀이 궁극ㅁ적으로 주어진 대로 살아가는 방법을 배울 때까지 지연될 것이다.
- 다운스트림 팀의 요구사항에 맞춘 인터페이스는 기대하기 힘들다.

> Therefore:


> Eliminate the complexity of translation between bounded contexts by slavishly adhering to the model of the upstream team. Although this cramps the style of the downstream designers and probably does not yield the ideal model for the application, choosing conformity enormously simplifies integration. Also, you will share a ubiquitous language with your upstream team. The upstream is in the driver’s seat, so it is good to make communication easy for them. Altruism may be sufficient to get them to share information with you.

- 업스트림 팀의 모델을 맹목적으로 따라감으로써 bounded contexts 간 번역의 복잡성을 제거한다.
- 이는 다운스트림 설계자의 스타일을 제한하고, 아마도 애플리케이션을 위한 이상적인 모델을 얻지 못할 수 있을지라도, 일관성을 선택하면, 통합은 엄청나게 단순화된다.
- 또한, 업스트림 팀과 유비쿼터스 언어를 공유하게 된다.
- 업스트림 팀이 driver 자리에 있으므로, 그들과의 커뮤니케이션을 쉽게 만드는 것이 좋다.
- 이타주의는 그들이 너와 함께 정보를 공유하도록 하는데 충분할 수 있다. 


## 4.7 Anticorruption Layer(부패 방지 레이어) -> 협업이 어려운 팀에서 사용할 수 있는 기술
> Translation layers can be simple, even elegant, when bridging well-designed bounded contexts with cooperative teams. But when control or communication is not adequate to pull off a shared kernel, partner or customer/supplier relationship, translation becomes more complex. The translation layer takes on a more defensive tone.

- 협력 팀과 잘 디자인된 bounded contexts를 연결할 때, Translation 레이어는 간단하고 심지어 우아할 수 있다.
- 그러나, 컨트롤아나 의사 소통이 충분하지 않은 경우, 공유 커널, 파트너 또는 고객/공급업체 관계에서는 Translation이 더 복잡해진다.
- translation 레이어는 보다 방어적인 톤을 띠게 된다. (-> 번역 레이어가 외부 시스템의 변화에 견딜 수 있도록 설계되어야 한다)


> A large interface with an upstream system can eventually overwhelm the intent of the downstream model altogether, causing it to be modified to resemble the other system’s model in an ad hoc fashion. The models of legacy systems are usually weak (if not big balls of mud), and even the exception that is clearly designed may not fit the needs of the current project, making it impractical to conform to the upstream model. Yet the integration may be very valuable or even required for the downstream project.

- 업스트림 시스템을 갖는 대규모 인터페이스는 결국 다운스트림 모델의 의도를 완전히 압도하여, 임시적으로 다운스트림 모델이 다른 시스템의 모델과 유사하도록 수정될 수 있다.
- 레거시 시스템의 모델은 일반적으로 (큰 진흙 덩어리가 아니더라도) 약하고, 명확하게 설계된 예외라도, 현재 프로젝트의 요구사항에 맞지 않지 않아, 업스트림 모델을 따르는 것이 비실용적일 수 있다.
- 하지만, 통합은 다운스트림 프로젝트를 위해 매우 가치 있거나 필요할 수 있다.

> Therefore:


> As a downstream client, create an isolating layer to provide your system with functionality of the upstream system in terms of your own domain model. This layer talks to the other system through its existing interface, requiring little or no modification to the other system. Internally, the layer translates in one or both directions as necessary between the two models.

- 다운스트림 클라이언트로서, 자체 도메인 모델 관점에서 업스트림 시스템의 기능을 시스템에 제공하기 위해 isolating 레이어를 만들어라.
- 이 레이어는 다른 시스템을 거의 또는 전혀 수정하지 않고도, 기존 인터페이스를 통해 다른 시스템과 통신한다.
- 내부적으로, 이 레이어는 두 모델 사이에서 필요에 따라 한방향 또는 양방향으로 translate 한다.


## 4.8 Open-host Service
> Typically for each bounded context, you will define a translation layer for each component with which you have to integrate that is outside the context. Where integration is one-off, this approach of inserting a translation layer for each external system avoids corruption of the models with a minimum of cost. But when you find your subsystem in high demand, you may need a more flexible approach.

- 일반적으로 각 bounded context를 위해, context를 외부와의 각 component 와 통합해야 할 때마다, translation 레이어를 정의할 것이다.
- 통합이 일회성인 경우, 각 외부 시스템에 대해 translation 레이어를 삽입하는 이 접근법은 최소한의 비용으로 모델의 손상을 방지한다.
- 그러나, 너가 너의 하위 시스템이 높은 수요를 발견한다면, 너는 좀더 유연한 접근 방식이 필요할 수 있다.


> When a subsystem has to be integrated with many others, customizing a translator for each can bog down the team. There is more and more to maintain, and more and more to worry about when changes are made.

- 한 서브시스템이 여러 다른 시스템과 통합되어야 할 때, 각각 서브 시스템을 위한 translator를 커스텀하는 것은 팀을 수렁에 빠진게 할 수 있다.
- 유지 관리할 항목이 점점 많아지고 변경 사항이 생길 때, 신경써야할 사항도 점점 늘어납니다.


> Therefore:

> Define a protocol that gives access to your subsystem as a set of services. Open the protocol so that all who need to integrate with you can use it. Enhance and expand the protocol to handle new integration requirements, except when a single team has idiosyncratic needs. Then, use a one-off translator to augment the protocol for that special case so that the shared protocol can stay simple and coherent.

- 서비스 집합으로서 너의 서브시스템에 접근할 수 있는 프로토콜을 정의해라.
- 너와 통합해야 하는 모든 사람들을 위해 프로토콜을 공개해라.
- 1개의 팀의 독특한 요구 사항을 갖는 경우를 제외하고, 새로운 통합 요구 사항을 처리하기 위해 프로토콜을 개선하고 확장ㅎ라.
- 그러고 나서, 공유 프로토콜을 단순하고 일관성 있게 유지하기 위해서, 특별한 경우를 위한 프로토콜을 강화하기 위해 일회성 translator를 사용해라.


> This places the provider of the service in the upstream position. Each client is downstream, and typically some of them will be conformist and some will build anticorruption layers. A context with an open host service might have any sort of relationship to contexts other than its clients.

- 이것은 서비스 제공자를 업스트림 위치시킨다.
- 각 클라이언트는 다운스트림이 되고, 일반적으로 일부는 conformist이 되고, 일부는 anticorruption layers를 구축한다.
- open host service 를 갖는 context는 클라이언트 이외의 컨텍스트와 어떤 종류의 관계도 갖게 될 수 있다.


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

<img width="595" alt="스크린샷 2024-05-07 오후 7 37 51" src="https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/assets/60481383/569bb596-bcc7-404a-8621-fc3e3f64e51d">


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


