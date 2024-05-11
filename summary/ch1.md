# 1장. 모델 활용하기
## 1.1 개요
> Domain-Driven Design is an approach to the development of complex software in which we:
> 1. Focus on the core domain.
> 2. Explore models in a creative collaboration of domain practitioners and software practitioners.
> 3. Speak a ubiquitous language within an explicitly bounded context.
> This three-point summary of DDD depends on the definition of the terms, which are defined
in this booklet.
 
- 도메인 기반 설계(Domain-Driven Design)는 복잡한 소프트웨어 개발을 위한 접근 방식으로, 다음과 같습니다:
  1. 핵심 도매인에 집중해라.
  2. 도메인 전문가와 소프트웨어 실무자의 창의적인 협업을 통해 모델을 탐색해라.
  3. 명시적으로 bounded context 내에서 유비쿼터스 언어를 말해라.
- DDD에 대한 3가지 포인트 요약은 이 책자에 정의된 용어의 정의에 달려있다.


> Many projects do modeling work without getting much real benefit in the end. The patterns of DDD distill successful practices from projects where dramatic benefits have come from modeling. Taken together, they lay out a quite different approach to modeling and software development that runs from fine details to high-level vision. Rigorous modeling conventions must be balanced with free exploration of models in collaboration with non-technical people. Tactics and strategy must be combined to succeed, and DDD addresses both tactical and strategic design.

- 많은 프로젝트는 끝날 때까지 실질적인 이점을 얻지 못한 채 모델링 작업을 수행한다.
- DDD의 패턴들은 모델링을 통해 극적인 이점을 가져오는 여러 프로젝트의 성공적인 practice를 요약하여 추려낸다.   
- 종합하면, DDD의 패턴들은 미세한 세부 사항부터 높은 수준의 목표까지 이어지는 모델링 및 SW 개발에 대한 상당히 다른 접근 방식을 제시한다.
- 엄격한 모델링 규칙은 기술자가 아닌 사람들과 공동으로 모델을 자유롭게 탐색하는 것과 균형을 이루어야 한다.
- 전술과 전략은 성공하기 위해서는 결합되어야 하며 DDD는 전술적 설계와 전략적 설계를 모두 다룬다.


> 전술이란?
> - 전체적인 장기적인 목표를 이루기 위한 방법
>   
> 전략이란?
> - 특정한 상황에서 실질적인 행동을 포함한 단기적인 목표를 달성하기 위한 방법


## 1.2 Bounded Context
> Multiple models are in play on any large project. They emerge for many reasons. Two subsystems commonly serve very different user communities, with different jobs, where different models may be useful. Teams working independently may solve the same problem in different ways through lack of communication. The tool set may also be different, meaning that program code cannot be shared.

- 하나의 대규모 프로젝트에서는 여러 모델이 사용된다.
- 그들은 다양한 이유로 드러난다.
- 2개의 서브시스템은 서로 다른 사용자 커뮤니티를 대상으로 하며, 각각 서로 다른 작업을 수행하는데, 이는 서로 다른 모델이 유용할 수 있다.
- 독립적으로 작업하는 팀은 의사소통 부족으로 동일한 문제를 다른 방식으로 해결할 수 있다.
- 또한, tool 세트가 다를 수 있으몰, 프로그램 코드를 공유할 수 없다.


> Multiple models are inevitable, yet when code based on distinct models is combined, software becomes buggy, unreliable, and difficult to understand. Communication among team members becomes confused. It is often unclear in what context a model should not be applied.

- 여러 모델은 피할 수 없는 일이지만, 서로 다른 모델을 기반으로 한 코드가 결합되면, 소프트웨어가 버그가 발생하고, 신뢰성이 떨어지며, 이해하기 어려워진다.
- 팀 구성원 간의 의사소통이 혼란스러워진다.
- 어느 문맥에서 모델이 적용되어서 안되는지가 불분명한 경우가 종종 있다.

> Model expressions, like any other phrase, only have meaning in context.

- 다른 어구와 마찬가지로 모델 표현은 오직 문맥 속에서 의미가 있다.


Therefore:


> Explicitly define the context within which a model applies. Explicitly set boundaries in terms of team organization, usage within specific parts of the application, and physical manifestations such as code bases and database schemas. Apply Continuous Integration to keep model concepts and terms strictly consistent within these bounds, but don’t be distracted or confused by issues outside. Standardize a single development process within the context, which need not be used elsewhere.

- 모델이 적용되는 문맥을 명확히 정의해라.
- 팀 구성, 응용 프로그램의 특정 부분 내에서의 사용, 코드 베이스 및 데이터베이스 스키마와 같은 물리적 표현 측면에서 boundaries를 명시적으로 설정해라.
- CI를 적용하여 모델 개념과 용어를 이러한 boundary 내에서 엄격하게 일관성을 유지하되, 외부 이슈에 의해 산만해지거나 혼동되지 않도록 해라.
- 해당 context 내에서는 다른 곳에서 사용할 필요가 없는 단일 개발 프로세스를 표준화해라.


