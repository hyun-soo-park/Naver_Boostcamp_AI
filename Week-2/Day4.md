## 4-1 pandas
### 1. 그룹 함수
- Group by : SQL groupby 명령과 같음
- unstack : Group으로 묶여진 데이터를 matrix 형태로 전환해줌
- Group by에 의해 splite된 상태를 추출 가능함
- Aggregation : 요약된 통계정보를 추출해 줌
- Transformation : 해당 정보를 변환해줌
  - Aggreation과 달리 Key값 별로 요약된 정보가 아님
  - 개별 데이터의 변환을 지원함
- Filtration : 툭정 정보를 제거하여 보여주는 필터링 기능


- Data : 시간과 데이터 종류가 정리된 통화량 데이터
- Merge : 두 개의 데이터를 하나로 합침
- Concat : 같은 형태의 데이터를 붙이는 연산 작업

---

## 4-2 확률론 맛보기
### 1. 딥러닝에서 확률론이 필요한 이유?
  - 딥러닝은 확률론 기반의 기계학습 이론에 바탕을 두고 있음
  - 기계 학습에서 사용되는 손실함수들의 작동 원리는 데이터 공간을 통계적으로 해석해서 유도하게 된다.
  - 회귀 분석에서 손실함수로 사용되는 L2-노름은 예측오차의 분산을 가장 최소화 하는 방향으로 학습하도록 유도 한다.
  - 분류 문제에서 사용되는 교차엔트로피는 모델 예측의 불확실성을 최소화하는 방향으로 학습하도록 유도 한다.
  - 분산 및 불확실성을 최소화 하기 위해서는 측정하는 방법을 알아야 한다.

### 2. 확률 변수
- 이산확률변수
  - 확률변수가 가질 수 있는 경우의 수를 모두 고려하여 확률을 더해서 모델링 한다.
- 연속확률변수
  - 데이터 공간에 정의된 확률변수의 밀도 위에서의 적분을 통해 모델링 한다.
- 조건부확률과 기계학습
  - 조건부 확률은 입력변수 x에 대해 정답이 y일 확률을 의미한다.
  - 로지스틱 회귀에서 사용했던 선형모델과 소프트맥스 함수의 결합은 데이터에서 추출된 패턴을 기반으로 확률을 해석하는데 사용된다.
- 기대값 : 확률분포가 주어지면 데이터를 분석하는 데 사용 가능한 여러 종류의 통계적 범함수를 계산할 수 있다.
- 기대값을 이용해 분산, 첨도, 공분산 등 여러 통계랑을 계산할 수 있다.

### 3. 몬테카를로 샘플링
- 기계학습에서 확률분포를 모를 때 데이터를 이용하여 기대값을 계산하려면 몬테카를로 샘플링 방법을 사용해야 한다.
```python
# 몬테카를로 예제 : e^-x^2의 [-1, 1] 적분 값을 구하기
import numpy as np

def mc_int(fun, low, high, sample_size = 100, repeat = 10):
    int_len = np.abs(high-low)
    stat = []
    for _ in range(repeat):
        x = np.random.uniform(low = low, high= high, size = sample_size)
        fun_x = fun(x)
        int_val = int_len * np.mean(fun_x)
        stat.append(int_val)
    return np.mean(stat), np.std(stat)

def f_x(x):
    return np.exp(-x**2)

print(mc_int(f_x, low = -1, high = 1, sample_size = 10000, repeat = 100))
```
