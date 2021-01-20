# RNN

RNN은 Recurrent Neural Network의 약자로 음성, 문자 등 순차적으로 등장하는 데이터 처리에 적합한 모델입니다.

## RNN의 특징

### 1. 시계열 예측

RNN은 은닉층의 노드에서 활성화 함수를 통해 나온 결과값을 출력층 방향으로도 보내면서, 다시 은닉층 노드의 다음 계산의 입력으로 보내는 특징을 갖고있습니다.

![029-1](https://user-images.githubusercontent.com/63298243/105148885-3e89f900-5b46-11eb-9cf1-876a2afd09ce.png)

RNN에서 은닉층에서 활성화 함수를 통해 결과를 내보내는 역할을 하는 노드를 셀(cell)이라고 합니다. 셀은 이전의 값을 기억하려고 하는 일종의 메모리 역할을 수행하므로 이를 메모리 셀 또는 RNN 셀이라고 표현합니다.

위의 이미지를 다시 아래와 같이 표현할 수 있습니다.

![029-2](https://user-images.githubusercontent.com/63298243/105148889-3fbb2600-5b46-11eb-80ea-a23ea2626d21.png)

메모리 셀이 출력층 방향으로 또는 다음 시점 t+1의 자신에게 보내는 값을 은닉 상태(hidden state)라고 합니다.  
즉 t 시점의 메모리 셀은 t-1 시점의 메모리 셀이 보낸 은닉 상태값을 t 시점의 은닉 상태 계산을 위한 입력값으로 사용합니다.

우리가 알고있던 노드 형태로 한번 다시 확인해봅시다.

![029-3](https://user-images.githubusercontent.com/63298243/105148892-4053bc80-5b46-11eb-91e9-6d4de060bcc4.png)

이는 시계열(연속된 시간) 예측에서 뛰어난 성능을 보입니다.

### 2. 입출력의 유연성

아래 그림과 같이 입력과 출력의 길이를 다르게 설계 할 수 있어 여러 방면으로 사용할 수 있습니다.

![029-4](https://user-images.githubusercontent.com/63298243/105148896-40ec5300-5b46-11eb-9003-935bb741ada4.png)

- one-to-many의 예시로는 하나의 사진에 대해서 그 사진의 제목을 출력하는 이미지 캡셔닝(Image Captioning)이 있습니다.

![029-5](https://user-images.githubusercontent.com/63298243/105148899-4184e980-5b46-11eb-919c-40793bcb3ecd.png)

- many-to-one의 예시로는 입력된 문서가 긍정적인지 부정적인지를 판별하는 감성 분류(sentiment classification), 또는 메일이 정상 메일인지 스팸 메일인지 판별하는 스팸 메일 분류(spam detection)가 있습니다.

![029-6](https://user-images.githubusercontent.com/63298243/105148901-4184e980-5b46-11eb-9f82-a78d2ce521a7.png)

- many-to-many의 에시로는 입력 문장으로 부터 대답 문장을 출력하는 챗봇과 입력 문장으로부터 번역된 문장을 출력하는 번역기, 또는 개체명 인식이나 품사 태깅과 같은 것이 있습니다.

![029-7](https://user-images.githubusercontent.com/63298243/105148902-421d8000-5b46-11eb-88e9-466b947316ca.png)

## RNN의 연산과정

![029-8](https://user-images.githubusercontent.com/63298243/105148905-421d8000-5b46-11eb-9000-f04cd9c648b5.png)

현재 시점 t에서의 은닉 상태값을 h<sub>t</sub>라고 정의하겠습니다.  
은닉층의 메모리 셀은 h<sub>t</sub>를 계산하기 위해서 총 두 개의 가중치를 갖게 됩니다.  
하나는 입력층에서 입력값을 위한 가중치 W<sub>x</sub>이고, 하나는 이전 시점 t-1의 은닉 상태값인 h<sub>t-1</sub>을 위한 가중치 W<sub>h</sub>입니다.

이를 식으로 표현하면 다음과 같습니다.
은닉층 : h<sub>t</sub>=tanh(W<sub>x</sub>x<sub>t</sub>+W<sub>h</sub>h<sub>t-1</sub>+b)  
출력층 : y<sub>t</sub>=f(W<sub>y</sub>h<sub>t</sub>+b)  
단, f는 비선형 활성화 함수 중 하나.

RNN의 은닉층 연산을 벡터와 행렬 연산으로 이해할 수 있습니다.  
자연어 처리에서 RNN의 입력 x<sub>t</sub>는 대부분의 경우에서 단어 벡터로 간주할 수 있는데, 단어 벡터의 차원을 d라고 하고, 은닉 상태의 크기를 D<sub>h</sub>라고 하였을 때 각 벡터와 행렬의 크기는 다음과 같습니다.

x<sub>t</sub> : (d×1)  
W<sub>x</sub> : (D<sub>h</sub>×d)  
W<sub>h</sub> : (D<sub>h</sub>×D<sub>h</sub>)  
h<sub>t-1</sub> : (D<sub>h</sub>×1)  
b : (D<sub>h</sub>×1)  

배치 크기가 1이고, d와 D<sub>h</sub> 두 값 모두를 4로 가정하였을 때, RNN의 은닉층 연산을 그림으로 표현하면 아래와 같습니다.

![029-9](https://user-images.githubusercontent.com/63298243/105148906-42b61680-5b46-11eb-96f8-ea38ab42621a.png)

이때 h<sub>t</sub>를 계산하기 위한 활성화 함수로는 주로 `하이퍼볼릭 탄젠트` 함수(tanh)가 사용됩니다. (ReLU로 사용하기도 합니다.)

위의 식에서 각각의 가중치 W<sub>x</sub>, W<sub>h</sub>, W<sub>y</sub>의 값은 모든 시점에서 값을 동일하게 공유합니다. 만약, 은닉층이 2개 이상일 경우에는 은닉층 2개의 가중치는 서로 다릅니다.

출력층은 결과값인 y<sub>t</sub>를 계산하기 위한 활성화 함수로는 상황에 따라 달라집니다.

예를 들어서 이진 분류를 해야하는 경우라면 시그모이드 함수를 사용할 수 있고 다양한 카테고리 중에서 선택해야하는 문제라면 소프트맥스 함수를 사용합니다.