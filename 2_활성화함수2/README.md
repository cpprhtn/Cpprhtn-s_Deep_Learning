# 활성화 함수2
앞에서 배운 시그모이드(sigmoid), 렐루(ReLU) 등의 활성화함수는 각 층의 뉴런(노드)에서 뉴런으로 값이 전달 할 때, 다음층에 전달될 값을 조절할 때 사용되었다.

이번에 배울 활성화 함수는 **출력층 활성화 함수**라고 부르며, 가장 마지막 층인 출력층에서 사용한다.

크게 항등함수와 소프트맥스(softmax) 함수가 있다.

### 항등함수
- 항등함수는 회귀(Regression)문제에서 사용한다.
  - 회귀는 연속적인 수치를 예측할 때를 말한다.
  - 몸무게 예측, 키 예측 등등

  ![2-8](https://user-images.githubusercontent.com/63298243/91726627-8af68b80-ebdb-11ea-962f-d0e24e96879c.png)

- 항등함수는 말 그대로 입력한 값 그대로 출력층에 내보내 주는 역할이다.


### 소프트맥스 함수
-
  ![2-9](https://user-images.githubusercontent.com/63298243/91726635-8cc04f00-ebdb-11ea-9cdb-6dfa813c3080.png)
  ![2-10](https://user-images.githubusercontent.com/63298243/91726640-8e8a1280-ebdb-11ea-9d70-c257e7ad3ea6.png)
