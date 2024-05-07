# 11장 코드 구조 따르기

- 코드는 현실 세계로부터 성문화된 구조: the code is a codified structure from the real world.
- 서로 다른 유형의 코드 구조가 어디서 오는지 논의
- 행위를 코드화하는 세 가지 방법, 각 방법 간에 행위를 이동시키는 방법
- 리팩터링이 도움이 될 때와 그렇지 않을 때
- 활용되지 않은 다양한 유형의 구조와, 이를 사용하는 방법

## 11.1 범위와 출처에 따른 구조 분류

- 매크로 아키텍처: 팀 간 구조
  - 외부 API, 각 팀이 어떤 데이터를 소유하는지 등 소프트웨어 플랫폼 정의
- 마이크로 아키텍처: 팀 내 구조
  - 사용하는 서비스, 데이터 구성, 코드 작성 방식
- 콘웨이 법칙: 외부 API의 모양은 조직 구조를 닮는 경향

## 11.2 행위를 코드화하는 세 가지 방법

### 11.2.1 제어 흐름에 행위 코드화하기

- 제어 연산자(루프), 메서드 호출, 열거된 코드의 줄
  - 열거된 반복적인 코드 줄 유형은 지양
  - 루프는 지역적으로만 동작 vs. 메서드 호출과 열거된 코드들은 non-local 구조를 표현할 수 있다.
  - 제어 연산자와 메서드 호출은 반복적인 줄로는 할 수 없는 무한 루프를 생성할 수 있다.

### 11.2.2 데이터 구조에 행위 코드화하기

- 재귀 데이터 구조
- 작은 변경은 더 쉽고 안전하게 할 수 있다. 더 많은 타입 안전성과 지역성을 얻기 때문
- 정보를 캐시하고 재사용할 수 있을 때 성능을 얻을 수도
- 클래스로 타입 코드 대체 및 전략 패턴의 도입

### 11.2.3 데이터에 행위 코드화하기

- 숫자를 클래스에 매핑하기

## 11.3 구조 노출을 위한 코드 추가

- 새로운 기능이나 하위 시스템을 구현할 때는 불확실성이 있으므로 빠르게 변경할 수 있도록 클래스보다는 열거형이나 루프 사용
- 코드가 성숙해지고 구조가 안정되면 코드도 리팩터링을 통해 구조에 맞게 안정, 견고하게 만든다.

## 11.4 예측 대신 관찰, 그리고 경험적 기술 사용

- 일반화된 코드가 사용될지에 대한 확신이 없다면(코드 변경이 없을 예정이라면) 더 멋진 코드를 작성하지 말라 
- 적당히 리팩토링하라

## 11.5 코드를 이해하지 않고도 안전성을 확보하는 방안

- 테스트를 통한 안전성 확보
- 숙달을 통한 안전성 확보
- 도구의 지원을 통한 안전성 확보
- 공식 인증을 통한 안전성 확보
- 내결함성을 통한 안전성 확보 (기능 토글, 실패 시 자동 롤백 등)

## 11.6 활용되지 않은 구조 이용

- 도메인으로부터 온 구조는 안전하게 활용할 수 있다. 그러나 소프트웨어의 수명이 우리의 프로세스보다 더 길기 때문에 새로운 프로세스를 도입할 때 이미 있는 기존 프로세스 코드를 풀어헤쳐야 한다.
- 그러므로 구조를 찾고, 코드에서 활용 가능한 구조를 찾아 사용해야 한다.

### 11.6.1 추출 및 캡슐화에 공백 활용

- 공백을 넣어 문장을 그룹화하고 메서드를 추출한다.
- 필드를 그룹화하여 데이터 요소의 관련성을 표현한다.

### 11.6.2 통합에 중복 코드 이용

- 문장을 메서드로 만들고, 메서드를 클래스로 만든다.

### 11.6.3 캡슐화로 공통 접사 활용

- 공통적인 명칭을 통해 그룹화된 것을 데이터 캡슐화한다.

