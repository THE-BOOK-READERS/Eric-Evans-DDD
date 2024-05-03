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
- 그러므로,

> Boil the model down. Define a core domain and provide a means of easily distinguishing it from the mass of supporting model and code. Bring the most valuable and specialized concepts into sharp relief. Make the core small.
- 도메인을 끓여라!
- 핵심 도메인을 정의하고, 그것과 그것을 지원하는 모델 및 코드의 덩어리를 쉽게 구별할 수 있는 수단을 제공해라.


> Apply top talent to the core domain, and recruit accordingly. Spend the effort in the core to find a deep model and develop a supple design—sufficient to fulfill the vision of the system.

- 핵심 도메인에 최고의 인재를 투입하고, 그에 따라 채용해라.
- 시스템의 비전을 충족하기에 충분한 심층적인 모델을 찾고 유연한 디자인을 개발하기 위해, 핵심에 노력을 기울여라. 


> Justify investment in any other part by how it supports the distilled core.
- distilled 된 핵심을 어떻게 지원하느냐에 따라 다른 부분에 대한 투자를 정당화시켜라





## 5.3 Generic Subdomains
## 5.4 Domain Vision Statement
## 5.5 Highlighted Core
## 5.6 Cohesive Mechanisms
## 5.7 Segregated Core
## 5.8 Abstract Core


