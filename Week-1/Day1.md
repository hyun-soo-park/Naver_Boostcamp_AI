
## 1-1 기본적인 컴퓨터 시스템_개요

### 1. 컴퓨터 OS

- 운영체제 : 우리의 프로그램이 동작할 수 있는 구동 환경 (어플리케이션 -> 운영체제 -> CPU+메모리)

### 2. 파일 시스템 : OS에서 파일을 저장하는 트리구조 저장 체계

- 디렉토리 : 폴더 또는 디렉토리로 불림, 파일과 다른 디렉토리를 포함할 수 있음
- 절대 경로 : 루트 디렉토리부터 파일 위치까지의 경로
  Ex) C:\user\docs
- 상대 경로 : 현재 있는 디렉토리부터 타깃 파일까지의 경로 Ex) ..//..//hello.txt

### 3. 터미널 : 마우스가 아닌 키보드로 명령을 입력 프로그램 실행

- GUI : Graphical User Interface
- CLI : Command Line Interface


### 4. Shell 명령어
```
  - Cd : 현재 디렉터리 이름을 보여주거나 바꾼다
  - Clear : CMD 화면에 표시된 것을 모두 지운다.
  - Cp : 하나 이상의 파일을 다른 위치로 복사한다
  - Rm : 하나 이상의 파일을 지운다
  - Ls : 디렉터리에 있는 파일과 하위 디렉터리 목록을 보여준다.
  - .. : 현재 디렉토리에서 한칸 앞에
  - . : 현재 디렉토리
  ```
  
---

## 1-2 파이썬 개요

### 1. 특징

- 독립적, 인터프리터


- 컴파일러 : 소스코드를 기계어로 먼저 번역, 실행 속도가 빠름
- 한번의 많은 기억장소 필요
- ex) C, 자바, C++, C#


- 인터프리터 : 별도의 번역 과정 없이 소스코드를 실행 시점에 해석하여 컴퓨터가 처리할 수 있도록 함
- 간단히 작성, 메모리가 적게 필요
- 실행 속도가 느림 ex) 파이썬, 스칼라

```
- 객체 지향적 언어: 실행 순서가 아닌 단위 중심으로 프로그램을 작성

- 동적 타이핑 언어 : 프로그램이 실행하는 시점에 프로그램이 사용해야 할 데이터에 대한 타입을 결정함
```

### 2. 사용하는 이유

- 이해하기 쉬운 문법, 다양한 라이브러리

---

## 1-3 파이썬 코딩 환경

### 1. 선호하는 운영체제를 선정

### 2. 코드 편집기

- 파이썬 코드도 일종의 문서이므로 한글, 워드처럼 코드를 입력할 문서 편집기가 필요함
- Text 타입의 문서를 저장하는 모든 편집기 사용 가능
- 설치된 어플리케이션, 웹 기반 인터랙티브 편집기로 나누어짐

### 3. Jupyter 개요

- IPython 커널을 기반으로 한 대화형 파이썬 셸
- 일반적인 터미널 셸 + 웹 기반 데이터 분석 Notebook 제공
- 미디어, 텍스트, 코드, 수식 등을 하나의 문서로 표현 가능
- 사실상 데이터 분석 Interactive Shell의 표준

### 4. Colab 개요

- 구글의 개발 클라우드 기반의 jupyter notebook
- 구글 드라이브 + GCP + jupyter 등이 합쳐져서 사용자가 손쉽게 접근
- VSCode와 연동 가능

---

## 피어세션 : 서로에 대해 소개하고 규칙과 플랜을 정하는 활동을 가졌다.

```
피어세션 규칙 :
- 모더레이터는 주마다 돌아가면서 한다.
- 2시까지 늦지 않게 참석한다.
- 서로에 대해 비난하지 않기
- 소수의 의견도 존중하기
- 부끄러워 하지 않고 모르는 것이 있으면 모두 물어보기
- 쉬운 부분을 질문했다고 놀리지 않기
```

```
피어세션 플랜 :
- 강의에서 모르는 부분이 있다면 정리해서 피어세션 시간에 서로 토의한다.
- 과제 제출에 대한 의견 공유한다.
- 월요일마다 퀴즈에 대해 리뷰한다.
```
