## 1. RNN

### 1. 시퀀스 데이터
- 소리, 문자열, 주가 등의 데이터
- 독립동등분포 가정을 잘 위배하기 때문에 순서를 바꾸거나 과거 정보에 손실이 발생하면 확률 분포도 바뀜
- 이전 시퀀스의 정보를 가지고 앞으로 발생할 데이터의 확률분포를 다루기 위해 조건부 확률을 이용할 수 있음
- 시퀀스 데이터를 다루기 위해선 길이가 가변적인 데이터를 다룰 수 있는 모델이 필요


### 2. 기울기 소실의 해결책
- 시퀀스 길이가 길어지는 경우 BPTT를 통한 역전파 알고리즘의 계산이 불안정 해지므로 길이를 끊는 것이 필요
- 이런 문제들 때문에 Vanilla RNN은 길이가 긴 시퀀스를 처리하는 데 문제가 있음

---

## 2. Sequential Models

### 1. Sequential Models
- Naive Sequence Model
- Autoregressive Model
- Markov Model
- Latent autogressive Model


### 2. transform

- the first sequence transduction model based entirely on attention
- 'Thinking' and 'Machines'
