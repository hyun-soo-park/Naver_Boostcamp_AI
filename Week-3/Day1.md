## 1. 베이즈 통계학

### 1. 조건부 확률
- 조건부확률 P(A|B)는 사건 B가 일어난 상황에서 사건 A가 발생할 확률을 의미한다.

### 2. 베이즈 통계 개요
- 베이즈 정리를 통해 새로운 데이터가 들어왔을 때 먼저 계산한 사후확률을 사전확률로 사용하여 갱신된 사후 확률을 계산할 수 있다.
- 조건부 확률은 유용한 통계적 해석을 제공하지만 인과관계를 추론할 때 함부로 사용해서는 안 된다.
- 인과관계는 데이터분포의 변화에 강건한 예측 모형을 만들 때 필요하다.
- 인과관계를 알아내기 위해서는 중첩요인의 효과를 제거하고 원인에 해당하는 변수만의 인과관계를 계산해야 한다.

---

## 2. Pytorch
- 딥러닝에 사용되는 프레임워크
- 다른 프레임워크에 비해 Dynamic computation graphs를 사용할 수 있다는 장점이 있음
- Numpy 구조를 가지는 Tensor 객체로 array 표현
- 자동미분을 지원하여 DL 연산을 지원
- 다양한 형태의 DL을 지원하는 함수와 모델을 지원함
