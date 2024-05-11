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

## 1.4 Continuous Integration

## 1.5 Model-Driven Design

## 1.6 Hands-on Modelers

## 1.7 Refactoring Toward Deeper Insight


