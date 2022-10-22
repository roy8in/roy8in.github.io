---
title: Stationary Bootstrap
date: 2022-10-22
categories:
 - Quant
tags:
 - [Bootstrap]
comments: True
use_math: True
---

Stationary Bootstrap에 대해 알아본다.



### Ⅰ. Bootstrap

Bootstrap은 주어진 표본의 일부를 임의로(randomly), 중복을 허락하여 추출하는 행위를 반복하여 표본의 통계치(estimates)를 추정하는 방법을 의미[(B. Efron, 1979)](https://www.jstor.org/stable/2958830)한다. Bootstrap을 활용하면 주어진 하나의 시계열 표본으로부터 여러 개의 모조의(pseudo) 시계열들을 만들 수 있고, 각각의 모조 시계열을 활용해 계산한 통계치를 평균함으로써 표본의 통계치를 추정할 수 있다. 

표본의 크기가 크지 않을 경우 특정 데이터에 의해 통계치가 크게 달라질 수 있는데, 표본의 일부를 추출하는 행위를 반복함으로써 좀 더 robust한 통계치를 얻을 수 있기 위함이다. 즉, Bootstrap을 통해 표본 통계치의 표준 오차(standard erorr)를 줄일 수 있다.

시계열 표본의 일부를 추출할 때 크기를 1로 할 수 있고, 크기를 1보다 큰 블록(block)형태로 정할 수도 있다. 예를 들어 코스피 지수의 2001년 1월부터 2021년 12월까지 20년간의 240개의 월간 데이터가 표본이라고 한다면, 한 달 수익률을 임의로 추출할 수도 있고, 연속된 여러 달의 수익률을 블록 형태로 추출할 수도 있다.

추출하는 블록의 크기를 고정된 상수(constant)로 설정하는 Bootstrap 방식을 Moving Block Bootstrap 이라 부른다. 1994년 Politis와 Romano는 블록의 크기를 상수가 아닌 확률변수로 결정하는 Stationary Bootstrap 방법[(Dimitris N. Politis and Joseph P. Romano, 1994)](https://www.jstor.org/stable/2290993)을 제안하였다. 이때 블록의 크기(확률변수)는 일반적으로 기하분포를 따른다고 가정한다. 즉, Moving Block Bootstrap에서 블록의 크기를 $b$라고 하였다면, 이에 대응하는 Stationary Bootstrap은 블록의 크기로 기하분포 $Geo(1/b)$를 따르는 확률변수를 사용한다.
![image](/assets/images/Figure_Stationary Boot Strap.png)

Stationary Bootstrap의 장점을 알아보기 위해 다음과 같은 모의실험을 생각해본다. $Z_t$가 i.i.d. 정규분포를 따를 때  $t=1, ..., 200$에 대해 두 관측값(확률변수) $X_t$와 $Y_t$를 다음과 같이 정의한다.

$ X_t = Z_t + Z_{t-1}+Z_{t-2}+Z_{t-3}+Z_{t-4}, \quad\quad Y_t = Z_t - Z_{t-1}+Z_{t-2}-Z_{t-3}+Z_{t-4} $

이 때 $\sum_{i=1}^{200} X_I = 5 \sum_{i=1}^{200} Z_i$이기 때문에 정규화된 $X_t$의 평균 $\sqrt{N} \; \bar{X}_N$의 분산은 $25(=5^2)$에 가까울 것으로 추정할 수 있다. 비슷한 이유로 정규화된 $Y_t$의 평균  $\sqrt{N} \; \bar{Y}_N$의의 분산은 $1(=1^2)$에 가까울 것이다.

추출하는 블록의 크기를 $b$라고 할 때, 1부터 200까지의 $b$를 대상으로  $\sqrt{N} \; \bar{X}_N$와  $\sqrt{N} \; \bar{Y}_N$의 분산을 계산해보면 [그림1]과 [그림2]와 같은 모습을 확인할 수 있다. [그림1]과 [그림2]에서 직선은 Moving Blocks를, 점선은 Stationary Bootstrap을 활용했을 때를 나타낸 것이다. $X_t$와 $Y_t$ 모두 Stationary Bootstrap으로 계산한 평균의 분산 추정치가 Moving Blocks Bootstrap으로 계산한 분산 추정치보다 블록 크기 변화에 덜 가변적인 모습이다. 실제 Stationary Bootstrap으로 계산한 추정치는 Moving Block Bootstrap으로 계산한 추정치의 가중이동평균이다.

<b>[그림1] 블록 크기 $b$에 따른  $\sqrt{N} \bar{X}_N$의 분산</b>

![image](/assets/images/Figure 1_Moving Blocks and Stationary Bootstrap Estimates.png)

<br>

<b>[그림2] 블록 크기 $b$에 따른  $\sqrt{N} \bar{Y}_N$의 분산</b>

![image](/assets/images/Figure 2_Moving Blocks and Stationary Bootstrap Estimates.png)

\* Politis and Romano(1994) 재인용

<br>

실무에서 Bootstrap을 활용함에 있어 블록 크기를 결정하는 것은 중요하다. 최적의 블록 크기에 대한 연구([Dimitris N. Politis and_Halbert White, 2004](http://public.econ.duke.edu/~ap172/Politis_White_2004.pdf))를 활용하여도, 금융 데이터라는 특성을 고려할 경우 표본으로부터 도출(추정)한 최적 블록의 크기가 실제로 최적이라고 확실한 수 없다. 최적 블록 크기에 대한 불확실성이 존재하는 상황에서 통계치가 블록 크기에 민감하게 반응하는 Moving Block Bootstrap 보다는 덜 민감하게 반응하는 Stationary Bootstrap이 금융 시계열을 다룰 때 더 나은 모델이 될 수 있다고 생각한다.
