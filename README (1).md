# ML_Lectur1-3_Summary

# Lecture 1. introduction

ML은 크게 Supervised learning 과 Unsupervised learning 으로 나눌 수 있다. 

Supervised learning: 데이터 셋을 제공 받고 입력과 출력 간에 관계가 있다고 생각하면서 올바른 출력이 어떻게 생겼는지 이미 알고 있음. 지도 학습 문제에서는 회귀와 분류 문제로 구분이 된다. 회귀(Regression)는 연속적인 출력 내에서 결과를 예측하는 것이다. 예를 들면, 중간고사 점수, 집 가격 등과 같은 문제. 분류(Classification)는 이산 적인 출력 값을 예측 하는 것이다. 예를 들면, 암 진단 여부 등과 같은 문제. Superviesd learning 에는 noise 값이 존재하면 안된다. 

-In supervised learning, we are given a data set and already know what our correct output should look like, having the idea that there is a relationship between the input and the output.

– Supervised learning problems are categorized into "regression" and "classification" problems. In a regression problem, we are trying to predict results within a continuous output, meaning that we are trying to map input variables to some continuous function. In a classification problem, we are instead trying to predict results in a discrete output. In other words, we are trying to map input variables into discrete categories

# Lecture 2. Linear Repression_One

![image.png](image.png)

- Training Set 과 Learning Algorithm은 내가 결정하는 것. 그럼 저절로 h 도 내가 결정하게 되는 것. h만 결정하게 되면 다른 모델에서도 사용 가능
- h_θ(x) = θ_0 + θ_1x 여기서 θ_0과 θ_1 이 두 parameter를 알아내야한다.
- error 값은 무조건 생기게 되어있고, 이를 줄여주는 것이 목표다.

![image.png](image%201.png)

- 1/2 → 미분하면 2가 앞으로 튀어나오는데, 이를 없애주려고 곱해준 것.
- m = 학습 데이터 갯수
- Cost function J(θ_0, θ_1)를 최소로 하는 것이 목표. 그리고 제곱을 해주는 이유 : 1. distance 개념이라 사용 2. 미분하기 편함.

![image.png](image%202.png)

여기서 J(θ_1) 그래프는 2차 방정식의 형태로 나온다. 즉 Cost function 이 2차식이 아니라 1차식이면 minimization point 를 찾기 힘들다. 

## Gradient descent(경사하강법)

![image.png](image%203.png)

- 위 그림이 최종적인 goal(global minimum이다.)
- 시작점이 다르면 아래 사진과 같이 local minimum에 빠질 수 있다.
- 결과값이 달라지는 이유는 Random 하게 initialization 했기 때문이다.

![image.png](image%204.png)

- 여기서 α 값은 learning rate 이다. 이 값을 얼마나 잘 적당히 설정하냐가 관건.
- α 값이 너무 작을 경우, 촘촘하게 진행되기 때문에 경사하강법이 굉장히 느려지게 된다. 반대로 클 경우, 발산 할 수 있어서 최소점을 overshoot 하게 된다.

![image.png](image%205.png)

- 여기서 기울기가 0이 되면서 미분값이 0이 나와버린다. 그래서 local minimum에 빠져버리는 것. 이런 경우, 가속도가 있거나 이런 값의 History를 가져와서 0이 되는 것을 방지 할 수 있다. 심지어 α값이 fixed 되어 있어도 이런 경우가 발생 할 수 있다.