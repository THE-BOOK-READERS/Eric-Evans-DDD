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

- operation의 side effect가 그들의 구현에 의해 암묵적으로만 정의될 경우, 많은 위임을 가진 설계는 원인과 결과가 뒤엉키게 된다.
- 프로그램을 이해하는 유일한 방법은 분기 경로를 통해 실행을 추척하는 것이다.
- 캡슐화의 가치는 잃어버리게 된다.
- 구체적인 실행을 추적해야 하는 필요성은 추상화를 무너뜨린다.


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


## 3.5 Standalone Classes(독립형 클래스)
> Even within a module, the difficulty of interpreting a design increases wildly as dependencies are added. This adds to mental overload, limiting the design complexity a developer can handle. Implicit concepts contribute to this load even more than explicit references.

- 한 모듈 내에서도 의존성이 추가될수록 설계를 해석하는 난이도가 급격하게 증가한다.
- 이는 정신적 과부하를 가중시켜, 개발자가 처리할 수 있는 설계의 복잡성을 제한한다.
- 암시적인 개념은 이러한 부담을 명시적인 참조보다 더 많이 준다.

> Low coupling is fundamental to object design. When you can, go all the way. Eliminate all other concepts from the picture. Then the class will be completely self-contained and can be studied and understood alone. Every such self-contained class significantly eases the burden of understanding a module.

- 낮은 결합도는 객체 설계에 기본적입니다.
- 가능하면 완전히 결합도를 제거해라.
- 그림에서 다른 개념을 모두 제거해라.
- 그러면 클래스가 완전히 독립적이 되고 개별적으로 공부하고 이해할 수 있다.
- 이러한 모든 독립형 클래스는 모듈을 이해하는 부담을 크게 줄어준다.


## 3.6 Closure of Operations
> Most interesting objects end up doing things that can’t be characterized by primitives alone.

- 대부분의 흥미로운 객체들은 단순한 기본 자료형(primitives)만으로는 완전히 표현할 수 없는 (복잡한) 작업을 수행한다.

<img width="524" alt="스크린샷 2024-05-26 오후 3 17 44" src="https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/assets/60481383/0621db7a-0c0b-4178-ba83-328117fb387c">


Therefore:


> Where it fits, define an operation whose return type is the same as the type of its argument(s). If the implementer has state that is used in the computation, then the implementer is effectively an argument of the operation, so the argument(s) and return value should be of the same type as the implementer. Such an operation is closed under the set of instances of that type. A closed operation provides a high-level interface without introducing any dependency on other concepts.

- 적절한 경우, 반환 유형이 인자의 유형과 동일한 operation을 정의해라.
- 구현자(-> 특정 메서드를 실행하는 객체)가 계산에 사용되는 상태를 가지고 있다면, 구현자는 사실상 operation의 인자이므로 인자와 반환 값은 구현자와 동일한 유형이어야 합니다.
- 이러한 operation은 해당 타입의 인스턴스 집합에 대해 닫혀 있다.
- 닫힌 operation은 다른 개념에 대한 의존성을 도입하지 않고도 고수준의 인터페이스를 제공한다.


> This pattern is most often applied to the operations of a value object. Because the life cycle of an entity has significance in the domain, you can’t just conjure up a new one to answer a question. There are operations that are closed under an entity type. You could ask an Employee object for its supervisor and get back another Employee. But in general, entities are not the sort of concepts that are likely to be the result of a computation. So, for the most part, this is an opportunity to look for in the value objects.

- 이 패턴은 주로 값 객체의 작업에 적용된다.
- 도메인에서 엔티티의 수명이 중요한 의미를 가지기 때문에, 질문에 답하기 위해 새로운 엔티티를 만들 수 없다.
- 엔티티 유형에 대해 닫힌 operation이 있다.
- 예를 들어, Employee 객체에게 그것의 감독자를 요청하고, 다른 Employee를 돌려받을 수 있다.
- 그러나, 일반적으로 엔티티는 계산의 결과가 될 수 있는 일종의 개념이 아니다. 
- 따라서, 대부분의 경우 이것은 값 객체에서 찾을 수 있는 기회이다.


> You sometimes get halfway to this pattern. The argument matches the implementer, but the return type is different, or the return type matches the receiver and the argument is different. These operations are not closed, but they do give some of the advantage of closure, in freeing the mind.

- 너는 때때로 이 패턴의 중간에 도달하기도 한다.
- 인자가 구현자와 일치하지만 반환 유형이 다르거나, 반환 유형이 수신자와 일치하지만 인자가 다른 경우이다.
- 이러한 operation은 닫혀 있지 않지만, 마음을 자유롭게 하는 데 있어서 닫힘의 장점 중 일부를 제공한다.
  

## 3.7 Declarative Design
> There can be no real guarantees in procedural software. To name just one way of evading assertions, code could have additional side effects that were not specifically excluded. No matter how model-driven our design is, we still end up writing procedures to produce the effect of the conceptual interactions. And we spend much of our time writing boilerplate code that doesn’t really add any meaning or behavior. Intention-revealing interfaces and the other patterns in this chapter help, but they can never give conventional object-oriented programs formal rigor.

