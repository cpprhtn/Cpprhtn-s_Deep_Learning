# Cppthrn's_Deep_Learning
#### (주의)Python 문법에 대한 설명은 하지않음


AI기술인 머신러닝과 딥러닝중 딥러닝을 먼저 알아야 한다고 생각한다.

우선 머신러닝 안에 딥러닝이 포함되는 개념이라고 보면 된다.

머신 러닝은 기본적으로 알고리즘을 이용해 데이터를 분석하고, 분석을 통해 학습하며,
학습한 내용을 기반으로 판단이나 예측을 한다.
이 중에서 학습하고 예측을 하는 과정에서 머신러닝과 딥러닝이 구분이 된다.
머신러닝의 경우에는 구현되어있는 라이브러리를 가져와 하이퍼파라미터 값의 조정으로 최적의 성능을 찾아내는 방법이다.
대부분의 구현된 라이브러리는 수학적 기법에 의한 것이다.


반면에 딥러닝은 뇌의 뉴런과 유사한 정보 입출력 계층을 활용해 데이터를 학습한다.
이를 달성하기 위해 딥러닝은 인공 신경망이라는 계층화된 알고리즘 구조를 사용한다.
인공 신경망의 설계는 인간 두뇌의 생물학적 신경망에서 영감을 얻어,
표준 머신 러닝 모델보다 훨씬 더 뛰어난 학습 프로세스를 제공한다.

```
Python Verson = 3.7

Development environment = Anaconda - Spyder 4.0.1
```
## 개론 강의 목록
|Date|Title|
|:---:|:---|
|1|인공지능 소개|
|2|인공지능 발전의 역사|
|3|문제 해결 및 탐색 전략|
|4|휴리스틱 탐색|

## 실습 강의 목록
|Date|Title|Description|
|:---:|:---|:---|
|1|[머신러닝의 종류](./AI_Class/001/README.md)|지도학습, 비지도학습, 강화학습, 준지도학습에 대한 설명|
|*|지도학습||
|2|[단순회귀분석](./AI_Class/002/Simple_linear_regression.ipynb)|단순회귀분석에 대한 설명|
|3|[다항회귀분석](./AI_Class/003/Polynomial_regression.ipynb)|다항회귀분석에 대한 설명|
|4|[다중회귀분석](./AI_Class/004/multivariate_regression.ipynb)|다중회귀분석에 대한 설명|
|5|[KNN](./AI_Class/005/knn_classification.ipynb)|KNN에 대한 설명|
|6|[SVM](./AI_Class/006/svm_classification.ipynb)|SVM에 대한 설명|
|*|CART(분류, 회귀 둘다 가능)||
|7|[DecisionTree](./AI_Class/007/decision_tree.ipynb)|DecisionTree에 대한 설명|
|8|[RandomForest](./AI_Class/008/random_forest.ipynb)|RandomForest에 대한 설명|
|*|비지도학습||
|9|[k-Means](./AI_Class/009/k_Means.ipynb)|k-Means에 대한 설명|
|10|[DBSCAN](./AI_Class/010/DBSCAN.ipynb)|DBSCAN에 대한 설명|
|*|신경망||
|11|[머신러닝과 딥러닝](./AI_Class/011/README.md)|머신러닝과 딥러닝, ANN에 대한 설명|
|12|[퍼셉트론](./AI_Class/012/README.md)|퍼셉트론 개념 설명|
|13|[활성화함수1](./AI_Class/013/README.md)|활성화 함수 설명1|
|14|[활성화함수2](./AI_Class/014/README.md)|활성화 함수 설명2|
|15|[신경망 연산방법](./AI_Class/015/README.md)|신경망 연산방법 설명|
|16|[신경망 구현](./AI_Class/016/README.md)|신경망 파이썬으로 구현해보기|
|17|[신경망 계산](./AI_Class/017/README.md)|신경망 계산해보기|
|18|[손실함수](./AI_Class/018/README.md)|cost function 설명|
|19|[경사하강법](./AI_Class/019/README.md)|경사하강법 설명|
|20|[Keras 모델 사용방법](./AI_Class/020/README.md)|케라스 라이브러리를 이용해 딥러닝 모델 생성하는 방법 알아보기|
|*|DNN||
|21|[DNN 실습](./AI_Class/021/Dnn.ipynb)|이제까지 배운 방법을 통해서 딥러닝 모델로 제작|
|22|[DNN 실습2](./AI_Class/022/Dnn2.ipynb)|실습 2|
|23|[DNN 실습3](./AI_Class/023/README.md)|캐글에서 실제로 적용해보기|
|*|개인 프로젝트||
|24|[개인 프로젝트 진행순서](./AI_Class/024/README.md)|DNN모델을 이용한 개인 프로젝트 진행해보기|
|*|CNN||
|25|[CNN 이론](./AI_Class/025/README.md)|CNN 이론에 대한 설명|
|26|[CNN 실습](./AI_Class/026/CNN.ipynb)|mnist data를 이용한 CNN 실습|
|27|[CNN 실습2](./AI_Class/027/CNN2.ipynb)|CNN으로 개와 고양이 이미지를 분류|
|28|[CNN 실습3](./AI_Class/028/CNN3.ipynb)|CNN으로 의류 이미지 분류|
|*|RNN||
|29|[RNN 이론](./AI_Class/029/README.md)|RNN 이론에 대한 설명|
|30|[LSTM 이론](./AI_Class/030/README.md)|LSTM 이론에 대한 설명|

## 딥러닝을 다루면서 드는 생각들
- 기계가 사람처럼 생각이 가능한가?
  - 윤리의식이나 도덕적 행동에 대한 이해가 가능할까?

- 강화학습을 기반으로 해서, 아기키우듯이 10년, 20년 가르치면 인간처럼 활동이 가능할까?
  - LOW계층에는 무의식적인 움직임, 행동이 프로그래밍 되어야?

- 신경망 이외로는 구현할 방법이 없을까?

- 인간은 누구나 실수를 한다. AI역시 실수도 할 수 있어야 하지 않나?
  - 의도되지 않은 실수
  - 역량을 벗어난 수행을 할 때 발생?

  - 이루다 사례를 보면서, Input 데이터가 얼마나 중요한지를 다시 느낌