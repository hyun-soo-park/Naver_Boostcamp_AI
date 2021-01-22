## 4-1 Python Object-Oriented Programming

- 만들어 놓은 코드를 재사용 하고 싶을 때
- 클래스와 객체 <객체 지향 언어의 이해>

### 1. 객체 : 실생활에서 일종의 물건, 속성과 행동을 가짐
- OOP는 이러한 객체 개념을 프로그램으로 표현
- 속성은 변수, 행동은 함수로 표현됨
- OOP는 설계도에 해당하는 클래스와 실제 구현체인 인스턴스로 나눔

### 2. Objects in Python
- class 선언, object는 python3에서 자동 상속
- class의 함수 명은 띄어쓰기 부분에 대문자
- Attribute 추가는 __init__, self와 함께!
- __init__은 객체 초기화 예약 함수
- __는 특수한 예약 함수나 맨글링에 사용
- method 추가는 기존 함수와 같으나, 반드시 self를 추가해야만 class 함수로 인정됨

### 3. OOP 특징

- 상속 : 부모 클래스로부터 속성과 메소드를 물려받은 자식 클래스를 생성 하는 것
  - super().__init__ 등으로 사용
- 다형성 : 같은 이름 메소드의 내부 로직을 다르게 작성
  - 파이썬은 dynamic 특성으로 인해 파이썬에서는 같은 부모클래스의 상속에서 주로 발생함
- 가시성 : 객체의 정보를 볼 수 있는 레벨을 조절하는 것
  - self.__items = [] -> Private 변수
- 캡슐화 또는 정보은닉 : Class를 설계할 때, 클래스 간 간섭/정보 공유의 최소화.

### 4. decorater function
- 1급 객체
  - 변수나 데이터 구조에 할당이 가능한 객체
  - 파라메터로 전달이 가능 + 리턴 값으로 사용
  - 파이썬의 함수는 일급 함수

- Inner function
  - 함수 내에 또다른 함수가 존재

- closures : inner function을 return 값으로 반환

---

## 4-2 Module and Project

### 1. 모듈 : 어떤 대상의 부분 혹은 조각
- 프로그램에서는 작은 프로그램 조각들, 모듈들을 모아서 하나의 큰 프로그램을 개발함
- 프로그램을 모듈화 시키면 다른 프로그램이 사용하기 쉬움
- 모듈 == py를 의미
- import를 사용하여 불러옴
- namespace : 모듈을 호출할 때 범위 정하는 방법
- 모듈 안에는 함수와 클래스 등이 존재 가능
- 필요한 내용만 골라서 호출할 수 있음
- from과 import를 사용함
- alias 설정하기 – 모듈 명을 별칭으로 써서
```python
import fah_converter as fah
from fah_converter import convert_c_to_f
```

### 2. 패키지 : 모듈을 모아놓은 단위, 하나의 프로그램
- 기능들을 나누어 폴더로 생성
- 각 폴더별로 필요한 모듈을 구현함
- 폴더별로 __init__.py 구성하기
- 현재 폴더가 패키지임을 알리는 초기화 스크립트
- 하위 폴더와 py 파일 모듈을 구성함

---

피어세션 :

- <https://tibetsandfox.tistory.com/20> : 파이썬 private 참고
- decorator 이해
