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
### Context Map
### Partnership * 
### Shared Kernel 
### Customer/Supplier Development
### Conformist
### Anticorruption Layer
### Open-host Service
### Published Language
### Separate Ways 
### Big Ball of Mud * 

## 5장. 전략적 설계를 위한 Distillation





### Core Domain
### Generic Subdomains
### Domain Vision Statement 
### Highlighted Core
### Cohesive Mechanisms
### Segregated Core
### Abstract Core

<img width="573" alt="스크린샷 2024-05-20 오후 1 37 25" src="https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/assets/60481383/bdd86f01-b374-423b-b68c-4cd7fdf95b52">

## 6장. 전략적 설계를 위한 대규모 구조
- 비즈니스가 발전함에 따라 시스템은 점점 거대해지고 복잡해진다.
- 따라서, 시스템의 큰 틀을 파악하기 위해 "대규모 구조"가 필요하다.
- 대규모 구조가 없다면, 개발자는 시스템 전체를 이해해야만 특정 부분을 이해할 수 있게 되어 비효율적이다.
- 각 부분의 책임에 대한 자세한 지식 없이도 전체 시스템 내에서 각 부분의 위치와 역할을 이해할 수 있도록 하는 것이 중요하다.
- 또한, 시스템은 시간이 지남에 따라 변화하므로 유연하게 설계해야 한다 (`Evolving Order`).
- 대규모 구조는 최소한의 단위로 설정하는 것이 좋다. 부적합한 구조는 없는 것보다 더 나쁠 수 있다.
- 이러한 대규모 구조를 설계하기 위해 4가지 주요 패턴이 있다:
1. `System Metaphor`: 시스템의 전반적인 이해를 돕는 은유를 사용하는 패턴 (예: 이미지 썸네일 생성 "파이프라인").
2. `Responsibility Layers`: 관심사 분리를 통해 시스템을 계층 구조로 나누는 패턴(예 : 인프라 계층, 도메인 계층 등)
3. `Knowledge Level`: 대규모 구조를 표현하고 이해하는 방법을 제공하는 패턴.
4. `Pluggable Component Framework`: 독립적으로 개발되고 교체 가능한 컴포넌트를 통해 시스템을 모듈화하는 패턴(예: JDBC).




### Evolving Order
- 시스템이 시간이 지남에 따라 변화하고 발전할 수 있도록 유연하게 설계.
### 대규모 구조의 패턴 1 : System Metaphor
- 시스템의 개념을 쉽게 이해할 수 있는 비유나 은유.
### Responsibility Layers
- 각 계층이 특정 책임을 가지도록 시스템을 계층 구조로 나누는 것.
### Knowledge Level
-  지식 수준은 도메인 전문가의 지식을 시스템 설계에 반영하는 것을 의미한다.
-  이때, 도메인 지식을 명시적으로 표현하고 관리하는 것.
### Pluggable Component Framework
- 독립적으로 개발되고 교체 가능한 컴포넌트로 시스템을 모듈화하는 것.

