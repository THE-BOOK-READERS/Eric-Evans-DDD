# DDD Reference - Definitions and Pattern Summaries











## 1장. 모델 활용하기
### Bounded Context 
### Ubiquitous Language 
### Continuous Integration 
### Model-Driven Design 
### Hands-on Modelers 
### Refactoring Toward Deeper Insight

## 2장. 모델 주도 설계의 구성 요소
### Layered Architecture
### Entities 
### Value Objects
### Domain Events * 
### Services 
### Modules 
### Aggregates
### Repositories
### Factories 

## 3장. 유연한 설계
### Intention-Revealing Interfaces 
### Side-Effect-Free Functions 
### Assertions
### Standalone Classes
### Closure of Operations 
### Declarative Design
### Drawing on Established Formalisms
### Conceptual Contours

## 4장. 전략적 설계를 위한 Context Mapping

- Bounded Context를 분리
- 각 컨택스트 간의 관계와 상호작용을 시각적으로 표현해놓는게 필요하다. (`Context Map`)
- 각 컨택스트 간의 관계에는 다양한 관계가 존재할 수 있는데, 크게 8가지 형태로 구분할 수 있다.
1. Partnership :
2. Shared Kernel 
3. Customer/Supplier Development
4. Conformist
5. Anticorruption Layer
6. Open-host Service(feat. Published Language)
7. Separate Ways 
8. Big Ball of Mud : 이건 그냥 컨텍스트 안 나누는게 더 나은 경우에 사용한다.



## 5장. 전략적 설계를 위한 Distillation

- 프로젝트에 투입될 수 있는 자원(예 : 시간, 돈, 사람 등)은 한정되어 있다.
- 따라서, 비즈니스의 핵심 요소([Core Domain](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch5.md#52-core-domain))와 그렇지 않은 요소([Generic Subdomains](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch5.md#53-generic-subdomains))를 구별하여 자원을 효율적으로 배분하기 위한 방법이 필요하다.
- 이 방법이 `Distillation`이다.
- Distillation을 통해 중요한 부분에 집중하고, 그렇지 않은 부분은 간소화하거나 외부에 위임할 수 있다.
- 이때, 어떤 것이 중요하고, 그렇지 않은지에 대한 기준을 정할 수 있게 해주는 문서들이 있는데, [Domain Vision Statement(1p)](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch5.md#54-domain-vision-statement-%EB%8F%84%EB%A9%94%EC%9D%B8-%EB%B9%84%EC%A0%84-%EC%84%A0%EC%96%B8%EB%AC%B8)과 [Highlighted Core(3~7p)](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch5.md#55-highlighted-core)이다.
- 그리고, 이렇게 분리할 때, 응집력 있게 분리해야된다. ([Cohesive Mechanisms](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch5.md#56-cohesive-mechanisms%EC%9D%91%EC%A7%91%EB%A0%A5-%EC%9E%88%EB%8A%94-%EB%A9%94%EC%BB%A4%EB%8B%88%EC%A6%98))
- 그 결과, 분리된 핵심 도메인([Segregated Core](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch5.md#57-segregated-core))을 발견할 수 있다.
- 이렇게 분리된 코어조차도 상세한 내용이 많아서 전체적인 그림을 전달하는 것이 어려울 수 있다.
- 그럴때에는 추상화 시켜라.([Abstract Core](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch5.md#58-abstract-core))

> 핵심, 지원, 일반 도메인 예시

<img width="573" alt="스크린샷 2024-05-20 오후 1 37 25" src="https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/assets/60481383/bdd86f01-b374-423b-b68c-4cd7fdf95b52">

## 6장. 전략적 설계를 위한 대규모 구조
- 비즈니스가 발전함에 따라 시스템은 점점 거대해지고 복잡해진다.
- 따라서, 시스템의 큰 틀을 파악하기 위해 `대규모 구조`가 필요하다.
- 대규모 구조가 없다면, 개발자는 시스템 전체를 이해해야만 특정 부분을 이해할 수 있게 되어 비효율적이다.
- 각 부분의 책임에 대한 자세한 지식 없이도 전체 시스템 내에서 각 부분의 위치와 역할을 이해할 수 있도록 하는 것이 중요하다.
- 또한, 시스템은 시간이 지남에 따라 변화하므로 유연하게 설계해야 한다 ([Evolving Order](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch6.md#62-evolving-order%EC%A7%84%ED%99%94%ED%95%98%EB%8A%94-%EC%A7%88%EC%84%9C)).
- 대규모 구조는 최소한의 단위로 설정하는 것이 좋다. 부적합한 구조는 없는 것보다 더 나쁠 수 있다.
- 이러한 대규모 구조를 설계하기 위해 4가지 주요 패턴이 있다 (-> 이 4가지 패턴을 모두다 사용하는게 대규모 구조가 아니라, 필요한 패턴만 적용시켜도 대규모 구조 도구를 활용한 것?)
1. [System Metaphor](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch6.md#63-system-metaphor) : 시스템의 전반적인 이해를 돕는 은유를 사용하는 패턴 (예: 이미지 썸네일 생성 "파이프라인").
2. [Responsibility Layers](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch6.md#64-responsibility-layers) : 관심사 분리를 통해 시스템을 계층 구조로 나누는 패턴(예 : 인프라 계층, 도메인 계층 등)
3. [Knowledge Level](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch6.md#65-knowledge-level) : 대규모 구조를 표현하고 이해하는 방법을 제공하는 패턴.
4. [Pluggable Component Framework](https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/blob/main/summary/ch6.md#66-pluggable-component-framework) : 독립적으로 개발되고 교체 가능한 컴포넌트를 통해 시스템을 모듈화하는 패턴(예: JDBC).

