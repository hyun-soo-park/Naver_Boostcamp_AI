## 1. CNN 첫걸음
### 1. Convolution 연산
- Convolution 연산은 커널을 입력벡터 상에서 움직여가며서 선형모델과 합성함수가 적용되는 구조
- Convolution 연산의 수학적인 의미는 신호를 커널을 이용해 국소적으로 증폭 또는 감소시켜서 정보를 추출 또는 필터링 하는 것
- 커널을 정의역 내에서 움직여도 변하지 않고 주어진 신호에 국소적으로 적용
- 다양한 차원에서 계산이 가능
- 2D에서는 커널을 입력벡터 상에서 움직여가면서 선형모델과 합성함수가 적용되는 구조
- 3D에서는 2차원을 3번 적용
- 커널이 모든 입력데이터에 공통으로 적용되기 때문에 역전파를 계산할 때도 convolution 연산이 나오게 됨

---

## 2.Optimization
### 1. Optimization 개요
- generalization
- Under-fitting vs over-fitting
- Cross validation
- Bias-variance tradeoff
- Bootstrapping
- Bagging and boosting

### 2. Gradiend Descent Methods
- Stochastic gradient descent
- Mini-batch gradient descent
- Batch gradient descent

### 3. Regularization
- Early stopping
- Parameter norm penalty
- Data augmentation
- Noise robustness
- Dropout
- Batch normalization
