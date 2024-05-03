# 5장. 전략적 설계를 위한 Distillation
## 5.1 개요
> How do you focus on your central problem and keep from drowning in a sea of side issues?
- 너는 어떻게 핵심 문제에 집중하고, side 이슈의 바다에 빠자지 않도록 하나요?

> Distillation is the process of separating the components of a mixture to extract the essence in a form that makes it more valuable and useful. A model is a distillation of knowledge. With every refactoring to deeper insight, we abstract some crucial aspect of domain knowledge and priorities. Now, stepping back for a strategic view, this chapter looks at ways to distinguish broad swaths of the model and distill the domain model as a whole.

- Distillation은 혼합물의 컴포넌트에서 좀더 가치 있고 유용하게 만드는 형태로 핵심을 추출하는 과정이다. 
- 모델은 지식의 distillation 이다. (-> 중요한 부분만 추상화 시킨게 모델이므로?)
- 더 깊은 통창력을 얻기 위한 모든 리팩토링을 통해, 우리는 도메인 지식과 우선순위의 몇 가지 중요한 측면을 추상화한다.
- 이제, 전략적 관점으로 돌아가서, 이 챕터에서는 모델의 넓은 범위를 구별하고 도메인 모델을 전체적으로 정제하는 방법을 살펴본다.


## 5.2 Core Domain
> In a large system, there are so many contributing components, all complicated and all absolutely necessary to success, that the essence of the domain model, the real business asset, can be obscured and neglected.

- 대규모 시스템에서는 기여하는 컴포넌트들이 너무 많고, 모두 복잡하며 성공하기 위해 절대적으로 필요하기 때문에, 실제 비즈니스 자산인 도메인 모델의 본질이 모호해지고 무시될 수 있다. 

> It is harsh reality that not all parts of the design are going to be equally refined. Priorities must be set. To make the domain model an asset, the critical core of that model has to be sleek and fully leveraged to create application functionality. But scarce, highly skilled developers tend to gravitate to technical infrastructure or neatly definable domain problems that can be understood without specialized domain knowledge.

- 디자인의 모든 부분이 동등하게 다듬어지지 않는다는 것이 가혹한 현실이다.
- 우선순위를 설정해야 한다.
- 도메인 모델을 자산으로 만들기 위해서, 모델의 중대한 핵심이 애플리케이션 기능을 만들기 위해 잘 녹여져(sleek) 있어야 하며, 완전히 활용되어야(fully leveraged) 한다.
- 그러나, 부족하고 매우 skilled한 개발자들은 특정 도메인 지식 없이 이해할 수 있는 기술적 인프라나 깔끔하게 정의된 도메인 문제에 끌리는 경향이 있다.


Therefore:

> Boil the model down. Define a core domain and provide a means of easily distinguishing it from the mass of supporting model and code. Bring the most valuable and specialized concepts into sharp relief. Make the core small.
- 도메인을 끓여라!
- 핵심 도메인을 정의하고, 그것과 그것을 지원하는 모델 및 코드의 덩어리를 쉽게 구별할 수 있는 수단을 제공해라.
- 가장 가치 있고 전문적인 개념을 날카로운 구조(sharp relief)로 가져와라. 
- 코어를 작게 만들어라.

> Apply top talent to the core domain, and recruit accordingly. Spend the effort in the core to find a deep model and develop a supple design—sufficient to fulfill the vision of the system.

- 핵심 도메인에 최고의 인재를 투입하고, 그에 따라 채용해라.
- 시스템의 비전을 충족하기에 충분한 심층적인 모델을 찾고 유연한 디자인을 개발하기 위해, 핵심에 노력을 기울여라. 


> Justify investment in any other part by how it supports the distilled core.
- distilled 된 핵심을 어떻게 지원하느냐에 따라 다른 부분에 대한 투자를 정당화시켜라





## 5.3 Generic Subdomains
## 5.4 Domain Vision Statement
## 5.5 Highlighted Core
## 5.6 Cohesive Mechanisms(응집력 있는 메커니즘)
> Computations sometimes reach a level of complexity that begins to bloat the design. The conceptual “what” is swamped by the mechanistic “how.” A large number of methods that provide algorithms for resolving the problem obscure the methods that express the problem.
- 가끔 계산이 너무 복잡해져서 설계를 부풀리기 시작하는 경우도 있다.
- 개념적으로 중심이 되는 "무엇(what)"이 기계적인 "어떻게(how)"에 묻혀 버리는 경우도 있다.
- 문제를 해결하기 위한 알고리즘을 제공하는 많은 방법들이 문제를 표현하는 방법들을 모호하게 한다.

Therefore:

> Partition a conceptually cohesive mechanism into a separate lightweight framework. Particularly watch for formalisms or well-documented categories of algorithms. Expose the capabilities of the framework with an intention-revealing interface. Now the other elements of the domain can focus on expressing the problem (“what”), delegating the intricacies of the solution (“how”) to the framework.

