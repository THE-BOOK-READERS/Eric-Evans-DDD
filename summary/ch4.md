# 4장. 전략적 설계를 위한 Context Mapping
## 4.1 개요
### 4.1.1 bounded context
- 어떤 모델이 정의되고 적용되는 경계에 대한 설명이다.
- 전형적으로, 서브시스템이나 특정 팀의 작업과 관련된 영역을 나타낸다.

### 4.1.2 upstream-downstream
- upstream 그룹의 액션은 downstream 그룹의 액션에 영향을 주지만, downstream 그룹의 액션은 upstream 그룹의 액션에 큰 영향을 미치지 않는 2개의 그룹 사이의 관계이다.
- upstream 팀은 downstream 팀의 운명과 관계없이 성공할 수 있다.

### 4.1.3 mutually dependent (상호 의존적)
- 서로 분리된 맥락에서 2개의 소프트웨어 개발 프로젝트가 둘다 성공 delivery되어야 하는 상황이다.
- (일반적으로 우리가 피하려는 상황이지만) 2개의 시스템이 서로 다른 시스템의 정보나 기능에 의존할 때, 우리는 자연스럽게 그들이 구축한 프로젝트를 상호 의존적인 것으로 볼 수 있다.
- 하지만, 시스템의 종속성이 한 방향으로만 실행되는 상호 의존적 프로젝트들 또한 있을 수 있다.
- 종속 시스템이 해당 시스템과 해당 시스템과의 통합 없이는 가치가 거의 없는 경우, (아마도 이것이 사용되는 유일한 장소이기 때문에) 종속 시스템을 delivery하지 못한 다면, 두 프로젝트 모두 실패하게 된다.

### 4.1.4 free (자유)
- 다른 context에서의 개발 작업 방향, 성공 또는 실패가 delivery에 거의 영향을 미치지 않는 소프트웨어 개발 컨텍스트

> delivery 란 무엇인가?
>
> - 제품이나 소프트웨어가 최종적으로 사용자에게 전달되는 것


## 4.2 Context Map


## 4.3 Partnership


## 4.4 Shared Kernel


## 4.5 Customer/Supplier Development



## 4.6 Conformist

## 4.7 Anticorruption Layer

## 4.8 Open-host Service

## 4.9 Published Language

## 4.10 Separate Ways

## 4.11 Big Ball of Mud


