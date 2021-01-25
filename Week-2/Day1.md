## 1-1 numpy

### 1. numpy 개요
- Numerical Python
- 파이썬의 고성능 과학 계산용 패키지
- Matrix와 Vector과 같은 Array 연산의 사실상 표준
- 일반 리스트에 비해 빠르고, 메모리 효율적
- 반복문 없이 데이터 배열에 대한 처리를 지원함


### 2. ndarray
- numpy는 np.array 함수를 활용하여 배열을 생성함 -> ndarray
- numpy는 하나의 데이터 type만 배열에 넣을 수 있음
- dynamic typing not supported
- c의 array를 활용하여 생성함


- shape : numpy array의 dimension 구성을 반환함
  - ndim : number of dimensions
  - size : data의 개수
- dtype : numpy array의 데이터 type을 반환함
  - ndarray의 single element가 가지는 data type
  - nbytes : ndarray object의 메모리 크기를 반환함


### 3. Handling shape
- reshape : Array의 shape의 크기를 변경함, element의 갯수는 동일
  - -1 : size를 기반으로 row 개수 선정
- flatten : 다차원 array를 1차원 array로 변환
  
  
### 4. indexing and slicing
- list와 달리 이차원 배열에서 [0,0] 표기법을 제공함
  
  
### 5. creation function
- arrange : array의 범위를 지정하여, 값의 list를 생성하는 명령어
- zeros : 0으로 가득 찬 ndarray 생성
- ones : 1로 가득 찬 ndarray 생성
- empty : shape만 주어지고 비어있는 ndarray 생성(memory initialization이 되지 않음)
- something_like : 기존 ndarray의 shape 크기 만큼 1, 0 또는 empty array를 반환
- identity : 단위 행렬(i 행렬)을 생성함
- eye : 대각선이 1인 행렬, k 값의 시작 index 변경이 가능
- diag : 대각 행렬의 값을 추출함
- random sampling : 데이터 분포에 따른 sampling으로 array를 생성]
- concatenate : numpy array를 합치는 함수


### 6. operation fucntion
- axis : 모든 operation function을 실행할 때 기준이 되는 dimension 축
- dot product : maxtrix의 기본 연산, dot 함수 사용 ```test_a.dot(test_b)```
- transopose : 행과 열을 변경
- broadcasting : shape이 다른 배열간 연산을 지원하는 기능


numpy는 c로 구현되어 있어 성능을 확보하는 대신, 파이썬의 최대 장점인 dynamic typing을 포기함


### 7. comparisons
- all : 데이터의 전부가 조건을 만족한다면 True
- any : 데이터 중 하나라도 조건을 만족한다면 True
- numpy는 배열의 크기가 동일할 때 element간 비교의 결과를 Boolean type으로 반환

### 8. boolean & fancy index
- fancy index : array를 index value로 사용하여 값 추출
```python
a = np.array([2,4,6,8],float)
b = np.array([0,0,1,3,2,1], int)
a[b]
a.take(b) # bracket index와 같은 효과
```

### 9. numpy data i/o
- loadtxt : 데이터를 불러와 읽는 기능
- savetxt : 데이터를 저장하는 기능

---

## 1-2 벡터
- 벡터 : 숫자를 원소로 가지는 리스트 또는 배열
  - 벡터는 공간에서 한 점을 나타낸다.
  - 벡터는 원점으로부터 상대적 위치를 표현한다.
  - 벡터에 숫자를 곱해주면 길이만 변한다.
  - 벡터끼리 같은 모양을 가지면 성분곱을 계산할 수 있다.
  

- 노름 : 원점에서부터의 거리를 말한다.
  - L1-노름 : 각 성분의 변화량의 절대값을 모두 더한다.
  - L2-노름 : 피타고라스 정리를 이용해 유클리드 거리를 계산한다.
```python
def l1_norm(x):
  x_norm = np.abs(x)
  x_norm = np.sum(x_norm)
  return x_norm

def l2_norm(x):
  x_norm = x*x
  x_norm = np.sum(x_norm)
  x_norm = np.sqrt(x_norm)
  return x_norm
```


- 두 벡터 사이의 거리 : 벡터의 뺄셈을 이용한다.
- 두 벡터 사이의 각도 : 제2코사인법칙에 의해 두 벡터 사이의 각도를 계산할 수 있다.
```python
def angle(x,y):
    v = np.inner(x,y) / (l2_norm(x) * l2_norm(y))
    theta = np.arccos(v)
    return theta
```
- 내적은 정사영된 벡터의 길이와 관련이 있다.

---

## 1-3 행렬
- 행렬 : 벡터를 원소로 가지는 2차원 배열
  - 행과 열이라는 인덱스를 가진다.
  - 여러 점들을 나타낸다
  - 행렬 곱셈은 ```X @ Y``` 로 표현한다.
  - ```np.inner```은 i번째 행 벡터와 j번째 행 벡터 사이의 내적을 성분으로 가지는 행렬을 계산한다.
  - 행렬곱을 통해 벡터를 다른 차원의 공간으로 보낼 수 있다.
  - 행렬곱을 통해 패턴을 추출할 수 있고 데이터를 압축할 수도 있다.


- 역행렬 : 어떤 행렬 A의 연산을 거꾸로 되돌리는 행렬을 역행렬이라고 한다.
  - ```np.linalg.inv(X)```
  - 만일 역행렬을 계산할 수 없다면 유사역행렬을 이용한다. ```np.linalg.pinv(X)```
  