- 절차적 소프트웨어에서는 실제로 어떤 보증도 할 수 없다.
- 단언문을 회피하는 한 가지 방법을 꼽자면, 코드에 명시적으로 제외되지 않은, 추가적인 부작용을 가질 수 있다.
- 우리의 디자인이 아무리 모델 중심적이라 할지라도, 우리는 여전히 개념적 상호 작용의 효과를 생성하기 위해 절차를 작성하게 된다.
- 그리고 우리는 실제로 의미나 행동을 추가하지 않는, 보일러플레이트 코드를 작성하는 데 많은 시간을 소비한다.
- 의도를 드러내는 인터페이스와 이 장에서 다루는 다른 패턴들이 도움이 될 수 있지만, 이러한 것들은 전통적인 객체지향 프로그램에 형식적인 엄격함을 줄 수 없다.


> These are some of the motivations behind declarative design. This term means many things to many people, but usually it indicates a way to write a program, or some part of a program, as a kind of executable specification. A very precise description of properties actually controls the software. In its various forms, this could be done through a reflection mechanism or at compile time through code generation (producing conventional code automatically, based on the declaration). This approach allows another developer to take the declaration at face value. It is an absolute guarantee.

- 이러한 것들은 선언적 디자인의 동기 중 일부이다.
- 이 용어는 많은 사람들에게 많은 것을 의미하지만, 일반적으로 프로그램 또는 프로그램의 일부를 일종의 실행 가능한 specification로 작성하는 방법을 나타낸다.
- 속성에 대해 매우 정확한 설명은 실제로 SW를 제어한다.
- 이것은 다양한 형태로 코드 생성(선언 기반의 기존 코드를 자동으로 생성하는)을 통해 컴파일 시간에 또는 reflection 메커니즘을 통해 수행될 수 있다.
- 이 접근법은 다른 개발자가 선언을 그대로 받아들일 수 있게 한다.
- 이는 절대적인 보증이디.


> Many declarative approaches can be corrupted if the developers bypass them intentionally or unintentionally. This is likely when the system is difficult to use or overly restrictive. Everyone has to follow the rules of the framework in order to get the benefits of a declarative program.

- 만약, 개발자가 의도적으로 또는 의도치 않게 그것들을 우회한다면, 많은 선언적 접근 방식은 손상될 수 있다.
- 이는 시스템을 사용하기 어렵게 하거나 지나치게 제한적인 경우에 발생할 수 있다.
- 선언적 프로그램의 이점을 얻기 위해, 모든 사람이 프레임워크의 규칙을 따라야 한다.

### A Declarative Style of Design
> Once your design has intention-revealing interfaces, side-effect-free functions, and assertions, you are edging into declarative territory. Many of the benefits of declarative design are obtained once you have combinable elements that communicate their meaning, and have characterized or obvious effects, or no observable effects at all.

- 일단 너의 설계가 의도를 드러내는 인터페이스, 부작용이 없는 함수, 그리고 단언문을 가지고 있다면, 너는 선언적 영역으로 진입하게 된다.
- 선언적 디자인의 많은 이점들은 의미를 전달하는 조합 가능한 요소들을 가지거나, 특성화되었거나 명백한 효과를 가지거나 전혀 관찰할 수 없는 효과를 가질 때 얻어집니다.


> A supple design can make it possible for the client code to use a declarative style of design. To illustrate, the next section will bring together some of the patterns in this chapter to make the specification more supple and declarative.

- 유연한 디자인은 클라이언트 코드가 선언적인 디자인 스타일을 사용할 수 있도록 만들어 줄 수 있다.
- 설명을 위해, 다음 섹션에서는 이 장에서 다룬 몇 가지 패턴을 결합하여 명세를 더 유연하고 선언적으로 만들 것이다.


## 3.8 Drawing on Established Formalisms(이미 존재하는 형식화된 개념이나 체계를 활용하는 것)
> Creating a tight conceptual framework from scratch is something you can’t do every day. Sometimes you discover and refine one of these over the course of the life of a project. But you can often use and adapt conceptual systems that are long established in your domain or others, some of which have been refined and distilled over centuries. Many business applications involve accounting, for example. Accounting defines a well-developed set of entities and rules that make for an easy adaptation to a deep model and a supple design.

- 맨 처음부터 탄탄한 개념적 framework를 만드는 것은 매일 할 수 없는 일이다.
- 때떄로 너는 프로젝트 수명 동안 그것들 중 하나를 발견하고 개선하기도 한다.
- 그러나, 너는 종종 도메인이나 다른 분야에서 오랫동안 확립된 개념적 시스템을 사용하고 적응할 수 있다.
- 그 중 일부는 세기 동안 정제되고 정제된 것이다.
- 예를 들어, 많은 비즈니스 응용 프로그램에는 회계를 포함한다.
- 회계는 심층 모델과 유연한 설계에 쉽게 적응할 수 있도록 만들어진, 잘 개발된 엔티티와 및 규칙 세트를 정의한다.


