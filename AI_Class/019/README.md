# 경사하강법 (Gradient Descent) -> Optimizer

## 확률적 경사 하강법 (SGD)
기울어진 방향으로 일정 거리만 가겠다는 단순한 방법

W는 갱신할 가중치 매개변수, dL/dW는 W에 대한 손실 함수의 기울기

η(이타)는 학습률을 의미하는데, 실제로는 0.01이나 0.001과 같은 값을 미리 정해서 사용


<img width="167" alt="019-2" src="https://user-images.githubusercontent.com/63298243/99655089-9a7cc680-2a9e-11eb-9e6e-955551e5a30c.png">

<img width="563" alt="019-3" src="https://user-images.githubusercontent.com/63298243/99655092-9b155d00-2a9e-11eb-8f53-2a96be2e6849.png">

## 모멘텀 (Momentum)
공이 가속도에 영향을 받아 바닥을 구르듯 행동

αv는 물체가 아무런 힘을 받지 않을 때 서서히 하강시키는 역할 (α는 0.9 등의 값으로 설정) -> 지면 마찰이나 공기 저항

V(velocity)는 (가)속도

<img width="161" alt="019-4" src="https://user-images.githubusercontent.com/63298243/99655095-9cdf2080-2a9e-11eb-9cd4-3186fb1f75f0.png">

<img width="130" alt="019-5" src="https://user-images.githubusercontent.com/63298243/99655097-9d77b700-2a9e-11eb-9a85-f413024f260e.png">

<img width="557" alt="019-6" src="https://user-images.githubusercontent.com/63298243/99655553-360e3700-2a9f-11eb-8c15-0866b4db8779.png">

## AdaGrad
움직임을 줄여나가는 방식, 지그재그 형태의 움직임이 갈수록 줄어듦

h는 기울기 값을 제곱하여 계속 더해줌

<img width="189" alt="019-7" src="https://user-images.githubusercontent.com/63298243/99655569-39092780-2a9f-11eb-889c-26dda792c04b.png">

<img width="198" alt="019-8" src="https://user-images.githubusercontent.com/63298243/99655571-39092780-2a9f-11eb-8455-3366924ddebf.png">

<img width="558" alt="019-9" src="https://user-images.githubusercontent.com/63298243/99655572-39a1be00-2a9f-11eb-8ec8-63fae7ecb2e8.png">


## Adam
모멘텀과 AdaGrad

두기법을 융합한 아이디어에서 출발한 기법

**현존하는 대부분의 모델에서 가장 점수가 잘 나옴**

<img width="560" alt="019-10" src="https://user-images.githubusercontent.com/63298243/99655574-3a3a5480-2a9f-11eb-81be-14943268feb7.png">
