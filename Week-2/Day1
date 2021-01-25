## 1-1 numpy

1. numpy 개요
- Numerical Python
- 파이썬의 고성능 과학 계산용 패키지
- Matrix와 Vector과 같은 Array 연산의 사실상 표준
- 일반 리스트에 비해 빠르고, 메모리 효율적
- 반복문 없이 데이터 배열에 대한 처리를 지원함


2. ndarray
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


3. Handling shape
- reshape : Array의 shape의 크기를 변경함, element의 갯수는 동일
  - -1 : size를 기반으로 row 개수 선정
- flatten : 다차원 array를 1차원 array로 변환
  
  
4. indexing and slicing
- list와 달리 이차원 배열에서 [0,0] 표기법을 제공함
  
  
5. creation function
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


6. operation fucntion
- axis : 모든 operation function을 실행할 때 기준이 되는 dimension 축
- dot product : maxtrix의 기본 연산, dot 함수 사용 ```test_a.dot(test_b)```
- transopose : 행과 열을 변경
- broadcasting : shape이 다른 배열간 연산을 지원하는 기능


numpy는 c로 구현되어 있어 성능을 확보하는 대신, 파이썬의 최대 장점인 dynamic typing을 포기함


7. comparisons
- all : 데이터의 전부가 조건을 만족한다면 True
- any : 데이터 중 하나라도 조건을 만족한다면 True
- numpy는 배열의 크기가 동일할 때 element간 비교의 결과를 Boolean type으로 반환