### 11.6.4 동적 실행으로 런타임 유형 활용

- 뭔말인지 모르겠다... 부탁해요 현철님




# 12장 최적화 및 일반화 회피

- 최적화: 코드 처리량을 늘리거나 처리 시간을 줄이는 성능 최적화
- 일반화: 코드가 더 일반적인 매개변수를 통해 더 많은 기능을 포함하도록

부탁해요 민경님


# 13장 나쁜 코드를 식별 가능하게 만들기

- 안티리팩터링: 나쁜 코드를 딱 봐도 안좋아 보이게 만들어서 품질의 수준을 명확히 표시하는 방법 

## 13.1 나쁜 코드에 대처하는 자세

- 나쁜 코드를 남겨두면 다시 찾기 쉽고, 통제가 지속가능하지 않다는 신호를 준다

## 13.2 깨끗한 코드와 레거시 코드로 분리

- 잘 만들 수 없다면 눈에 띄게 만들어야 한다.
- 전체 파일이 깨끗할 때 나쁜 코드가 더 쉽게 식별되며, 손쉽게 리팩터링할수있다.

## 13.3 나쁜 코드를 찾는 방법

- 이 책의 규칙: 단순하고 구체적인 코드
- 코드스멜: 완전하고 추상적인 코드
- 순환 복잡도: 알고리즘(객관적) - 코드를 통과하는 경로의 수
- 인지 복잡도: 알고리즘(주관적) - 메서드를 읽는 동안 얼마나 많은 정보를 유지해야 하는지

## 13.4 코드를 안전하게 나쁜 코드로 보이기 위한 규칙

- 올바른 정보를 절대 훼손하지 말 것
- 향후 리팩터링을 어렵게 만들지 말 것: 공백 줄이나 가지고 있는 모든 정보를 표시
- 결과를 한 눈에 알 수 있을 것: 코드가 신호로 인식되고, 깨끗한 코드와 구분할 수 있는 눈에 띄는 차이를 보장

## 13.5 나쁜 코드를 나쁘게 보이기 위한 방법

- 열거형 사용
- 정수형 및 문자열을 타입 코드로 사용
- 코드에 매직 넘버 넣기
- 코드에 주석 넣기
- 코드에 공백 넣기
- 이름을 기준으로 항목을 그룹화하기
- 이름에 컨텍스트 추가하기 (공통접사 추가 등)
- 긴 메서드 만들기
- 메서드에 많은 매개변수 넘기기: 데이터 객체나 구조체를 긴 매개변수 목록으로 만들어 유형과 이름을 모두 유지
- getter와 setter 사용하기


# 14장 마무리

## 14.1 이 책의 여정을 돌아보며

- 리팩터링이 무엇이고 왜 필수적인지, 언제 우선시해야 하는지 
- 리팩터링의 목표: 불변속성을 지역화해서 취약성을 줄이고 결합을 줄여 유연성을 높인다.
- 1부: 긴 함수를 분해하고, 타입 코드를 클래스로 대체, 함수를 클래스의 메서드화, if/함수/클래스 통합
- 2부: 리팩터링과 코드 품질에 영향을 미치는 사회-기술적 주제 

## 14.2 기본 철학 탐구

- 항상 더 작은 단계 찾기 (큰 문제를 작은 조각으로 분해): 최소한의 개선만 하는 여러 중간 단계를 거친다.
- 기본 구조 찾기
- 협업을 위한 규칙 사용: 규칙들이 리팩터링할 때 안정감과 자신감을 부여하게 할 것
- 개인보다 팀을 우선시하기
- 완전성보다 단순선 우선하기: 모호하고 일반적인 규칙보다 적용 용이성을 추구?
- 객체 또는 고차함수 사용하기

## 14.3 이후 여정

- 마이크로 아키텍처: 팀 내 아키텍처
- 매크로 아키텍처: 팀 간 아키텔처
- 소프트웨어 품질: 테스트 주도 개발, 타입 이론 학습