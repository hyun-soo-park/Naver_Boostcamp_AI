## 3-1 파이썬 자료구조

### 1. 스택
- 나중에 넣은 데이터를 먼저 반환하도록 설계된 메모리 구조 Data의 입력을 Push, 출력을 Pop이라고 함
- 리스트를 사용하여 구현이 가능하다.
- Pop : return이 존재 한다

### 2. 큐
- 먼저 넣은 데이터를 먼저 반환하도록 설계된 메모리 구조
- 리스트를 사용하여 구현이 가능
- Put은 append, get은 pop(0)을 사용

### 3. 튜플
- 값의 변경이 불가능한 리스트
- 선언 시 ()로 선언한다.
- 사용하는 이유 : 프로그램을 작동하는 동안 변경되지 않은 데이터의 저장
- 함수의 반환 값 등 사용자의 실수에 의한 에러를 사전에 방지
- 튜플로 인정을 받으려면 꼭 ,를 사용해야한다.

### 4. 집합(set)
- 값을 순서없이 저장, 중복 불허 하는 자료형
- Set 객체 선언을 이용하여 객체 생성
- add, remove를 사용하여 값을 추가, 제거
- discard 삭제, clear 모든 원소 삭제, update([1,2,3]) 추가
- 합집합 union, | 교집합 intersection & 차집합 difference –

### 5. 사전(딕셔너리)
- 데이터를 저장할 때는 구분을 지을 수 있는 값을 함께 저장
- 구분을 위한 고유 값을 key이라고 함
- Key 값을 활용하여 데이터 값(Value)를 관리함
- {key1:value1, key2:value2}의 형태
- Code = {} 혹은 code= dict() 로 생성
- Code.items() : 아이템 출력 
- code.keys() : 키 값만 출력 
- ```code[‘german’] = 49``` : dict 추가 
- code.values() : value 값만 출력

### 6. Collections 모듈

- deque:
  - Stack과 queue를 지원하는 모듈
  - Linked list의 특성을 지원함
  - 기존 list 형태의 함수를 모두 지원함
  - Appendleft, popleft,extendleft 등 가능

- OrderedDict
  - Dict와 달리, 데이터를 입력한 순서대로 dict를 반환함
  - 3.6 이후로는 dict도 순서대로 지원
  
- defaultdict
  -Dict type의 값에 기본값을 지정, 신규 값 생성시 사용하는 방법
```python
from collections import defaultdict
d = defaultdict(object)
d = defaultDict(lambda: 0)
print(d[“first”])
```

- Counter
  - Sequence type의 data element들의 갯수를 dict 형태로 반환
```python
[“B”,”S”,”S”,”C”]
c = Counter(ball_or_strike_list)
c = {“B” : 1, “S” : 2, “C” :1}
```

- named tuple
  - Tuple 형태로 Data 구조체를 저장하는 방법
  - 저장되는 data의 variable을 사전에 지정해서 저장함
```python
from collections import namedtuple

Point = namedtuple(‘Point’, [‘x’,’y’])

p = Point(11, y=22)

print(p[0] + p[1])
print(p.x,p.y)
```

---

## 3-2 Pythonic Code

- split 함수
  - 데이터를 split()을 기준으로 나눈다.

- list comprehension
  - 기존 리스트를 사용하여 간단히 다른 리스트를 만드는 기법
  - 포괄적인 리스트
  - 일반적으로 for+append 보다 속도가 빠름
```python
result = [I for I in range(10)]
result = [I for I in range(10) if i%2==0]

word_1 = “Hello”
word_2 = “World”

result = [i+j for I in word_1 for j in word_2 if not (i==j)]
[[w.upper(), w.lower(), len(w)] for w in words]
```

- enumerate, zip

  - enumerate : list의 element를 추출할 때 사용
```python
for I, v in enumerate(“ABC”):

print ({0} \t {1}.format(I,v))
```

- zip : 두개의 list의 값을 병렬적으로 추출함
```python
for a,b in zip(alist, blist):

print(a,b)
```

- lambda, map, reduce
  -lambda : 함수 이름 없이 함수처럼 쓸 수 있는 익명 함수
```python
f = lambda x,y: x+y

print(f(1,4))
```

- map : 실행시점의 값을 생성, 메모리 효율적

- reduce : map function과 달리 list에 똑같은 함수를 적용해서 통합
```python
from functools import reduce

reduce(lambda x, y: x+y, [1,2,3,4,5]) #15
```

- iterable objects
  -내부적 구현으로 __iter__와 __next__가 사용됨
```python
iter_obj = iter(cities)

print(next(iter_obj))
```
- generator
  - iterable object를 특수한 형태로 사용해주는 함수
  - element가 사용되는 시점에 값을 메모리에 반환
  - yield를 사용해 한번에 하나의 element만 반환함

- generator comprehension

  - list comprehension과 유사한 형태로 generator 형태의 list 생성
  - generator expression 이라는 이름으로도 부름
  - [] 대신 ()를 사용하여 표현
  - generator은 메모리 용량을 상당히 작게 차지함
  - list 타입의 데이터를 반환해주는 함수는 generator로 만들어라: 읽기 쉬운 장점, 중간 과정에서 loop이 중단될 수 있을 때, 큰 데이터를 처리할 때, 파일 데이터를 처리할 때
```python
gen_ex = (n*n for n in range(500))

print(type(g)) -> <class ‘generator’>
```
  
- function passing arguments
  - 함수에 입력되는 arguments의 다양한 형태
```
- keyword arguments
- default arguments
- variable-length asterisk
```
- 함수의 parameter가 정해지지 않았다?
  - 가변인자 using asterisk(*) 기호를 사용하여 함수의 parameter를 표시함
  - 개수가 정해지지 않은 변수를 함수의 parameter로 사용하는 법
  - keyword arguments와 함께, argument 추가가 가능
  - 가변인자는 일반적으로 *args를 변수명으로 사용
  - 기존 parameter 뒤에 나오는 값을 튜플로 저장
```python
def asterisk_test(a,b,*args):

return a+b+sum(args)
```
- 키워드 가변인자
  - parameter 이름을 지정하지 않고 입력하는 방법
  - asterisk(*) 두개를 사용하여 함수의 parameter를 표시함
  - 입력된 값은 dict type으로 사용할 수 있음
  - 가변인자는 오직 한 개만 기존 가변인자 다음에 사용
```
def kwargs_test_1(**kwargs):

print(kwargs)
```
- asterisk : 흔히 알고 있는 *를 의미함
  - 앞에 *이 들어가면 unpacking이 된다.
  - 앞에 **이 들어가면 dict 
