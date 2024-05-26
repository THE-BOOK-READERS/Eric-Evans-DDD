# 3장. 유연한 설계
## 3.1 개요
> To have a project accelerate as development proceeds—rather than get weighed down by its own legacy—demands a design that is a pleasure to work with, inviting to change. A supple design.

- (자신의 레거시에 의해 얽매이지 않고) 개발이 진행됨에 따라 프로젝트를 가속화하려면, 작업하는 것이 즐겁고, 변화를 유도하는 설계를 요구한다. 유연한 설계


> Supple design is the complement to deep modeling.

- 유연한 설계는 심층적인 모델링을 보완한다. 


> Developers play two roles, each of which must be served by the design. The same person might well play both roles—even switch back and forth in minutes—but the relationship to the code is different nonetheless. One role is the developer of a client, who weaves the domain objects into the application code or other domain layer code, utilizing capabilities of the design. A supple design reveals a deep underlying model that makes its potential clear. The client developer can flexibly use a minimal set of loosely coupled concepts to express a range of scenarios in the domain. Design elements fit together in a natural way with a result that is predictable, clearly characterized, and robust.

- 개발자는 두 가지 역할을 수행하는데, 각각은 디자인에 의해 제공되어야 합니다.
- 동일한 사람이 두 역할을 수행할 수도 있지만, 코드에 대한 관계는 여전히 다릅니다.
- 하나는 클라이언트의 개발자 역할인데, 도메인 객체를 응용 프로그램 코드나 다른 도메인 레이어 코드에 편리하게 통합시키는 것입니다.
- 유연한 디자인은 그 근본적인 모델을 드러내어 그 잠재력을 분명히 합니다.
- 클라이언트 개발자는 도메인 내의 다양한 시나리오를 표현하기 위해 최소한의 느슨하게 결합된 개념 집합을 유연하게 사용할 수 있습니다.
- 디자인 요소는 자연스럽게 조화되어 결과물이 예측 가능하고 명확하며 견고하게 됩니다.


> Equally important, the design must serve the developer working to change it. To be open to change, a design must be easy to understand, revealing that same underlying model that the client developer is drawing on. It must follow the contours of a deep model of the domain, so most changes bend the design at flexible points. The effects of its code must be transparently obvious, so the consequences of a change will be easy to anticipate.
>
> 1. Making behavior obvious
>
> 2. Reducing the cost of change
>
> 3. Creating software developers to work with

- 또한, 디자인은 변경을 수용하기 위해 개발자의 역할을 충족해야 합니다.
- 변경을 수용하려면, 디자인은 이해하기 쉬워야 하며, 클라이언트 개발자가 활용하는 그 근본적인 모델을 드러내야 합니다.
- 대부분의 변경이 유연한 지점에서 디자인을 굽히게 만드는 도메인의 깊은 모델의 윤곽을 따라야 합니다.
- 코드의 효과는 명백하게 분명해야 하므로 변경의 결과를 예측하기 쉬워야 합니다.
1. 행동을 명확하게 만들기
2. 변경 비용을 줄이기
3. 소프트웨어 개발자를 작업할 수 있게 만들기


## 3.2 Intention-Revealing Interfaces
> If a developer must consider the implementation of a component in order to use it, the value of encapsulation is lost. If someone other than the original developer must infer the purpose of an object or operation based on its implementation, that new developer may infer a purpose that the operation or class fulfills only by chance. If that was not the intent, the code may work for the moment, but the conceptual basis of the design will have been corrupted, and the two developers will be working at cross-purposes.

- 만약, 개발자가 컴포넌트를 사용하기 위해 컴포넌트의 구현을 고려해야 한다면, 캡슐화의 가치는 상실된다. (-> 인터페이스 사용해라!??)
- 만약, 원래 가발자가 아닌 다른 사람이 구현을 기반으로 객체나 동작을 추론해야 하는 경우, 새로운 개발자는 동작이나 클래스가 충족하는 목적을 우연히로만 추론할 수 있다.
- 만약, 그것이 의도한 바가 아니었다면, 코드는 당분간 동작할 수 있을지 모르겠지만, 설계의 개념적 기반은 손상되었을 것이며, 두 개발자는 서로 다른 목적으로 작업하게 될 것이다.

Therefore:


> Name classes and operations to describe their effect and purpose, without reference to the means by which they do what they promise. This relieves the client developer of the need to understand the internals. These names should conform to the ubiquitous language so that team members can quickly infer their meaning. Write a test for a behavior before creating it, to force your thinking into client developer mode.

