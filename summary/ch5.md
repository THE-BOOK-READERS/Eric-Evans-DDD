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

> It is harsh reality that not all parts of the design are going to be equally refined. Priorities must be set. To make the domain model an asset, the critical core of that model has to be sleek and fully leveraged to create application functionality. But scarce, highly skilled developers tend to gravitate to technical infrastructure or neatly definable domain problems that can be understood without specialized domain knowledge.

Therefore:
> Boil the model down. Define a core domain and provide a means of easily distinguishing it from the mass of supporting model and code. Bring the most valuable and specialized concepts into sharp relief. Make the core small.

> Apply top talent to the core domain, and recruit accordingly. Spend the effort in the core to find a deep model and develop a supple design—sufficient to fulfill the vision of the system.

> Justify investment in any other part by how it supports the distilled core.
















## 5.3 Generic Subdomains
## 5.4 Domain Vision Statement
## 5.5 Highlighted Core
## 5.6 Cohesive Mechanisms
## 5.7 Segregated Core
## 5.8 Abstract Core


