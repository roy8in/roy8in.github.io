---
title: 마코위츠의 저주(Markowitz's Curse)
date: 2022-11-27
categories:
 - Portfolio
tags:
 - [MVO, Portfolio Optimization]
comments: True
use_math: True
---

현대 포트폴리오 이론의 중심에 있는 해리 마코위츠(Harry Markowitz)의 평균-분산 최적화(Mean-Variance Optimization, 이하 MVO) 활용 관련 일종의 패러독스를 정리

Markos M. Lopez de Prado의 글을 정리한 것

### Ⅰ. Convex Portfolio Optimization

$N$개의 자산으로 구성된 포트폴리오를 생각해본다. 평균 벡터를 $\mu$, 공분산 행렬을 $V$로 쓰기로 한다. 마코위츠의 통찰력은 전통적인 자산 배분 문제를 Quadratic Programming으로 다루는 것이다. 이 Quadratic Programming의 목적은 포트폴리오에 제약을 주는 벡터$a$에 대해서 $w'a=1$이며
$$
\min_w \frac{1}{2} w' V w
$$
을 만족하는 비중 벡터 $w$를 찾는 것이다. 이 문제는 Lagrangian형태로 바꿔 쉽게 풀 수 있다.
$$
L \left(w, \lambda \right) = \frac{1}{2} w'Vw - \lambda(w'a -1)
$$
로 설정할 수 있고, 
$$
\begin{equation}\label{eq:1} \frac{\partial L \left(w, \lambda \right)}{\partial w} = Vw - \lambda a \end{equation}
$$


,
$$
\begin{equation}\label{eq:2} \frac{\partial L\left( w, \lambda\right)}{\partial \lambda} = w'a -1\end{equation}
$$
이다. 식 $\eqref{eq:1}$ 조건이 $0$이 되려면 $v w- \lambda a =0$이므로 
$$
\begin{equation} \label{eq:3} w=\lambda V^{-1} a\end{equation}
$$
이고,

식 $\eqref{eq:2}$ 조건이 0이 되려면
$$
\begin{equation}\label{eq:4} w'a =a'w=1\end{equation}
$$
$w'a =a'w=1$이다.