## 1.3 Ubiquitous Language
> To create a supple, knowledge-rich design calls for a versatile, shared team language, and a lively experimentation with language that seldom happens on software projects.

- 유연하고 지식이 풍부한 설계를 만들기 위해서는, 다재다능하고, 공유된 팀 언어, 그리고 소프트웨어 프로젝트에서 드물게 발생하는 언어에 대한 활발한 실험이 필요하다.


> Within a single bounded context, language can be fractured in ways that undermine efforts to apply sophisticated modeling. If the model is only used to draw UML diagrams for the technical members of the team, then it is not contributing to the creative collaboration at the heart of DDD.

- 단일 bounded context 내에서는 언어가 정교한 모델링을 적용하려는 노력을 약화시키는 방식으로 분열될 수 있다.
- 모델이 팀의 기술 멤버들을 위한 UML 다이어그램을 그리는 데만 사용된다면, 모델은 DDD의 핵심인 창의적인 협업에 기여하지 않는다.
  

> Domain experts use their jargon while technical team members have their own language tuned for discussing the domain in terms of design. The terminology of day-to-day discussions is disconnected from the terminology embedded in the code (ultimately the most important product of a software project). And even the same person uses different language in speech and in writing, so that the most incisive expressions of the domain often emerge in a transient form that is never captured in the code or even in writing.

- 도메인 전문가들은 자신들의 전문 용어를 사용하는 반면, 기술 팀 멤버들은 설계 관점에서 도메인을 논의하기 위해 조정된 자체 언어를 사용한다.
- 일상적인 토론의 용어는 코드(= 결국 소프트웨어 프로젝트의 가장 중요한 제품)에 내장된 용어와 분리되어 있다.
- 심지어 같은 사람이라도, 말하는 언어와 쓰는 언어가 다르기 때문에, 도메인의 가장 날카로운 표현은 종종 코드나 글에서도 절대로 포착되지 않는 일시적인 형태로 나타난다.

> Translation blunts communication and makes knowledge crunching anemic.

- 번역은 커뮤니케이션을 둔화시키고 지식을 빈약하게 만든다.


> Yet none of these dialects can be a common language because none serves all needs.

- 그러나 이러한 다양한 방언 중 어느 것도 모든 요구를 충족시키지 못하기 때문에, 공통 언어가 될 수 없다.


> Domain experts should object to terms or structures that are awkward or inadequate to convey domain understanding; developers should watch for ambiguity or inconsistency that will trip up design.

- 도메인 전문가는 도메인을 이해하는데 어색하거나 부적절한 용어나 구조에 이의를 제기해야 한다.
- ; 개발자는 설계를 방해할 수 있는 모호함이나 불일치를 주의 깊게 관찰해야 한다.
  

> Play with the model as you talk about the system. Describe scenarios out loud using the elements and interactions of the model, combining concepts in ways allowed by the model. Find easier ways to say what you need to say, and then take those new ideas back down to the diagrams and code.

- 시스템에 대해 이야기하면서 모델을 가지고 놀아봐라.
- 모델에서 허용하는 방식으로 개념들을 결합하고, 모델의 요소와 상호 작용을 사용하여, 시나리오를 소리내어 설명해라.
- 말할 필요가 있는 것을 더 쉽게 말하는 방법을 찾고, 그리고 나서 새로운 아이디어를 다시 다이어그램과 코드로 가져와라.


> With a ubiquitous language, the model is not just a design artifact. It becomes integral to everything the developers and domain experts do together.

- 유비쿼터스 언어를 사용하면, 모델은 단순히 설계 아티팩트가 아니다.
- 모델은 개발자와 도메인 전문가들이 함께 하는 모든 것에 필수적인 요소가 된다.


Therefore:


> Use the model as the backbone of a language. Commit the team to exercising that language relentlessly in all communication within the team and in the code. Within a bounded context, use the same language in diagrams, writing, and especially speech.

- 언어의 중추로 모델을 사용해라.
- 팀 내에서 그리고 코드에서, 모든 의사소통에서 해당 언어를 끊임없이 사용하도록 강요해라.  
- bounded context 내에서, 다이어그램, 글쓰기 및 특히 스피치에서 동일한 언어를 사용해라.


> Recognize that a change in the language is a change to the model.

- 언어의 변화가 모델의 변화임을 인지해라.


> Iron out difficulties by experimenting with alternative expressions, which reflect alternative models. Then refactor the code, renaming classes, methods, and modules to conform to the new model. Resolve confusion over terms in conversation, in just the way we come to agree on the meaning of ordinary words.

- 대안 모델을 반영하는 대체 표현을 실험하여 어려움을 해결해라. 
- 그런 다음 새로운 모델에 맞게 클래스, 메서드 및 모듈의 이름을 바꾸어 코드를 리팩터링해라.
- 일상적인 단어의 의미에 동의하는 것과 마찬가지로, 대화에서 용어에 대한 혼란을 해결해라.


## 1.4 Continuous Integration

## 1.5 Model-Driven Design

## 1.6 Hands-on Modelers

## 1.7 Refactoring Toward Deeper Insight