- 개념적으로 응집력 있는 메커니즘을 별도의 경량 프레임워크로 분할해라.
- 특히, 형식주의 또는 잘 문서화된 알고리즘 카테고리를 주의 깊게 살펴봐라.
- 의도를 드러내는 인터페이스를 통해 프레임워크의 기능을 노출시켜라.
- 이제 도메인의 다른 요소들은 문제("무엇")를 표현하는 데 집중할 수 있으며, 프레임워크에 해결책("어떻게")의 복잡성을 위임한다.

> Factoring out generic subdomains reduces clutter, and cohesive mechanisms serve to encapsulate complex operations. This leaves behind a more focused model, with fewer distractions that add no particular value to the way users conduct their activities. But you are unlikely ever to find good homes for everything in the domain model that is not core. The segregated core takes a direct approach to structurally marking off the core domain.

- 일반적인 서브도메인을 나누면 혼란이 줄어들고, 응집력 있는 메커니즘은 복잡한 operation을 캡슐화하는 역할을 한다.
- 이로써 더 집중된 모델이 만들어지고, 사용자가 활동을 수행하는 방법에 특별한 가치를 추가하지 않는 방해 요소들이 줄어든다.
- 그러나, 핵심이 되지 않는 도메인 모델의 모든 것에 대해 항상 적절한 곳에 찾을 수는 없다.
- 분리된 핵심은 핵심 도메인을 구조적으로 표시하는 직접적인 접근 방식을 취한다.


## 5.7 Segregated Core
> Elements in the model may partially serve the core domain and partially play supporting roles. Core elements may be tightly coupled to generic ones. The conceptual cohesion of the core may not be strong or visible. All this clutter and entanglement chokes the core. Designers can’t clearly see the most important relationships, leading to a weak design.

- 모델 내의 요소들은 부분적으로 핵심 도메인을 제공하고, 부분적으로 supporting 역할을 합니다.
- 핵심 요소들은 일반적인 요소들과 강하게 결합될 수 있다.
- 핵심의 개념적 응집력이 강하지 않거나 명확하지 않을 수 있다.
- 이 모든 혼란과 엉킴은 핵심을 질식시킨다.
- 설계자들은 가장 중요한 관계를 명확하게 볼 수 없어, 설계가 약해지는 결과를 초래할 수 있다.

Therefore:

> Refactor the model to separate the core concepts from supporting players (including ill- defined ones) and strengthen the cohesion of the core while reducing its coupling to other code. Factor all generic or supporting elements into other objects and place them into other packages, even if this means refactoring the model in ways that separate highly coupled elements.

- 핵심 개념을 지원 요소들(불명확한 요소 포함)과 분리하고, 핵심 개념의 응집력을 강화하는 동시에 다른 코드와의 결합을 줄이도록 모델을 리팩토링해라. 
- 비록 그것이 고도로 결합력이 높은 요소를 분리하는 방식으로 모델을 리패토링하는 것을 의미하더라도, 모든 일반적 요소(=일반 도메인) 또는 지원 요소들(=지원 도메인)을 다른 객체로 분리하고, 이를 다른 패키지에 배치해라.


## 5.8 Abstract Core
> Even the core domain model usually has so much detail that communicating the big picture can be difficult.
- 핵심 도메인 모델조차도 대개 상세한 내용이 많아서 전체적인 그림을 전달하는 것이 어려울 수 있다.

> When there is a lot of interaction between subdomains in separate modules, either many references will have to be created between modules, which defeats much of the value of the partitioning, or the interaction will have to be made indirect, which makes the model obscure.
- 분리된 모듈 사이의 서브도메인 간 상호작용이 많은 경우, 모듈 간에 많은 참조가 생성되어야 하며, 이는 분할의 많은 가치를 상실시킵니다. 또는 상호작용을 간접적으로 만들어야 하며, 이는 모델을 어렵게 만듭니다.

Therefore:

> Identify the most fundamental differentiating concepts in the model and factor them into distinct classes, abstract classes, or interfaces. Design this abstract model so that it expresses most of the interaction between significant components. Place this abstract overall model in its own module, while the specialized, detailed implementation classes are left in their own modules defined by subdomain.
- 모델에서 가장 기본적인 차별화되는 개념을 식별하고, 이를 별도의 클래스, 추상 클래스 또는 인터페이스로 분리해라. 
- 중요한 컴포너트 간의 상호 작용을 대부분 표현하도록 이 추상 모델을 설계해라.
- 이런 추상적인 전체 모델을 그 자체 모듈에 배치하는 반면, 전문화되고 상세한 구현 클래스는 하위 도메인에 의해 정의된 자신의 모듈에 남겨둬라.
  
