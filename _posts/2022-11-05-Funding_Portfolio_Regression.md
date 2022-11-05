---
title: Funding Portfolio
date: 2022-11-05
categories:
 - Finance
tags:
 - [Portfolio]
comments: True
use_math: True
---

Andrew Ang at el. 의 《Review of the Active Management of the Norwegian Government Pension Fund Global》 자료를 참고하여 대체자산의 수익률을 전통자산들의 수익률로 표현하는 방법 중 한 가지를 정리한다.

***

Unsmoothing 기법을 이용하여 추정한 실제 수익률을 $r_t^{\rm{true}}$라고 하자. $r_t$를 주식 수익률 ($r_t^{\rm{stock}}$) 및 채권 수익률($r_t^{\rm{bond}}$)과의 회귀분석을 통해 팩터 노출도를 확인한다.

자료에서는 분석기간 중 $0.78$의 자기상관성을 갖는 NCREIF 부동산 지수의 수익률을 주식과 채권의 수익률로 회귀분석한 사례를 담았다. 회귀분석 결과는 다음과 같다.
$$
\begin{equation} r_t ^{\rm{true}}=-0.50 + 0.49 r_t ^{\rm{stock}}+0.51 r_t^{\rm{bond}}+\epsilon_t \end{equation}
$$
식 (1)은 부동산에 ＄1.0만큼 투자하는 것은 ＄0.49의 주식과 ＄0.51의 채권을 사용하는 기회비용이 발생함을 의미한다. TPA 관점에서 생각해보면 부동산에 ＄1.0 투자하기 위해＄0.49의 주식을 매도하고 ＄0.51의 채권을 매도하여 재원을 조달하는 개념이다. 상수항 $-0.5$는 분석기간 동안 NCREIF 부동산 지수가 주식 및 채권의 조합보다 성과가 부진했음을 의미한다.

회귀분석결과 $R^2=0.24$로 나타났다. 이는 공모자산의 패시브 운용으로는 만들어낼 수 없는 수익 부분이 상당히 많다는 것을 의미한다. NCREIF로 측정한 평균적인 부동산 투자의 성과가 주식과 채권의 혼합보다 부진했던 것은 부동산 투자를 성공적으로 수행하기 위해서는 많은 스킬과 투자 집행이 전제되어야 함을 의미한다.

위에서 설명한 회귀분석은 매우 단순한 형태의 분석일 뿐이며, 대체자산의 수익률의 데이터가 부족하다면 수행하기 어려운 단점이 있다. 

참고로 앞에서는 Smoothed되어 있는 NCREIF 지수를 Unsmoothing 한 뒤에 주식 및 채권 수익률과 회귀분석을 수행하였다. 반대로, Smoothed되어 있는 NCREIF 지수를 그대로 사용하고, 주식 및 채권 수익률을 Smoothing 한 뒤에 회귀분석을 수행할 수도 있다. 









