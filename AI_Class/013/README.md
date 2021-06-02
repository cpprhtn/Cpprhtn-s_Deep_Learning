# 활성화 함수1

- 앞서 배운 편향이 추가된 식을 아래와 같이 표현할 수 있다.

![2-1](https://user-images.githubusercontent.com/63298243/90618819-6f8a9880-e24b-11ea-9ce5-8a4a121022ad.jpeg)

- 입력 신호의 총합이 h(x)라는 함수를 거처 0과 1로 출력됨을 알 수 있다.

### 활성화 함수란
- 위에서 등장한 h(x)라는 함수처럼 입력 신호의 총합을 출력 신호로 변환하는 함수를 일빈적으로 활성화 함수라고 한다.
- 입력 신호의 총합이 활성화(0/1)를 일으키는지를 정하는 역할을 한다.

## 계단 함수
- 단 함수는 퍼셉트론에서 사용하는 활성화 함수이다.
- 위의 조건 분기 식처럼 입력이 0을 넘으면 1을 출력하고, 이외에는 0을 출력하는 함수이다.

#### 계단 함수 구현 1
```Python
def step_F(x):
  if x>0:
    return 1
  else:
    return 0
```
- 위의 구현은 단순하지만 x는 실수만 받아들인다.
- 또한 신경망이 처리하는 type인 numpy배열을 지원하지 않는다.

#### 게단 함수 구현 2
```Python
import numpy as np
def step_F(x):
  y = x > 0
  return y.astype(np.int)
```
- 위 식을 간단히 설명하자면
  - 넘파이 배열에 부등호 연산을 수행시 bool 배열이 생성
  - 이를 int형으로 형변환하여 0과 1로 return


#### 함수 그래프
```Py
import numpy as np
import matplotlib.pyplot as plt
x = np.arange(-5.0, 5.0, 0.1)
y = step_F(x)
plt.plot(x, y)
plt.ylim(-0.1, 1.1)
plt.show()
```

![2-2](https://user-images.githubusercontent.com/63298243/90619242-f475b200-e24b-11ea-869e-803aa49a5df7.png)

- 위 그림처럼 0을 기준으로 y값이  0과 1로 나뉜다.

## 시그모이드 함수 (Sigmoid Function)
- 시그모이드 함수는 신경망에서 사용하는 활성화 함수 중 하나이다.
- S자 모양의 함수라는 뜻이다.
- Vanishing Gradient 문제로 사용하지 않는다.
#### 시그모이드 함수 구현
```Py
def sigmoid(x):
  return 1 / (1 + np.exp(-x))
```

#### 함수 그래프
```Py
import numpy as np
import matplotlib.pyplot as plt
x = np.arange(-5.0, 5.0, 0.1)
y = sigmoid(x)
plt.plot(x, y)
plt.ylim(-0.1, 1.1)
plt.show()
```

![2-3](https://user-images.githubusercontent.com/63298243/90748457-2ac73600-e30d-11ea-93c3-c96350ab2763.png)


## 하이퍼볼릭 탄젠트 함수 (tanh)
- 시그모이드 함수와 거의 비슷하나, 0근처에서의 변화율이 더 크다.
- 주로 RNN(순환 신경망)에서 사용한다.

#### tanh 함수 구현
```Py
def tanh_F(x):
  return np.tanh(x)
```

#### 함수 그래프
```Py
import numpy as np
import matplotlib.pyplot as plt
x = np.arange(-5.0, 5.0, 0.1)
y = tanh_F(x)
plt.plot(x, y)
plt.ylim(-0.1, 1.1)
plt.show()
```

<img width="823" alt="013-1" src="https://user-images.githubusercontent.com/63298243/105956842-bbbfeb80-60bb-11eb-9791-d00fa025436e.png">



## 렐루 함수 (Rectified Linear Unit)
- 비교적 최근에 만들어진 신경망 활성화 함수이다.
- 시그모이드 함수보다 많이 사용한다.

<img width="188" alt="2-4" src="https://user-images.githubusercontent.com/63298243/90751221-d02fd900-e310-11ea-81a0-35e16c3f6e7a.png">

#### 렐루 함수 구현
```Py
def relu(x):
  return np.maximum(0, x) //두 입력중 큰 값을 선택해 반환
```

![2-5](https://user-images.githubusercontent.com/63298243/90751230-d1f99c80-e310-11ea-8e71-8d9cd35b32e9.png)

## Parametric ReLU (PReLU)
- 렐루의 단점을 보완한 활성화 함수이다.
  - 렐루에서는 x값이 -0.1이어도 0, -100이어도 0이 나오기 때문에 음수값에 대한 정도를 반영하기 어렵다.

  ![2-7](https://user-images.githubusercontent.com/63298243/90752066-e5593780-e311-11ea-8ed5-0368f5c30638.png)

#### P-렐루 함수 구현
```Py
def PReLU(x):
    a = 0.05 //0 이하에 곱해줄 값
    return np.maximum(a*x, x)
```
- 여기서 a값이 0.01일때 LeakyReLU(LReLU)라고 한다.

![2-6](https://user-images.githubusercontent.com/63298243/90751237-d3c36000-e310-11ea-9965-59f175127c80.png)

