---
title: Smoothing 기간 계산 방법
date: 2022-11-05
categories:
 - Quant
tags:
 - [Time Series]
comments: True
use_math: True
---

Andrew Ang at el. 의 《Review of the Active Management of the Norwegian Government Pension Fund Global》 자료를 참고하여 수익률을 Smoothing 하는 기간 결정 방법을 정리한다.

***

<br>

$X_t$가 $AR(1)$ 프로세스, 즉

$\begin{equation} X_t = c + \phi X_{t-1} + \epsilon_t \end{equation}$

라고 가정하자. 여기서 $c$는 상수, $\epsilon_t \sim N(0, \sigma_{\epsilon}^2)$를 따르는 노이즈이다. 모든 $t$에 대해서 $E[X_t]=\mu$(상수)라고 가정하면

$\begin{equation} \mu = E[c+\phi X_{t-1}+\epsilon_t]=c+\phi \mu\end{equation}$

임을 알 수 있다.

$X_t$가 평균 $\mu$로부터 떨어져있는 정도를 보면

$\begin{equation}\begin{split} X_t - \mu &= c + \phi X_{t-1} + \epsilon_t - \mu \\&= \phi X_{t-1}+\epsilon_t - \phi \mu \\&= \phi(X_{t-1}-\mu) + \epsilon_t \end{split}\end{equation}$

이다. $X_t - \mu$를 $\tilde{X}_{t}$라고 쓰면 $\tilde{X}_t=\phi \tilde{X}_{t-1}+\epsilon_t$이다. (따라서 일반성을 잃지 않고 $AR(1)$ 프로세스 $X_t$의 평균을 0으로, 즉 $c=0$으로 가정해도 무방하다. 따라서 번거로움을 피하기 위해 아래에서는 tilde( $\tilde{}$ ) 를 생략한다.)

<br>

 $\begin{equation}{X}_{t+1}=\phi {X}_{t}+\epsilon_{t+1}\end{equation}$

이고,

$\begin{equation} {X}_{t+2} = \phi {X}_{t+1}+\epsilon_{t+2}=\phi^2 {X}_t+\phi \epsilon_{t+1} + \epsilon_{t+2} \end{equation}$

이므로 임의의 양의 정수 $h$에 대해서

$\begin{equation} {X}_{t+h} = \phi^h {X}_t + \sum\limits _{i=0} ^ {h-1} \phi^i \epsilon_{t+h-i}  \end{equation}$

임을 알 수 있다. ${X}_{t}$를 알고 있는 상황에서 식 (6) 양변에 조건부 기댓값을 취하면, $E(\epsilon_t)=0$ 이므로,

$\begin{equation}E[{X}_{t+h} | {X}_t]  = \phi^h X_t \end{equation}$

이 된다.

만약 특정 시점 $t$에 충격이 발생하였고, 그 충격의 영향력의 $75$%가 사라지는, 즉 충격의 $25$%만 남는 데 까지 걸리는 평균적인 시간 $h$를 구한다면

 $\begin{equation} E[X_{t+h}] = \phi^h X_t = 0.25 X_t \end{equation}$

이므 로 $h=\frac{\log0.25}{\log\phi}$이 된다. 만약 $X_t$의 자기상관계수 $\phi$가 $0.78$이라면 이 때 $h$는 $6 \left(\approx \frac{\log 0.25}{ \log 0.78} \right)$으로 가정할 수 있다.