- 그들이 약속한 것을 이해하는 수단에 대한 reference 없이도, 그들의 효과와 목적을 설명하기 하도록 클래스와 동작을 네이밍해라. 
- 이것은 클라이언트 개발자가 내부 구조를 이해할 필요가 없게 한다.
- 이러한 이름은 팀 구성원들이 그 의미를 빠르게 유추할 수 있도록, 유비쿼터스 언어로 형성되어야 한다.
- 클라이언트 개발자 모드로 사고하도록 강제하기 위해, 그것이 생성하기 전에 동작에 대한 테스트를 작성해라. (-> TDD 하라는 말인가?)


## 3.3 Side-Effect-Free Functions
> Interactions of multiple rules or compositions of calculations become extremely difficult to predict. The developer calling an operation must understand its implementation and the implementation of all its delegations in order to anticipate the result. The usefulness of any abstraction of interfaces is limited if the developers are forced to pierce the veil. Without safely predictable abstractions, the developers must limit the combinatory explosion, placing a low ceiling on the richness of behavior that is feasible to build.

- 여러 규칙의 Interactions 또는 계산들의 조합은 예측하기가 극도로 어렵다.
- 동작을 호출하는 개발자는 결과를 예상하기 위해 그것의 구현 뿐만 아니라 그것의 모든 위임의 구현도 이해해야 한다.
- 개발자가 베일을 뚫어야 한다면(= 내부 구현을 들여다봐야 한다면), 인터페이스 추상화의 유용성은 제한된다.
- 안전하게 예측가능한 추상화가 없다면, 개발자는 구축 가능한 행동의 풍부함에 낮은 한계선을 설정놓으면서, 조합의 폭발을 제한해야 한다. 


Therefore:

> Place as much of the logic of the program as possible into functions, operations that return results with no observable side effects. Strictly segregate commands (methods which result in modifications to observable state) into very simple operations that do not return domain information. Further control side effects by moving complex logic into value objects when a concept fitting the responsibility presents itself.

- 가능한 한 많은 프로그램 논리를 관찰 가능한 부작용 없는 결과를 반환하는 연산을 가진 함수에 넣어라.
- 엄격하게 명령(관찰 가능한 상태에 대한 수정을 초래하는 메서드)을 도메인 정보를 반환하지 않는 매우 간단한 동작으로 분리해라.
- 책임에 맞는 개념이 나타날 때, 복잡한 논리를 값 객체로 옮김으로서, 부작용을 추가로 제어해라.


> All operations of a value object should be side-effect-free functions.
- VO의 모든 동작은 부작용이 없는 함수이어야 한다.


## 3.4 Assertions
> When the side effects of operations are only defined implicitly by their implementation, designs with a lot of delegation become a tangle of cause and effect. The only way to understand a program is to trace execution through branching paths. The value of encapsulation is lost. The necessity of tracing concrete execution defeats abstraction.




Therefore:


> State post-conditions of operations and invariants of classes and aggregates. If assertions cannot be coded directly in your programming language, write automated unit tests for them. Write them into documentation or diagrams where it fits the style of the project’s development process.

- 연산의 사후조건과 클래스와 애그리게이트의 불변 조건을 명시해라.
- 만약, 이러한 assertions가 너의 프로그래밍 언어에서 직접적으로 코드화할 수 없다면, 그것들을 위해 자동화된 단위 테스트를 작성해라.
- 그것들을 프로젝트 개발 프로세스의 스타일에 맞는 문서나 다이어그램에 작성해라. 


> Seek models with coherent sets of concepts, which lead a developer to infer the intended assertions, accelerating the learning curve and reducing the risk of contradictory code.
- 학습 곡선을 가속화하면서 모순된 코드의 위험을 줄여주는, 개발자가 의도된 assertions을 추론할 수 있는, 응집력 있는 개념 세트를 가진 모델을 찾아라.


> Assertions define contracts of services and entity modifiers. 
- Assertions은 서비스의 계약과 엔티티 수정자의 계약을 정의한다.

#### 서비스의 계약의 예시
- 계좌 서비스의 입금 메서드는 입금할 금액이 양수여야 하고, 입금 후 잔액은 증가해야 한다는 조건을 말한다.

#### 엔티티 수정자(= 데이터의 상태를 변경하는 연산을 담당한다)의 계약의 예시
- 계좌 객체의 출금 메서드는 출금할 금액이 잔액보다 작거나 같아야 하며, 출금 후 금액은 음수가 도지 안항야 한다는 조건을 말한다.


> Assertions define invariants on aggregates.
- Assertions은 애그리게이트의 불변성을 정의한다.


> 실무에서는 assert을 잘 사용하지 않는 이유
- 참고 : https://puleugo.tistory.com/177
<img width="529" alt="스크린샷 2024-05-26 오후 2 32 10" src="https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/assets/60481383/fd5fb2a1-131b-4ac5-b6f2-8edb49aa68a3">




## 3.5 Standalone Classes
## 3.6 Closure of Operations
## 3.7 Declarative Design
## 3.8 Drawing on Established Formalisms
## 3.9 Conceptual Contours
