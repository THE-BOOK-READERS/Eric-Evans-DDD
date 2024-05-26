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

- 

Therefore:


> Name classes and operations to describe their effect and purpose, without reference to the means by which they do what they promise. This relieves the client developer of the need to understand the internals. These names should conform to the ubiquitous language so that team members can quickly infer their meaning. Write a test for a behavior before creating it, to force your thinking into client developer mode.

- 그들이 약속한 것을 이해하는 수단에 대한 reference 없이도, 그들의 효과와 목적을 설명하기 하도록 클래스와 동작을 네이밍해라. 
- 이것은 클라이언트 개발자가 내부 구조를 이해할 필요가 없게 한다.
- 이러한 이름은 팀 구성원들이 그 의미를 빠르게 유추할 수 있도록, 유비쿼터스 언어로 형성되어야 한다.
- 클라이언트 개발자 모드로 사고하도록 강제하기 위해, 그것이 생성하기 전에 동작에 대한 테스트를 작성해라. (-> TDD 하라는 말인가?)




## 3.3 Side-Effect-Free Functions
## 3.4 Assertions
## 3.5 Standalone Classes
## 3.6 Closure of Operations
## 3.7 Declarative Design
## 3.8 Drawing on Established Formalisms
## 3.9 Conceptual Contours
