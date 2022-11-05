---
title: Unsmoothing Returns 방법 (1)
date: 2022-11-05
categories:
 - Quant
tags:
 - [Time Series]
comments: True
use_math: True
---

대체자산의 성과를 감정평가(Appraisal) 기준으로 보고하는 경우 지수 수익률이 smoothed되는 경우가 많은데, 이를 Unsmoothing하는 기법을 정리한다.

***

<br>

$r_t^*$를 $t$시점에 보고된 감정평가 기준의 수익률이라고 하자. 감정평가 기준 수익률 $r_t^{*}$이 $AR(1)$의 특성을 가진다고 가정하자. 즉,

 $\begin{equation} r_t^{*} = c+ \phi r_{t-1}^{*}+\epsilon_t \end{equation}$

이며 여기서 $\phi \in (0, 1)$인 상수이고, $\epsilon_t \:\sim \,  \text{i.i.d.} \, \,N(0, \sigma_{\epsilon}^2)$인 노이즈다. 

$r_t$를 감정평가 기준이 아닌 관측되지 않는 실제 수익률이라고 할 때, $r_t^*$가 이전 감정평가 기준 수익률 $r_{t-1}^*$의 정보와 실제 수익률 $r_t$의 가중평균이 된다고 가정하자. 즉,

$\begin{equation} r_t^* = \phi r_{t-1}^*+(1-\phi)r_t=\phi r_{t-1}^{*}+(c+\epsilon_t) \end{equation}$

라고 가정한다. 식(1)과 식(2)를 관측되지 않는 실제 수익률 $r_t$에 대해 풀면

$\begin{equation} r_t= \frac{1}{1-\phi}r_t^{*}-\frac{\phi}{1-\phi}r_{t-1}^* \end{equation}$

임을 알 수 있다. 즉, 관측된 감정평가 기준 수익률 $r_{t}^{*}$을 관측되지 않는 실제 수익률 $r_t$로 바꿀 수 있는 것이다.

<br>

일반성을 잃지않고 $c=0$을 가정한다. 식(1)을 이용해 감정평가 기준 수익률 $r_t^{*}$의 변동성 $\gamma_0$을 계산해보면

$\gamma_0=E\left[ {r_t^*}^2 \right]=E\left[ (\phi r_{t-1}^{*}+\epsilon_t)^2 \right]=E\left[ \phi^2 {r_{t-1}^{*}}^2 +{\epsilon_t}^2+2\phi r_{t-1}^{*} \epsilon_t \right]= \phi^2 \gamma_0+\sigma_{\epsilon}^2$

이므로

$\begin{equation}\gamma_0 = \frac{\sigma_{\epsilon}^2}{1-\phi^2}\end{equation}$

임을 알 수 있다. 

한편, 감정평가 기준 수익률 $r_t^{*}$과 $r_{t-1}^*$의 상관관계 $\gamma_1$는

$\begin{equation}\gamma_1=E\left[  r_{t-1}^{*}(\phi r_{t-1}^{*}+\epsilon_t) \right]=\phi \gamma_0\end{equation}$

이다.

식 (3)과 식 (5)를 이용해 관측되지 않는 실제 수익률 $r_t$의 변동성 $var(r_t)$을 계산해보면 $\phi \in (0, 1)$이므로

$\begin{split} var(r_t) &=\frac{1}{(1-\phi)^2} \gamma_0 + \frac{\phi^2}{(1-\phi)^2} \gamma_0 - 2 \frac{\phi}{(1-\phi)^2} \gamma_1 \\&= \frac{1}{(1-\phi)^2} (\gamma_0 + \phi^2 \gamma_0 -2 \phi^2 \gamma_0 ) \\&= \frac{1}{(1-\phi)^2} \gamma_0 (1-\phi^2 ) \\&= \frac{1+\phi}{1-\phi} \gamma_0 \\& > \gamma_0 =var(r_t^*)\end{split}$

이다. 즉, 관측되지 않는 실제 수익률 $r_t$의 변동성이 관측된 감정평가 기준 수익률 $r_t^*$의 변동성보다 크다.









