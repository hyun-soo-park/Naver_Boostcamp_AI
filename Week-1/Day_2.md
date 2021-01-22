## 2-1 변수와 리스트

### 1. 변수 : 데이터를 저장하기 위한 메모리 공간의 프로그래밍상 이름
- ex) professor = ‘sungcheol’의 의미는 professor이라는 변수에 sungcheol이라는 값을 넣으라는 의미
- 변수는 메모리 주소를 가지고 있고, 변수에 들어가는 값은 메모리 주소에 할당됨
- 변수 : 프로그램에서 사용하기 위한 특정한 값을 저장하는 공간
- 선언이 되는 순간 메모리 특정 영역에 물리적인 공간이 할당됨
- 변수에는 값이 할당되고 해당 값은 메모리에 저장됨
- A = 8의 의미는 A라는 이름을 가진 메모리 주소에 8을 저장하라는 의미

```
1) 기본 자료형
- 수치자료형 – 정수형(integer), 실수형(float) / 문자형(string) / 논리 자료형(Boolean)
- Integer : 32비트, float : 64비트의 메모리를 차지함
- Dynamic Typing : 코드 실행 시점에 데이터의 Type를 결정하는 방법

2) 연산자와 피 연산자
- 연산의 순서는 수학에서 연산 순서와 같음
- **는 제곱승 연산자
- %는 나머지를 구하는 연산자

3) 데이터 형변환
- Float()와 int() 함수를 사용하여 데이터의 형 변환 가능
- 실수형에서 정수형으로 변환시 내림
- Type() 함수는 변수의 데이터 형을 확인하는 함수
```

```
컴퓨터는 왜 이진수를 쓰나?
컴퓨터는 실리콘이라는 재료로 만든 반도체로 구성되는데, 전류가 흐를때 1, 흐르지 않을 때 0으로만 숫자를 표현할 수 있음 이진수 한자리를 bit라 칭하고 8개의 bit는 1byte
```

### 2. List 또는 시퀀스 자료형 : 여러 데이터들의 집합, int, float같은 다양한 데이터 타입 포함

```
List의 특징
- 인덱싱
  - List에 있는 값들은 주소(offset)를 가짐 -> 주소를 사용해 할당된 값을 호출

- 슬라이싱
  - List에 있는 값들을 잘라서 쓰는 것이 슬라이싱. List의 주소 값을 기반으로 부분 값을 반환
  - Ex) list[0:10:2] : 2칸씩 띄워서 슬라이싱
  - List[::2] : 2칸씩 띄워서 슬라이싱

- 패킹
  - 한 변수에 여러개의 데이터를 넣는 것

- 언패킹
  - 한 변수의 데이터를 각각의 변수로 변환
  - 2차원에서는 a = b[:] 방식과 같이 copy할 수 없다. 따라서 2차원에서는 import copy 이후 copy.deepcopy()를 사용 해야 한다.
```
---

## 2-2 함수와 콘솔 인/아웃

### 1. 함수 : 어떤 일을 수행하는 코드의 덩어리

- ex) Def calculate_rectangle_area(x,y) : Return x*y
- 반복적인 수행을 1회만 작성 후 호출
- 코드를 논리적인 단위로 분리

### 2. 캡슐화 : 인터페이스만 알면 타인의 코드 사용

```python
Def 함수이름(parameter #1,…,):
수행문 #1(statements)
수행문 #2(statements)
Return <반환값>
```

### 3. Print formatting

- %string
```python
Print(“%s %s” %(‘one’,’two’))
Print(“{} {}”.format(‘one’,’two’)) # 값의 형식을 넣어주지 않아도 자동으로 지정
```

- Format 함수

```python
Print(“I eat %d apples and %s apples”%(3,’five’))
```

  - %c : 문자 1개, %f : 부동 소수
  - %8.2f : 8자리를 비우고, 소수점 2자리 까지 출력하라
```python
Print(“my name is {1} and {0} years old”.format(age,name))
```

  - Padding : 여유 공간을 지정해서 출력하라

- Fstring
  - Python 3.6 이후 formatting 기법, 최근 가장 많이 쓰임

```python
print(f”Hello,{name}. You are {age}.”)
print(f”{name:20}’) // 왼쪽 정렬 후 20칸 padding
print(f”{name:20}’)
print(f”{number :.2f}”) // 소수 둘째자리까지 출력
```

---

## 2-3 조건문과 반복문