> There are many such formalized conceptual frameworks, but my personal favorite is math. It is surprising how useful it can be to pull out some twist on basic arithmetic. Many domains include math somewhere. Look for it. Dig it out. Specialized math is clean, combinable by clear rules, and people find it easy to understand.

- 이와 같은 정형화된 개념적 프레임워크가 많이 있지만, 내 개인적인 취향은 수학이다.
- 기본 산술에 몇 가지 변형을 도입하는 것이 얼마나 유용한지 놀랍다.
- 많은 도메인은 어디에든 수학을 포함하고 있다.
- 찾아봐라.
- 파해쳐봐라.
- 전문 수학은 명확하고, 명확한 규칙에 따라 결합 가능하며, 사람들이 이해하기 쉽다.


> A real-world example, “Shares Math,” was discussed in Chapter 8 of the book, Domain-Driven Design.

- 실제 예로는 "주식 수학"이라는 것이 있습니다. 이는 도메인 주도 설계 책의 8장에서 논의되었습니다.


## 3.9 Conceptual Contours(개념적 윤곽)
> Sometimes people chop functionality fine to allow flexible combination. Sometimes they lump it large to encapsulate complexity. Sometimes they seek a consistent granularity, making all classes and operations to a similar scale. These are oversimplifications that don’t work well as general rules. But they are motivated by basic problems.

- 때때로 사람들은 유연한 조합을 허용하기 위해 기능을 세밀하게 나눈다.
- 때때로 그들은 복잡성을 캡슐화하기 위해 큰 덩어리로 묶기도 한다.
- 때때로 그들은 모든 클래스와 operation을 비슷한 규모로 만들기 위해 일관된 세분성을 추구한다.
- 이러한 것들은 일반적인 규칙으로는 잘 작동하지 않는 과도한 단순화이다.
- 그러나, 그들은 기본적인 문제들에 의해 동기부여받는다.


> When elements of a model or design are embedded in a monolithic construct, their functionality gets duplicated. The external interface doesn’t say everything a client might care about. Their meaning is hard to understand, because different concepts are mixed together.

- 모델이나 디자인의 요소들이 거대한 구조물에 내장되어 있을 때, 그들의 기능성이 중복된다.
- 외부 인터페이스는 클라이언트가 관심을 갖는 모든 것을 말하지 않는다.
- 그들의 의미는 다른 개념들이 서로 섞여 있기 때문에 이해하기 어렵다.


> Conversely, breaking down classes and methods can pointlessly complicate the client, forcing client objects to understand how tiny pieces fit together. Worse, a concept can be lost completely. Half of a uranium atom is not uranium. And of course, it isn’t just grain size that counts, but just where the grain runs.

- 반면에, 클래스와 메서드를 분해하는 것은 클라이언트 객체가 작은 조각들이 어떻게 서로 결합되어있는지에 대해 이해해도록 강요하면서, 
- 더 나쁜 경우에는 개념이 완전히 사라질 수 있다는 것이다.
- 우라늄 원자의 절반은 우라늄이 아니다.
- 물론, 중요한 것은 입자 크기만이 아니라 입자가 어디를 향해 달리는지가 중요하다.


Therefore:


> Decompose design elements (operations, interfaces, classes, and aggregates) into cohesive units, taking into consideration your intuition of the important divisions in the domain. Observe the axes of change and stability through successive refactorings and look for the underlying conceptual contours that explain these shearing patterns. Align the model with the consistent aspects of the domain that make it a viable area of knowledge in the first place.

- 도메인 안에서 너의 직관으로 중요한 구분을 고려하여, 설계 요소(작업, 인터페이스, 클래스 및 집합체)를 응집력 있는 단위로 분해해라.
- 연속적인 리팩토링을 통해, 변화와 안정성의 축을 관찰하고, 이러한 절단 패턴을 설명하는 기저 개념적 윤곽을 찾아라.
- 처음부터 도메인을 생존가능한 지식 영역으로 만드는 도메인의 일관된 측면과 모델을 일치시켜라.


> A supple design based on a deep model yields a simple set of interfaces that combine logically to make sensible statements in the ubiquitous language, and without the distraction and maintenance burden of irrelevant options.

- 깊은 모델을 기반으로 한 유연한 디자인은 일관된 언어로 합리적인 명제를 만들어내는 단순한 인터페이스 세트를 제공하며, 관련 없는 옵션의 혼란과 유지보수 부담 없이 그들을 조합할 수 있습니다.
- 심층모델을 기반으로 한 유연한 설계는 관련없는 옵션으로 인한 방해나 유지 관리 부담이 없이, 유비쿼터스 언어 내에서 합리적인 설명을 만들기 위해 논린적으로 결합된, 간단한 인터페이스를 제공한다.


