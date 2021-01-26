## 2-1 경사하강법

### 1. 미분 : 변수의 움직임에 따른 함수값의 변화를 측정하기 위한 도구로 최적화에서 제일 많이 사용하는 기법
```python
import sympy as sym
from sympy.abc import x

sym.diff(sym.poly(x**2 + 2*x + 3), x)
```
- 미분은 주어진 점에서 접선의 기울기를 의미한다
- 한 점에서 접선의 기울기를 알면 어느 방향으로 점을 움직여야 함수값이 증가/감소 하는지 알 수 있다
- 미분값을 더하면 경사상승법이라 하며 함수의 극대값의 위치를 구할 때 사용한다
- 미분값을 빼면 경사하강법이라 하며 함수의 극소값의 위치를 구할 때 사용한다
- 경사상승/경사하강 방법은 극값에 도달하면 움직임을 멈춘다

```python
import sympy as sym
import numpy as np
from sympy.abc import x

def func(val):
    fun = sym.poly(x**2 + 2*x + 3)
    return fun.subs(x,val), fun

def func_gradient(fun, val):
    _, function = fun(val)
    diff = sym.diff(function, x)
    return diff.subs(x,val),diff

def gradient_descent(fun, init_point, lr_rate = 1e-2, epsilon = 1e-5):
    cnt = 0
    val = init_point
    diff, _ = func_gradient(fun, init_point)
    while np.abs(diff) > epsilon:
        val = val - lr_rate * diff
        diff, _ = func_gradient(fun, val)
        cnt += 1

    print("함수 : {}, 연산횟수 : {}, 최소점 : ({}, {})".format(fun(val)[1],cnt,val,fun(val)[0]))

gradient_descent(fun = func, init_point=np.random.uniform(-2,2))
```

- 각 변수 별로 편미분을 계산한 그래디언트 벡터를 이용하여 경사하강/경사상승법에 사용할 수 있다.
- 이론적으로 경사하강법은 미분 가능하고 볼록한 함수에 대해선 적절한 학습률과 학습횟수를 선택했을 때 수렴이 보장된다.
- 비선형회귀 문제의 경우 목적식이 볼록하지 않을 수 있으므로 수렴이 항상 보장되지는 않는다.

### 2. 확률적 경사하강법 : 모든 데이터를 사용해서 업데이트 하는 대신 데이터 한개 또는 일부 활용하여 업데이트 한다.
- 볼록이 아닌 목적식은 SGD를 통해 최적화 할 수 있다.
- SGD는 데이터의 일부를 가지고 패러미터를 업데이트 하기 때문에 연산자원을 좀 더 효율적으로 활용하는데 도움이 된다.
- 경사하강법은 전체 데이터를 가지고 목적식의 그레디언트 벡터를 계산한다.
- SGD는 미니배치를 가지고 그레디언트 벡터를 계산한다.
- 미니 배치는 확률적으로 선택하므로 목적식 모양이 바뀌게 된다.
- SGD는 볼록이 아닌 목적식에서도 사용 가능하므로 경사하강법보다 머신러닝 학습에 더 효율적이다.
