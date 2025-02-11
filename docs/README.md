# 🏁 자동차 경주 미션

## 📌 미션 설명
우아한테크코스 웹 백엔드 6기 미션으로 `자동차 경주 게임`을 구현하는 프로젝트이다.

<br/>

## 📂 디렉토리 구조
```
.
├── main
│   └── java
│       └── racingcar
│           ├── Application.java
│           ├── config
│           ├── controller
│           ├── domain
│           ├── dto
│           ├── util
│           └── view
└── test
    └── java
        ├── racingcar
        │   ├── ApplicationTest.java
        │   ├── application
        │   ├── config
        │   └── domain
        └── study
            └── StringTest.java
```

<br/>

## ✨기능 목록

### Domain 기능
**Car**
- [X] 1~5자로 이루어진 이름으로 자동차를 생성하는 기능
- [X] 숫자가 4 이상일 경우, 한 칸 이동하는 기능

**Cars**
- [X] 여러 대의 자동차를 생성하는 기능
  - 유효성 검증:
    - 자동차가 한 대일 경우 예외 처리
    - 자동차 이름이 중복될 경우 예외 처리
- [X] 자동차들을 이동하게 하는 기능

**Game**
- [X] 자동차와 시도 횟수로 게임을 생성하는 기능
  - 유효성 검증:
    - 시도 횟수가 0 이하일 경우 예외 처리
- [X] 시도 횟수만큼 자동차를 이동시키는 기능
- [X] 회차별 경주 결과를 저장하는 기능
- [X] 우승자를 판별하는 기능 

**RoundResult**
- [X] 회차별 경주 결과를 생성하는 기능

### 입력 기능
- [X] 자동차 이름 입력 기능
  - 유효성 검증:
    - 이름을 쉼표로 구분하지 않았을 경우 예외 처리
- [X] 자동차 이동 횟수 입력 기능
  - 유효성 검증:
    - int 범위를 벗어났을 경우 예외 처리

### 출력 기능
- [X] 각 차수별 실행 결과 출력 기능
- [X] 우승자 안내 문구 출력 기능

### 유틸 기능
- [X] 0~9 사이의 랜덤 숫자를 생성하는 기능

<br/>

## ✅ 테스트 케이스

### 통합 테스트

**입력 기능**

| 테스트 케이스                                        | 통과 여부 |
|:-----------------------------------------------|:------|
| 정상 상황일 때 예외가 발생하지 않는다.                         | ✔️️   |
| 입력값이 공백일 때 예외가 발생한다.                           | ✔️️   |
| 입력값이 쉼표 기준으로 split 되었을 때 한 개 라도 공백이면 예외가 발생한다. | ✔️    |
| 입력값이 쉼표 기준으로 구분되지 않았을 때 예외가 발생한다.              | ✔️️   |

### 단위 테스트

**Car**

| 테스트 케이스                    | 통과 여부 |
|:---------------------------|:------|
| 정상 상황일 때 자동차가 생성된다.        | ✔️    |
| 자동차 이름이 5자 이상일 때 예외가 발생한다. | ✔️    |
| 숫자가 4 이상일 때 자동차가 전진한다.     | ✔️️   |
| 숫자가 4 미만일 때 자동차가 정지한다.     | ✔️️   |

**Cars**

| 테스트 케이스                     | 통과 여부 |
|:----------------------------|:------|
| 정상 상황일 때 Cars가 생성된다.        | ✔️    |
| 중복되는 자동차 이름이 있을 때 예외가 발생한다. | ✔️    |
| 자동차가 한 대일 때 예외가 발생한다.       | ✔️    |
| 숫자가 주어지면 자동차를 이동하게 한다.      | ️     |

**Game**

| 테스트 케이스                   | 통과 여부 |
|:--------------------------|:------|
| 시도 횟수가 1미만일 때 예외가 발생한다.   | ✔️    |
| 시도 횟수만큼 결과를 저장한다.         | ✔️    |
| 우승자가 1명일 때 정확한 결과를 리턴한다.  | ✔️    |
| 우승자가 여러명일 때 정확한 결과를 리턴한다. | ✔️    |