식 $\eqref{eq:3}$ 양변에 $a'$를 곱하고 식 $\eqref{eq:4}$를 활용하면
$$
a'w= a'\lambda V^{-1}a = \lambda a' V^{-1}a=1
$$
이므로
$$
\begin{equation}\label{eq:5} \lambda= \frac{1}{a' V^{-1}a}\end{equation}
$$
이다. 식 $\eqref{eq:3}$에 식 $\eqref{eq:5}$을 대입하면 최적 비중 $w^{\ast}$을 구할 수 있다.
$$
w^{\ast}= \frac{V^{-1}a}{a' V^{-1}a}
$$
이다. 

 $a=1_N$이면, 최적 비중은 최소분산 포트폴리오가 되고, 

$a=\mu$이면, 최적 비중은 포트폴리오의 샤프 비율을 최대화 시키는 포트폴리오가 나오게 된다.
$$
\text{Sharpe Ratio}= \frac{w' \mu}{ \sqrt{w' V w}}
$$
따라서 기대수익률이 MVO에서 매우 중요한 역할을 하게 된다.

<br>

### Ⅱ. The Condition Number

공분산 행렬의 특정 구조들은 MVO의 최적해를 unstable하게 만든다. 실무에서는 특정 공분산 행렬 뿐만 아니라 거의 모든 공분산 행렬이 MVO의 결과를 unstable하게 만든다.

이를 이해하기 위해 두 자산으로 이루어진 포트폴리오를 생각해본다. 이 때 두 자산 수익률의 상관관계를 $\rho$라고 쓰기로 한다. 두 자산의 상관관계 행렬 $C$는 다음과 같다.
$$
C= \begin{bmatrix}1 & \rho \\ \rho & 1\end{bmatrix}
$$
상관관계 행렬 $C$의 대각화 $CW=W\Lambda$는 다음과 같이 할 수 있다.

상관관계 행렬 $C$의 eigenvalue를 구해보면,
$$
\lvert{C-I\lambda}\rvert=0
$$
이므로
$$
\begin{vmatrix}1-\lambda & \rho \\ \rho & 1-\lambda \end{vmatrix}=(1-\lambda)^2 - \rho^2 =0
$$
이다. 즉, $\lambda = 1\pm\rho $이며,
$$
\Lambda= \begin{bmatrix}1+\rho & 0 \\0 & 1-\rho\end{bmatrix}
$$
이다. 상관관계 행렬 $C$의 eigenvalue들에 대해 eigenvector를 구해보면
$$
\begin{bmatrix} 1-\Lambda_{1,1} & \rho \\ \rho & 1-\Lambda_{2,2}\end{bmatrix}\begin{bmatrix}W_{1,1} & W_{1,2} \\ W_{2,1} & W_{2,2}\end{bmatrix}=\begin{bmatrix}-\rho & \rho \\ \rho & \rho\end{bmatrix}\begin{bmatrix}W_{1,1} & W_{1,2} \\ W_{2,1} & W_{2,2}\end{bmatrix}=\begin{bmatrix}0&0\\0&0\end{bmatrix}
$$
이므로
$$
\begin{bmatrix}W_{1,1} & W_{1,2} \\ W_{2,1} & w_{2,2}\end{bmatrix}=\begin{bmatrix}\frac{1}{\sqrt{2}}&\frac{1}{\sqrt{2}} \\ \frac{1}{\sqrt{2}} & -\frac{1}{\sqrt{2}}\end{bmatrix}
$$
이다.
$$
W \Lambda W' = \begin{bmatrix}\frac{1}{\sqrt{2}}&\frac{1}{\sqrt{2}} \\ \frac{1}{\sqrt{2}} & -\frac{1}{\sqrt{2}}\end{bmatrix} 
\begin{bmatrix}1+\rho & 0  \\ 0 & 1-\rho\end{bmatrix} 
\begin{bmatrix}\frac{1}{\sqrt{2}}&\frac{1}{\sqrt{2}} \\ \frac{1}{\sqrt{2}} & -\frac{1}{\sqrt{2}}\end{bmatrix}'
= \begin{bmatrix}1  & \rho  \\ \rho  & 1\end{bmatrix} =C
$$
임을 쉽게 알 수 있다.

$tr(C)=\Lambda_{1,1}+\Lambda_{2,2}=2$이므로 eigenvalue들의 합이 고정된 상황에서 $\rho$는 한 eigenvalue가 다른 eigenvalue보다 얼마나 큰지를 나타내는 수를 의미한다.

$C$의 행렬식(determinant)는 $ \lvert C \rvert = 1-\rho^2$이므로 $\rho=0$일 때 행렬식이 최대가 된다. 즉, 두 자산이 전혀 관련이 없을 때 $C$의 행렬식이 최대가 된다.

한편, $C$의 행렬식은 $\rho= \pm1$일 때 $0$으로 최소가 된다. 즉, 두 자산이 완전히 correlated되어있을 때 최소가 된다. 

상관관계 행렬 $C$의 역행렬 $C^{-1}$을 보면
$$
C^{-1} = W \Lambda^{-1} W' = \frac{1}{\lvert C\rvert} \begin{bmatrix}1 & -\rho \\ -\rho & 0\end{bmatrix}
$$
이다. 즉, $\rho$가 0에서 멀어질수록 한 eivenvalue가 다른 eigenvalue보다 커지며, $\lvert C \rvert$가 작아진다. 따라서 $\lvert C \rvert^{-1}$가 폭발하게 된다. 즉, $w^{\ast}$추정의 unstability가 커진다.

일반적으로, 공분산 구조로 야기되는 instability는 두 양극단의 eigenvalue들의 차이의 크기로 측정할 수 있다. 공분산 혹은 상관관계 행렬의 조건수(the condition number)는 eigenvalue의 최대값과 최소값의 비율의 절대값으로 정의된다. 위의 예에서는
$$
\lim\limits_{\rho \to {1^{-}}} \frac{\Lambda_{1,1}}{\Lambda_{2,2}}=+\infty
$$
이고,
$$
\lim\limits_{\rho \to -1^{+}} \frac{\Lambda_{2,2}}{\Lambda_{1,1}}=+\infty
$$
이다.

<br>

### Markowitz's Curse

상관관계 행렬 $C$는 공분산행렬 $V$를 표준화한 것이며, $w^{\ast}$를 계산할 때 사용되는 $V^{-1}$는 $C^{-1}$와 관련이 있다. 포트폴리오 내 자산들간 상관관계가 높을 때, 즉 $-1 < \rho\ll0 $이거나 $0 \ll \rho <1$일때, $C$는 높은 조건수를 갖게 되며, 공분산 행렬의 역행렬 $V^{-1}$의 크기가 폭발(explode)하게 된다. 이럴 경우 포트폴리오 최적해  $w^{\ast}$는 $V^{-1}$에 대한 함수이기 때문에 포트폴리오 최적해를 구할 때 문제가 생긴다. 즉, 마코위츠의 최적해는 상관관계 $\rho \approx 0$ 일때만 그 수치적 안정성이 담보된다.

하지만 상관관계가 $0$에 가깝다면 최적화가 그다지 필요하지 않다. 포트폴리오 최적화가 정말로 필요할 때는 $\rho \not \approx 0$일때인데, 이 때는 최적화의 결과인 $w^{\ast}$의 stability가 보장되지 못하기 못하게 된다. 이를 '마코위츠의 저주'라고 부른다. 
