# Eric-Evans-DDD

도메인 주도 설계 - 소프트웨어의 복잡성을 다루는 지혜

<p align="center">
 <img width="300px" src="https://github.com/THE-BOOK-READERS/Eric-Evans-DDD/assets/20085849/5a92ab4b-9e91-41f5-b413-59958ee4620f">
</p>

# 포스팅

<p><b>▣ 01부  동작하는 도메인 모델 만들기</b><br>
도메인 주도 설계에서의 모델의 유용성<br>
소프트웨어의 본질<br>
<br>
<b>01장   지식 탐구</b><br>
효과적인 모델링의 요소<br>
지식 탐구<br>
지속적인 학습<br>
지식이 풍부한 설계<br>
심층 모델<br>
<br>
<b>02장   의사소통과 언어 사용</b><br>
UBIQUITOUS LANGUAGE (보편 언어)<br>
크게 소리내어 모델링하기<br>
한 팀, 한 언어<br>
문서와 다이어그램<br>
- 글로 쓴 설계 문서<br>
- 실행 가능한 기반<br>
설명을 위한 모델<br>
<br>
<b>03장   모델과 구현의 연계</b><br>
MODEL-DRIVEN DESIGN (모델 주도 설계)<br>
모델링 패러다임과 도구 지원<br>
내부 드러내기: 왜 모델이 사용자에게 중요한가<br>
HANDS-ON MODELER (실천적 모델러)<br>
<br>
<b>▣ 02부   모델 주도 설계의 기본 요소<br>
<br>
04장   도메인의 격리</b><br>
LAYERED ARCHITECTURE (계층형 아키텍처)<br>
- 계층 간 관계 설정<br>
- 아키텍처 프레임워크<br>
도메인 계층은 모델이 살아가는 곳<br>
SMART UI(지능형 UI) "안티 패턴"<br>
다른 종류의 격리<br>
<br>
<b>05장   소프트웨어에서 표현되는 모델</b><br>
연관관계<br>
ENTITY (엔티티, 참조객체라고도 함)<br>
- ENTITY 모델링<br>
- 식별 연산의 설계<br>
VALUE OBJECT (값 객체)<br>
- VALUE OBJECT의 설계<br>
- VALUE OBJECT를 포함한 연관관계 설계<br>
SERVICE(서비스)<br>
- SERVICE와 격리된 도메인 계층<br>
- 구성 단위<br>
- SERVICE에 접근하기<br>
MODULE(모듈, 패키지라고도 함)<br>
- 기민한 MODULE<br>
- 인프라스트럭처 주도 패키지화의 함정<br>
모델링 패러다임<br>
- 객체 패러다임이 지배적인 이유<br>
- 객체 세계에서 객체가 아닌 것들<br>
- 패러다임이 혼재할 때 MODEL-DRIVEN DESIGN 고수하기<br>
<br>
<b>06장   도메인 객체의 생명주기</b><br>
AGGREGATE (집합)<br>
FACTORY (팩터리)<br>
- FACTORY와 FACTORY의 위치 선정<br>
- 생성자만으로 충분한 경우<br>
- 인터페이스 설계<br>
- 불변식 로직의 위치<br>
- ENTITY FACTORY와 VALUE OBJECT FACTORY<br>
- 저장된 객체의 재구성<br>
REPOSITORY (리파지터리)<br>
- REPOSITORY에 질의하기<br>
- 클라이언트 코드가 REPOSITORY 구현을 무시한다 (개발자는 그렇지 않지만)<br>
- REPOSITORY 구현<br>
- 프레임워크의 활용<br>
- FACTORY와의 관계<br>
관계형 데이터베이스를 위한 객체 설계<br>
<br>
<b>07장   언어의 사용(확장 예제)</b><br>
화물 해운 시스템 소개<br>
도메인 격리: 응용 기능 소개<br>
ENTITY와 VALUE OBJECT의 구분<br>
- 역할과 그 밖의 속성<br>
해운 도메인의 연관관계 설계<br>
AGGREGATE의 경계<br>
REPOSITORY의 선정<br>
시나리오 연습<br>
- 예제 애플리케이션 기능: 화물의 목적지 변경<br>
- 예제 애플리케이션 기능: 반복 업무<br>
객체 생성<br>
- Cargo에 대한 FACTORY와 생성자<br>
- Handling Event 추가<br>
리팩터링할 시간: Cargo AGGREGATE의 설계 대안<br>
해운 모델의 MODULE<br>
새로운 기능 도입: 할당량 검사<br>
- 두 시스템의 연계<br>
- 모델 강화: 업무 분야 나누기<br>
- 성능 최적화<br>
최종 검토<br>
<br>
<b>▣ 03부   더 심층적인 통찰력을 향한 리팩터링</b><br>
리팩터링 수준<br>
심층 모델<br>
심층 모델/유연한 설계<br>
발견 과정<br>
<br>
<b>08장   도약</b><br>
도약에 관한 일화<br>
- 괜찮은 모델이기는 하지만……<br>
- 도약<br>
- 더 심층적인 모델<br>
- 냉정한 결정<br>
- 결말<br>
기회<br>
기본에 집중하라<br>
후기 : 연이은 새로운 통찰력의 출현<br>
<br>
<b>09장   암시적인 개념을 명확하게</b><br>
개념 파헤치기<br>
- 언어에 귀 기울여라<br>
- 어색한 부분을 조사하라<br>
- 모순점에 대해 깊이 고민하라<br>
- 서적을 참고하라<br>
- 시도하고 또 시도하라<br>
다소 불명확한 개념의 모델링<br>
- 명시적인 제약조건<br>
- 도메인 객체로서의 프로세스<br>
SPECIFICATION (명세)<br>
- SPECIFICATION의 적용과 구현<br>
<br>
<b>10장   유연한 설계</b><br>
INTENTION-REVEALING INTERFACE (의도를 드러내는 인터페이스)<br>
SIDE -EFFECT-FREE FUNCTION (부수효과가 없는 함수)<br>
ASSERTION (단정)<br>
CONCEPTUAL CONTOUR (개념적 윤곽)<br>
STANDALONE CLASS (독립형 클래스)<br>
CLOSURE OF OPERATION (연산의 닫힘)<br>
선언적 설계<br>
- 도메인 특화 언어<br>
선언적인 형식의 설계<br>
- SPECIFICATION을 선언적인 형식으로 확장하기<br>
받음각<br>
- 서브 도메인으로 분할하라<br>
- 가능하다면 정립된 정형화를 활용하라<br>
<br>
<b>11장   분석 패턴의 적용<br>
<br>
12장   모델과 디자인 패턴의 연결</b><br>
STRATEGY (POLICY라고도 함)<br>
COMPOSITE (복합체)<br>
그렇다면 FLYWEIGHT는?<br>
<br>
<b>13장   더 심층적인 통찰력을 향한 리팩터링</b><br>
시작<br>
조사팀<br>
선행 기술<br>
개발자를 위한 설계<br>
타이밍<br>
위기를 기회로<br>
<br>
<b>▣ 04부   전략적 설계<br>
<br>
14장   모델의 무결성 유지</b><br>
BOUNDED CONTEXT (제한된 컨텍스트)<br>
- BOUNDED CONTEXT 안의 균열 인식<br>
CONTINUOUS INTEGRATION (지속적인 통합)<br>
CONTEXT MAP (컨텍스트 맵)<br>
- CONTEXT 경계에서의 테스트<br>
- CONTEXT MAP의 조직화와 문서화<br>
BOUNDED CONTEXT 간의 관계<br>
SHARED KERNEL (공유 커널)<br>
CUSTOMER/SUPPLIER DEVELOPMENTTEAM (고객/공급자 개발 팀)<br>
CONFORMIST (준수자)<br>
ANTICORRUPTION LAYER (오류 방지 계층)<br>
- ANTICORRUPTION LAYER의 인터페이스 설계<br>
- ANTICORRUPTION LAYER의 구현<br>
- 교훈적인 이야기<br>
SEPARATE WAYS (각자의 길)<br>
OPEN HOST SERVICE (공개 호스트 서비스)<br>
PUBLISHED LANGUAGE (공표된 언어)<br>
코끼리 통일하기<br>
모델의 컨텍스트 전략 선택<br>
- 팀 의사결정 또는 그 이상<br>
- 우리 자신을 컨텍스트에 배치하기<br>
- 경계의 변형<br>
- 변경할 수 없다는 사실을 인정하기: 외부 시스템의 묘사<br>
- 외부 시스템과의 관계<br>
- 설계 중인 시스템<br>
- 개별 모델의 특수한 요구사항 충족하기<br>
- 배치<br>
- 타협점<br>
- 프로젝트가 이미 진행 중일 때<br>
변형<br>
- CONTEXT 병합: SEPARATE WAYS → SHARED KERNEL<br>
- CONTEXT 병합: SHARED KERNEL → CONTINUOUS INTEGRATION<br>
- 레거시 시스템의 단계적 폐기<br>
- OPEN HOST SERVICE → PUBLISHED LANGUAGE<br>
<br>
<b>15장   디스틸레이션</b><br>
CORE DOMAIN (핵심 도메인)<br>
- CORE 선택<br>
- 누가 그 일을 할 것인가?<br>
디스틸레이션의 단계적 확대<br>
GENERIC SUBDOMAIN (일반 하위 도메인)<br>
- 일반화가 재사용 가능하다는 의미는 아니다<br>
- 프로젝트 위험 관리<br>
DOMAIN VISION STATEMENT (도메인 비전 선언문)<br>
HIGHLIGHTED CORE (강조된 핵심)<br>
- 디스틸레이션 문서<br>
- 표시된 CORE<br>
- 프로세스 도구로서의 디스틸레이션 문서<br>
COHESIVE MECHANISM (응집력 있는 메커니즘)<br>
- GENERIC SUBDOMAIN과 COHESIVE MECHANISM<br>
- MECHANISM이 CORE DOMAIN의 일부인 경우<br>
선언적 형식의 디스틸레이션<br>
SEGREGATED CORE (분리된 핵심)<br>
- SEGREGATED CORE를 만드는 데 드는 비용<br>
- 발전하는 팀의 의사결정<br>
ABSTRACT CORE (추상화된 핵심)<br>
심층 모델의 디스틸레이션<br>
리팩터링의 대상 선택<br>
<br>
<b>16장   대규모 구조</b><br>
EVOLVING ORDER (발전하는 질서)<br>
SYSTEM METAPHOR (시스템 은유)<br>
- "미숙한 은유"와 그것이 필요 없는 이유<br>
RESPONSIBILITY LAYER (책임 계층)<br>
- 적절한 계층의 선택<br>
KNOWLEDGE LEVEL (지식 수준)<br>
PLUGGABLE COMPONENT FRAMEWORK (착탈식 컴포넌트 프레임워크)<br>
구조는 얼마나 제약성을 지녀야 하는가?<br>
잘 맞아떨어지는 구조를 향한 리팩터링<br>
- 최소주의<br>
- 의사소통과 자기 훈련<br>
- 재구조화가 유연한 설계를 낳는다<br>
- 디스틸레이션은 부하를 줄인다<br>
<br>
<b>17장   전략의 종합</b><br>
대규모 구조와 BOUNDED CONTEXT와의 결합<br>
대규모 구조와 디스틸레이션과의 결합<br>
평가 먼저<br>
누가 전략을 세우는가?<br>
- 애플리케이션 개발에서 창발하는 구조<br>
- 고객(애플리케이션 개발팀) 중심의 아키텍처 팀<br>
전략적 설계 결정을 위한 6가지 필수 요소<br>
- 기술 프레임워크도 마찬가지다<br>
- 종합계획을 조심하라<br>
<br>
<b>▣ 결론</b><br>
<br>
맺음말<br>
앞을 내다보며<br>
<br>
부록   이 책에 포함된 패턴의 사용법<br>
패턴 이름<br>
<br>
용어 설명<br>
참고 문헌<br>
사진 협찬<br>
찾아보기<br>
<br>
</p>
