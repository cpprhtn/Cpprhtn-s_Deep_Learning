# 신경망 구현

## 아래와 같은 n층 신경망을 구현해본다.

![4-1](https://user-images.githubusercontent.com/63298243/90955717-e4afd500-e4ba-11ea-8414-868eb72bfafc.png)


### 3층 신경망(n = 2)
#### 구조분석
- 입력층(뉴런 2개) -> 은닉층1(뉴런 3개) -> 은닉층2(뉴런 2개) -> 출력층(뉴런 2개)
  - 입력이 2개이고 출력이 2개인 신경망

- 사용할 활성화 함수
  - ReLU (or Sigmoid)
```Py
def relu(x):
  return np.maximum(0, x)
```

- 연산 순서
  - 0층=>1층: x -> a -> z
  - 1층=>2층: z -> a -> z
  - 2층=>3층: z -> a -> y

- a = np.dot(x,w)+b
## 구현 코드 (각 층별로 자세히)
- W1, b1은 1층 구현이라는 의미
- 배열 형태 관계를 확인하시길 바람
  - 이해가 안될 시 [3_신경망 연산](https://github.com/cpprhtn/Cppthrn-s_Deep_Learning/tree/master/3_%EC%8B%A0%EA%B2%BD%EB%A7%9D%EC%97%B0%EC%82%B0) 복습부탁
```Py
import numpy as np

#사용할 활성화 함수 정의
def relu(x):
  return np.maximum(0, x)

#0층(뉴런 2개) -> 1층(뉴런 3개)
x = np.array([1.0,0.5]) #입력: (2,) 배열형태
W1 = np.array([[0.1,0.3,0.5],[0.2,0.4,0.6]]) #가중치(임의의 값): (2,3) 배열형태
b1 = np.array([0.1,0.2,0.3]) #편향: (3,) 배열형태

a1 = np.dot(x, W1) + b1
z1 = relu(a1)

#1층(뉴런 3개) -> 2층(뉴런 2개)
W2 = np.array([[0.1,0.4],[0.2,0.5],[0.3,0.6]]) #(3,2) 배열형태
b2 = np.array([0.1,0.2]) #(2,) 배열형태
a2 = np.dot(z1, W2) + b2
z2 = relu(a2)

#2층(뉴런 2개) -> 3층(뉴런 2개)
W3 = np.array([[0.1,0.3],[0.2,0.4]]) #(2,2) 배열형태
b3 = np.array([0.1,0.2]) #(2,) 배열형태

a3 = np.dot(z2 , W3) + b3
Y = a3
```

## 구현 코드 정리.Ver
```Py
import numpy as np

def relu(x):
  return np.maximum(0, x)

def init_network(): #n층의 가중치와 편향값을 미리 정의
    network = {}
    network['W1'] = np.array([[0.1,0.3,0.5],[0.2,0.4,0.6]])
    network['b1'] = np.array([0.1,0.2,0.3])
    network['W2'] = np.array([[0.1,0.4],[0.2,0.5],[0.3,0.6]])
    network['b2'] = np.array([0.1,0.2])
    network['W3'] = np.array([[0.1,0.3],[0.2,0.4]])
    network['b3'] = np.array([0.1,0.2])

    return network

def nn(network, x): #신경망 Neural network
    W1,W2,W3 = network['W1'],network['W2'],network['W3']
    b1,b2,b3 = network['b1'],network['b2'],network['b3']

    a1 = np.dot(x,W1) + b1
    z1 = relu(a1)
    a2 = np.dot(z1, W2) + b2
    z2 = relu(a2)
    a3 = np.dot(z2, W3) + b3
    y = a3

    return y


network = init_network()
x = np.array([1.0,0.5])
y = nn(network ,x)
print(y)
```
