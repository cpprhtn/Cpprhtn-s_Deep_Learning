# 머신러닝의 종류

## 지도학습

지도학습에는 알고리즘에 주입되는 훈련 데이터에 "레이블"이라는 답(결과값)이 포함되어 있다.

크게 분류(Classification)와 회귀(Regression)로 나눌 수 있다.

- 분류 : class를 예측하는 것
    - (ex)
    - 내가 받은 메일이 스팸메일이냐 아니냐, 누군가가 나에게 보낸 메세지가 욕설이냐 아니냐와 같이 대답이 예/아니오로 구분될 수 있는 문제
    - 입력 text가 영어 / 프랑스어 / 독일어 / 이탈리아어 / 스페인어 / 한국어 / 일본어 / 중국어 / 등등 어느 언어인지 분류하는 문제

- 회귀 : 연속적인 숫자, 즉 예측값이 float 형태인 문제들을 해결하는데 사용
    - (ex)
    - 지하철 역과의 거리, 일정 거리안의 관공서, 마트, 학군의 수 등등 여러 feature들로 어떤 지역의 땅값을 예측하는 문제
    - 누군가의 키와 몸무게를 예측하는 문제

![001-1](https://user-images.githubusercontent.com/63298243/97887533-664e9980-1d6d-11eb-976b-a7b0691c410d.png)


- 분류와 회귀의 구분법
    - 분류는 class를 예측하므로 결과값이 확률로 주어짐 (0~1사이)
    - 회귀는 확률을 예측하는 것이 아님. 값들의 연속성이 있고, 그 연속성 중에 어디에 점을 찍을지 결정하는 것



#### 사용되는 알고리즘
- K-nearest neighbors (K-최근접 이웃)
- linear regression (선형 회귀)
- logistic regression (로지스틱 회귀)
- Support Vector Machine[SVM] (서포트 벡터 머신)
- decision tree & random forest (결정트리 & 랜덤 포레스트)
- neural networks (신경망)




## 비지도 학습

비지도 학습은 지도학습과는 반대로 훈련 데이터에 레이블이 없다.

#### 사용되는 알고리즘
- 군집
    - K-means (K-평균)
    - DBSCAN
    - HCA (계층 군집 분석)
    - 이상치 탐지와 특이치 탐지
    - one-class SVM (원-클래스)
    - isolation forest
    - 
![001-2](https://user-images.githubusercontent.com/63298243/97889616-eaa21c00-1d6f-11eb-85c4-d69104891410.png)


- 예시 : 신용카드 부정 사용 탐지, 구매 패턴 분석 등 소비자 행동 특성을 그룹화하는데 사용된다.
- 어떤 소비자와 유사한 특성을 갖는 집단을 구분하게 되면, 같은 집단 내의 다른 소비자를 통해 새로운 소비자의 구매 패턴이나 행동 등을 예측하는데 활용할 수 있다.

- 시각화와 차원축소
    - PCA (주성분 분석)
    - Kernel PCA
    - LLE (지역적 선형 임베딩)
    - t-SNE
<img width="625" alt="001-3" src="https://user-images.githubusercontent.com/63298243/97889626-ed047600-1d6f-11eb-80c0-ea1edb9a0fa7.png">
<t-SNE를 이용해 시각화>

- 연관 규칙 학습
    - 어프라이어리
    - 이클렛

## 준지도 학습

간단히 말하면 지도학습과 비지도학습을 결합한 학습이다.

레이블이 있는 데이터와 없는 데이터 모두를 사용하여 예측에 사용한다.

#### 사용되는 알고리즘
- Deep Belief Network[DBN] (심층 신뢰 신경망)
- Restricted Boltzmann Machine[RBM] (제한된 볼츠만 머신)

## 강화학습 (Reinforcement Learning)

학습하는 시스템을 에이전트라고 부르며 환경(environment)을 관찰해서 행동(action)을 실행하고 그 결과로 보상(reward)을 받는다.

시간이 지나면서 가장 큰 보상을 얻기 위해 정책(policy)이라고 부르는 최상의 전략을 스스로 학습한다.

<img width="625" alt="001-4" src="https://user-images.githubusercontent.com/63298243/97890765-491bca00-1d71-11eb-98f0-d256920c8d11.png">


#### 사용되는 알고리즘
- Deep Q-Networks[DQN]
- Double DQN
- actor-critic (액터-크리틱 알고리즘)
- Asynchronous Advantage actor-critic (A3C)
- Soft actor-critic (SAC)
