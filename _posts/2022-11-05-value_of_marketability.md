---
title: 비유동성 프리미엄 추정 방법
date: 2022-11-04
categories:
 - Quant
tags:
 - [Option, Illiquidity Premium]
comments: True
use_math: True
---

룩백(Lookback) 옵션 가격을 활용하여 비유동성 프리미엄의 상한을 추정하는 방법론을 담은 Francis A. Longstaff의 자료를 정리한다.

***

완벽한 마켓 타이밍 능력을 보유한 투자자가 있음을 가정한다. 그러나 이 투자자는 $T$기간 동안 보유하고 있는 자산을 매도할 수 없다. 이 투자자에게 매도 제약의 가치는 어떻게 추정할 수 있을까?

만약 매도 제한이 없었다면 투자자는 $T$시점까지의 가격 중 가장 높은 가격에 자산을 매도할 수 있었을 것이고, 그 가격에 따라 매도 제약의 가치가 결정된다고 볼 수 있다.

$M_T$가 투자자가 완벽한 마켓 타이밍 능력을 발휘하여 $T$시점까지의 고점에서 자산을 매도하고, 매도한 이후에는 무위험 자산에 투자했을 때 시점 $T$에서의 가치라고 하면

$$
M_T := \max\limits_{0 \le \tau \le T} e^{r(T-\tau)}V_{\tau}
$$
라고 쓸 수 있다. 여기서 $\tau$는 $0$부터 $T$까지의 기간 중 자산 가격이 고점인 시점을 의미한다.

완벽한 마켓 타이밍 능력을 가진 투자자에게 자산 $V$의 $T$ 시점까지의 매도 제약의 가치를 $F(V, T)$라고 쓴다면, 이는 $\left(M_T-V_T \right)$의 기대값의 현재가치라고 할 수 있다. 즉,

$$
F(V,T)=e^{-rT} E[M_T-V_T]=e^{-rT} E[M_t]-e^{-rt}E[V_T]
$$
이다.

자산의 현재 시점에서의 가격 $V$가 다음과 같은 확률 과정을 따른다고 가정한다.

$$
dV= \mu V dt + \sigma V dZ 
$$
여기서 $\mu$는 평균 수익률을 나타내는 상수이고, $\sigma$는 변동성을 의미하는 상수이며, $Z$는 standard Wiener Process이다. 또한 무위험 수익률 $r$이 상수라고 가정한다. Brownian motion의 최대값의 밀도 함수를 [활용](https://personal.ntu.edu.sg/nprivault/MA5182/maximum-brownian-motion.pdf)하면

$$
F(V,T)=V \left(2+ \frac{\sigma^2 T}{2}\right)N\left(\frac{\sqrt{\sigma^2 T}}{2}\right)+V \sqrt{\frac{\sigma^2 T}{2 \pi}} \text{exp}\left({\frac{-\sigma^2T}{8}}\right)-V
$$
임을 알 수 있다. 여기서 $N(\cdot)$은 정규분포의 누적분포함수(cdf)이다. 매도 제약의 가치를 비유동성 프리미엄이라고 한다면, 비유동성 프리미엄은 자산의 현재 가치 $V$와 변동성 $\sigma$ 및 매도제한기간 $T$에 비례함을 알 수 있다.

***

자료: Francis A. Longstaff - How much Can Marketability Affect Security Values? (1995)





