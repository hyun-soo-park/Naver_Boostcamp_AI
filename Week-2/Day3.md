## 3-1 pandas

### 1. Pandas 개요
- pandas : 구조화된 데이터의 처리를 지원하는 Python 라이브러리
- Python 계의 엑셀
- 고성능 array 계산 라이브러리인 numpy와 통합하여, 강력한 "스프레드시트" 처리 기능을 제공
- 인덱싱, 연산용 함수, 전처리 함수 등을 제공함
- 데이터 처리 및 통계 분석을 위해 사용


### 2. Pandas의 구성
- Series : DataFrame중 하나의 Column에 해당하는 데이터의 모음 Object
  - Column vector을 표현하는 object
- DataFrame : Data Table 전체를 포함하는 Object
  - Series를 모아서 만든 Data Table = 기본 2차원
  - loc : index location ```s.loc[:3] #index의 이름이 3인 데이터까지 출력 하라```
  - iloc : index position ```s.iloc[:3] #index number 3전까지 출력 하라```
  - values : 값 출력
  - column 이름 없이 사용하는 index number은 row 기준 표시 ```df[:3]
- pandas의 series type의 데이터에도 map 함수 사용 가능
- function 대신 dict, sequence형 자료 등으로 대체 가능
- describe : Numeric type 데이터의 요약 정보를 보여줌
- unique : series data의 유일한 값을 list로 반환함
- corr : 상관 계수를 구하는 함수
- cov : 공분산을 구하는 함수

---

## 3-2 딥러닝 학습방법 이해하기
- 신경망 : 비선형 모델
- 소므트맥스 연산 
  - 소프트맥스 함수는 모델의 출력을 확률로 해석할 수 있게 변환해주는 연산이다.
  - 분류 문제를 풀 때 선형 모델과 소프트맥스 함수를 결합하여 예측한다.
- 신경망은 선형모델과 활성함수를 합성한 함수이다.
- 활성함수를 쓰지 않으면 딥러닝은 선형 모형과 차이가 없다.
- 딥러닝에서는 ReLU 함수를 많이 쓰고 있다.
- 다중 퍼셉트론(MLP)는 신경망이 여러층 합성된 함수이다.
- 신경망 층이 깊을수록 목적함수를 근사하는데 필요한 뉴런의 숫자가 훨씬 빨리 줄어들어 좀 더 효율적으로 학습이 가능하다.
- 딥러닝은 역전파 알고리즘을 이용하여 각 층에 사용된 패러미터를 학습한다.
- 역전파 알고리즘은 합성함수의 미분법인 연쇄법칙 기반 자동미분을 사용한다.
