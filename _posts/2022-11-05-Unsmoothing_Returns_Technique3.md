---
title: Unsmoothing Returns 방법 (3)
date: 2022-11-05
categories:
 - Quant
tags:
 - [Time Series]
comments: True
use_math: True
---

대체자산의 성과를 감정평가(Appraisal) 기준으로 보고하는 경우 지수 수익률이 smoothed되는 경우가 많은데, 이를 Unsmoothing하는 기법을 다룬 Alexander Rudin, Jason Mao, Nan R. Zhang, Anne-Marie Fink의 자료에서 필요한 내용을 정리한다.

***

<br>

Pedersen, Page, and He (2014)의 방법론은  $w_j$와 $\beta_i$를 두 단계에 걸쳐 계산한다는 아쉬움이 있다. 각각을 추정할 때 회귀분석을 수행해야 하는데, 두 번의 회귀분석 과정에서 발생하는 추정 오차(estimation errors)가 누적될 수 있기 때문이다. 따라서 회귀분석을 한 번만 수행하는 방법을 소개한다.

<br>

개별 대체자산의 관측된 smoothed 수익률은 관측되지 않은 최근 실제 수익률들의 가중평균이라고 가정하는 것은 동일하다. 즉,
$$
\begin{equation}r_{obs,t} = \sum\limits_j^Q w_j r_{t-j}\end{equation}
$$
여기서

&emsp;$r_{obs, j}$: 관측된 지수 수익률

&emsp;$Q$: lag 수

&emsp;$r_t$: 관측되지 않는 실제 수익률

&emsp;$w_j$: 과거의 관측되지 않는 실제 투자 성과가 현재 관측된, smoothed 수익률에 영향을 미치는 정도

이다. 즉, 이 모델은 관측된 수익률 $r_{obs}$이 과거의 투자 수익률 $r$의 이동평균이라고 가정하는 것이다. 

하지만 식 (1)의 표현을 다음과 같이 조금 다르게 표현해본다.
$$
\begin{equation}r_{obs,t} = \theta_0 r_t + \sum\limits_{j=1}^Q \theta_j r_{obs, t-j}\end{equation}
$$
$\theta_j$를 알고 있을 때 $w_j$를 계산할 수 있고, 이것의 역도 성립하므로 식(2)와 식(1)은 동일한 표현이다.

한 자산의 수익률은 리스크 팩터 수익률의 선형 결합(linear combination)으로 표현할 수 있다고 가정한다.
$$
\begin{equation}r_t = \alpha+\sum\limits_i^N \beta_i f_{i, t}+\epsilon_t\end{equation}
$$
여기서

&emsp;$r_t$: 자산의 수익률

&emsp;$\alpha$: 상수

&emsp;$\beta_i$: 자산의 $i$번째 팩터에 대한 노출도

&emsp;$f_i$: $i$번째 팩터의 수익률

&emsp;$\epsilon_t$: 오차항

이다. $\sum\limits_{j=0}^{Q} \theta_j =1$이므로, 식 (3)를 활용하여 식 (2)를 다시 표현하면 
$$
\begin{equation}\begin{split}r_{obj,t}&=\theta_0 \left(\alpha+\sum\limits_{i=1}^N \beta_i f_{i, t} +\epsilon_t\right)+\sum\limits_{j=1}^{Q}\theta_j r_{obs, t-j}\\&= \alpha'+\left( 1-\sum\limits_{j=1}^{Q}\theta_j \right)\sum\limits_{i=1}^{N}\beta_i f_{i, t}+\sum\limits_{j=1}^Q \theta_j r_{obs, t-j}+\epsilon'_t\end{split}\end{equation}
$$
으로 쓸 수 있다. 식 (4)를 통해 관측된 수익률 $r_{obs, t}$와 팩터 수익률 $f_{i, t}$들로부터 smoothing parameters $\theta_j$와 팩터 노출도 $\beta_i$를 한 번의 회귀분석을 통해 구할 수 있다.

<br>

이렇게 Unsmoothing 하는 방법에는 단점이 있는데

1. lag parameter $Q$를 설정하는 어려움
2. 사용하는 proxy 지수와 기관이 투자하는 대체자산의 성격이 다를 수 있음

등이다.

<br>

***

자료: Alexander Rudin, Jason Mao, Nan R. Zhang, and Anne-Marie Fink - Fitting Private Equity into the Total Portfolio Framework (2019)