- If 다음에 조건을 표기하여 참 또는 거짓을 판단함
- 참/거짓의 구분을 위해서는 비교 연산자를 활용
- 숫자형의 경우에는 수학에서의 참/거짓과 동일, 컴퓨터는 존재하면 참 없으면 거짓이라고 판단함
- List에서 all(list) : and 연산, any(list) : or 연산
- 삼항 연산자 : is_even = True if value %2==0 else False
- 반복문 변수명 : 임시적인 반복 변수는 대부분 I,j,k로 정함
- 0부터 시작하는 반복문 : 반복문은 대부분 0부터 반복을 시작
- 무한 loop : 반복 명령이 끝나지 않는 프로그램 오류


- 디버깅 : 코드의 오류를 발견하여 수정하는 과정, 문법적 에러를 찾기 위한 에러 메시지 분석, 논리적 에러를 찾기 위한 테스트도 중요
- 논리적 에러 : 중간중간 에러를 찾기 위해 loop를 돌려본다.
```python
If __name__ == “__main__”:
Main()
```

---

## 2-4 String and advanced function concept

- 시퀀스 자료형으로 문자형 data를 메모리에 저장
- 영문자 한 글자는 1byte의 메모리 공간을 사용
- String은 1byte 크기로 한 글자씩 메모리 공간이 할당됨
- 컴퓨터는 문자를 직접적으로 인식x, 모든 데이터는 2진수로 인식
- Int : 4바이트, long : 무제한, float : 8바이트
- String은 list와 같은 방식으로 인덱싱, 슬라이싱
```
It’s ok -> print(‘it\’s ok’)
```
- 두줄 이상의 표현 : \n을 사용하거나
```
a= ‘’’ it’s ok

I’m happy

See you.’’’
```
과 같이 따옴표 세번 사용이렇게 표현 가능

```python
F = open(“yesterday.txt”,’r’)

While True:
line = f.readline()

if not line:
break
Yesterday_lyric = yesterday_lyric + line.strip() + ‘\n’

f.close()
n_of_yesterday = yesterday.lyric.upper().count(“YESTERDAY”)
```

### 1. 함수 호출 방식 개요
- 값에 의한 호출(Call by Value)
  - 함수에 인자를 넘길 때 값만 넘김
  - 함수 내에 인자 값 변경 시, 호출자에게 영향을 주지 않음

- 참조에 의한 호출(Call by Reference)
  - 함수에 인자를 넘길 때 메모리 주소를 넘김
  - 함수 내에 인자 값 변경 시, 호출자의 값도 변경됨
  
- 객체 참조에 의한 호출(Call by Object Reference)
  - 파이썬은 객체의 주소가 함수로 전달되는 방식
  - 전달된 객체를 참조하여 변경 시 호출자에게 영향을 주나, 새로운 객체를 만들 경우 호출자에게 영향을 주지 않음

### 2. 변수의 범위(Scoping Rule)
- 지역 변수 : 함수 내에서만 사용
- 전역 변수 : 프로그램 전체에서 사용
- 함수 내에서 전역변수 사용시 global 선언

### 3. Function type hints
처음 함수를 사용하는 사용자가 인터페이스를 알기 어렵다는 단점이 있으므로 사용
```python
Def do_function(var_name: var_type) -> return type:
Pass
```
```python
def type_hint_example(name: str) -> str:
Return f”Hello, {name}”
```

- Type hints의 장점
  - 사용자에게 인터페이스를 명확히 알려줄 수 있다.
  - 함수의 문서화시 파라미터에 대한 정보를 명확히 알 수 있다.
  - Mypy 또는 IDE, linter 등을 통해 코드의 발생 가능한 오류를 사전에 확인
  - 시스템 전체적인 안정성을 확보할 수 있다.


- Docstring: 파이썬 함수에 대한 상세 스펙을 사전에 작성

- 함수 작성 가이드 라인
  - 함수는 가능하면 짧게 작성할 것
  - 함수 이름에 함수의 역할, 의도가 명확히 드러낼 것
  - 하나의 함수에는 유사한 역할을 하는 코드만 포함
  - 인자로 받은 값 자체를 바꾸지는 말 것(임시 변수 선언)
  - 공통적으로 사용되는 코드는 함수로 변환
  - 복잡한 수식 -> 식별 가능한 이름의 함수로 변환
  - 복잡한 조건 -> 식별 가능한 이름의 함수로 변환

--- 

## 피어세션 : 강의에서 몰랐던 부분에 대해 토의하고 과제의 풀이에 대해 같이 논의 하였다.

- 내일 토의할 일
  - call-by-reference에 대해 확실하게 이해하기
  - 반복문에 else 들어가는 부분
  - 정규 식
