# Eric-Evans-DDD

도메인 주도 설계 - 소프트웨어의 복잡성을 다루는 지혜

<p align="center">
 <img width="300px" src="https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/assets/20085849/5a92ab4b-9e91-41f5-b413-59958ee4620f">
</p>

# 포스팅

## 01부 동작하는 도메인 모델 만들기

- 도메인 주도 설계에서의 모델의 유용성
- 소프트웨어의 본질

- [01장 지식 탐구](./chapter01/)

  - 효과적인 모델링의 요소
  - 지식 탐구
  - 지속적인 학습
  - 지식이 풍부한 설계
  - 심층 모델

- 02장 의사소통과 언어 사용

  - UBIQUITOUS LANGUAGE (보편 언어)
  - 크게 소리내어 모델링하기
  - 한 팀, 한 언어
  - 문서와 다이어그램

- 03장 모델과 구현의 연계
  - MODEL-DRIVEN DESIGN (모델 주도 설계)
  - 모델링 패러다임과 도구 지원
  - 내부 드러내기: 왜 모델이 사용자에게 중요한가
  - HANDS-ON MODELER (실천적 모델러)

## 02부 모델 주도 설계의 기본 요소

- 04장 도메인의 격리

  - LAYERED ARCHITECTURE (계층형 아키텍처)
  - 도메인 계층은 모델이 살아가는 곳
  - SMART UI(지능형 UI) "안티 패턴"
  - 다른 종류의 격리

- 05장 소프트웨어에서 표현되는 모델

  - 연관관계
  - ENTITY (엔티티, 참조객체라고도 함)
  - VALUE OBJECT (값 객체)
  - SERVICE(서비스)
  - MODULE(모듈, 패키지라고도 함)
  - 모델링 패러다임

- 06장 도메인 객체의 생명주기

  - AGGREGATE (집합)
  - FACTORY (팩터리)
  - REPOSITORY (리파지터리)
  - 관계형 데이터베이스를 위한 객체 설계

- 07장 언어의 사용(확장 예제)
  - 화물 해운 시스템 소개
  - 도메인 격리: 응용 기능 소개
  - ENTITY와 VALUE OBJECT의 구분
  - 해운 도메인의 연관관계 설계
  - AGGREGATE의 경계
  - REPOSITORY의 선정
  - 시나리오 연습
  - 객체 생성
  - 리팩터링할 시간: Cargo AGGREGATE의 설계 대안
  - 해운 모델의 MODULE
  - 새로운 기능 도입: 할당량 검사
  - 최종 검토

## 03부 더 심층적인 통찰력을 향한 리팩터링

- 리팩터링 수준
- 심층 모델
- 심층 모델/유연한 설계
- 발견 과정

- 08장 도약

  - 도약에 관한 일화

- 09장 암시적인 개념을 명확하게

  - 개념 파헤치기
  - 다소 불명확한 개념의 모델링
  - SPECIFICATION (명세)

- 10장 유연한 설계

  - INTENTION-REVEALING INTERFACE (의도를 드러내는 인터페이스)
  - SIDE -EFFECT-FREE FUNCTION (부수효과가 없는 함수)
  - ASSERTION (단정)
  - CONCEPTUAL CONTOUR (개념적 윤곽)
  - STANDALONE CLASS (독립형 클래스)
  - CLOSURE OF OPERATION (연산의 닫힘)
  - 선언적 설계
  - 선언적인 형식의 설계
  - 받음각

- 11장 분석 패턴의 적용

- 12장 모델과 디자인 패턴의 연결

  - STRATEGY (POLICY라고도 함)
  - COMPOSITE (복합체)
  - 그렇다면 FLYWEIGHT는?

- 13장 더 심층적인 통찰력을 향한 리팩터링
  - 시작
  - 조사팀
  - 선행 기술
  - 개발자를 위한 설계
  - 타이밍
  - 위기를 기회로

## 04부 전략적 설계

- 14장 모델의 무결성 유지

  - BOUNDED CONTEXT (제한된 컨텍스트)
  - CONTINUOUS INTEGRATION (지속적인 통합)
  - CONTEXT MAP (컨텍스트 맵)
  - BOUNDED CONTEXT 간의 관계
  - SHARED KERNEL (공유 커널)
  - CUSTOMER/SUPPLIER DEVELOPMENTTEAM (고객/공급자 개발 팀)
  - CONFORMIST (준수자)
  - ANTICORRUPTION LAYER (오류 방지 계층)
  - SEPARATE WAYS (각자의 길)
  - OPEN HOST SERVICE (공개 호스트 서비스)
  - PUBLISHED LANGUAGE (공표된 언어)
  - 코끼리 통일하기
  - 모델의 컨텍스트 전략 선택
  - 변형

- 15장 디스틸레이션

  - CORE DOMAIN (핵심 도메인)
  - 디스틸레이션의 단계적 확대
  - GENERIC SUBDOMAIN (일반 하위 도메인)
  - DOMAIN VISION STATEMENT (도메인 비전 선언문)
  - HIGHLIGHTED CORE (강조된 핵심)
  - COHESIVE MECHANISM (응집력 있는 메커니즘)
  - 선언적 형식의 디스틸레이션
  - SEGREGATED CORE (분리된 핵심)
  - ABSTRACT CORE (추상화된 핵심)
  - 심층 모델의 디스틸레이션
  - 리팩터링의 대상 선택

- 16장 대규모 구조

  - EVOLVING ORDER (발전하는 질서)
  - SYSTEM METAPHOR (시스템 은유)
  - RESPONSIBILITY LAYER (책임 계층)
  - KNOWLEDGE LEVEL (지식 수준)
  - PLUGGABLE COMPONENT FRAMEWORK (착탈식 컴포넌트 프레임워크)
  - 구조는 얼마나 제약성을 지녀야 하는가?
  - 잘 맞아떨어지는 구조를 향한 리팩터링

- 17장 전략의 종합

  - 대규모 구조와 BOUNDED CONTEXT와의 결합
  - 대규모 구조와 디스틸레이션과의 결합
  - 평가 먼저
  - 누가 전략을 세우는가?
  - 전략적 설계 결정을 위한 6가지 필수 요소
