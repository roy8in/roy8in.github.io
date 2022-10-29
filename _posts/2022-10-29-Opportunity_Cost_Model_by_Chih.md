---
title: Reference Portfolio & Factor Investing (Sung Cheng Chih)
date: 2022-10-29
categories:
 - Portfolio
tags:
 - [Opportunity Cost Model, Reference Portfolio]
comments: True
use_math: True
---

SUNG Cheng Chih의 《Reference Portfolio & Factor Investing: Advances in Global Investment Management》 발표 자료에서 필요한 부분을 정리

***

### Part 1: Motivation

David Denison, John Ilkiw, Don Raymond, Mark Wiseman 주도로 캐나다 CPPIB에서 2000년대 중반 'Total Portfolio Approach(TPA)' 체계에서 기회비용모델이 도입되었고, 이후 싱가포르 GIC와 뉴질랜드 NZ Super에서 각 연기금 상황에 맞게 조정하여 도입하였다.

공모(Public) 시장에서 거래되는 유동성 높은 자산들의 수익률과 위험은 사모(Private) 시장의 대체 자산의 수익률과 위험보다 더 이해하기 쉽고, 수익률을 복제하기도 쉽다.

대체 투자의 위험은 공모 시장 투자와 일정 겹치는 부분이 있다. 그 정도는 대체투자의 성격에 따라 다르다. 그러나 실제 대체 투자의 성과에는 서로 상관성이 낮은 공모 시장의 체계적(Systematic) 수익률과 대체 투자 자체 특성의(Idiosyncratic) 수익률이 모두 작용한다.

기준 포트폴리오(Reference Portfolio)는 유동성이 높은 자산으로 구성되며, 공모 시장 및 사모 시장의 다양한 액티브 투자에 대한 기회 비용을 측정할 수 있게 한다.

실제 포트폴리오의 총 위험은 기준 포트폴리오에 비해 확대된 액티브 리스크 배분에 의해 관리된다.

<br><br>

### Part 2: Theory

기회비용모델 기본 구성

<span style="color:grey"><b>Reference Universe, $\Pi$</b></span>: 유동성이 높고 공모 시장에서 거래되는 자산으로 구성된 자산(군) 유니버스이며, 보통 국채 및 상장 주식으로 구성된다. 

예, $\Pi$ = {글로벌 주식, 글로벌 채권}

<br>

<b>Reference Portfolio, $B$</b>: 주어진 제약조건 하에서 Reference Universe $\Pi$ 내 자산들로 구축하는 포트폴리오로, 현실적으로 투자할 수 있는 저비용 패시브 형식의 최적 포트폴리오를 의미한다.

예, $B$ = 글로벌 주식 80% + 글로벌 채권 20% 

<br>

<span style="color:green"><b>Funding Benchmark, $B_i$</b></span>: 개별 투자 전략의 수익률을 $R_i$라고 했을 떄, 이 개별 투자 전략은 Reference Universe $\Pi$ 자산들의 조합인 Fundinb Benchmark $B_i$을 기준으로 관린된다. 이는 해당 전략을 투자함으로써 발생하는 기회비용의 Proxy로 작용하고, 위험 및 성과평가의 기준이 된다. 

<br>

<span style="color:grey"><b>Return Projection, $P_i$</b></span>: 개별 투자 전략의 수익률을 $R_i$라고 했을 때, $R_i$를 Reference Universe $\Pi$에 투영하면, 

$R_i = P_i + r_i = B_i + (P_i - B_i) + r_i$

이다. 여기서 $P_i$를 Reurn Projection라고 한다. 대체자산의 경우 <span style="color:green">Funding Benchmark $B_i$</span>는 일반적으로 회귀분석을 통해 결정되며, 암묵적으로 $B_i \approx P_i$임을 가정한다.

<br>

<span style="color:navy"><b>Residual Return, $r_i$</b></span>: 개별 투자 전략의 수익률 $R_i$와 Return Projection $P_i$의 차이로 표현할 수 있으며($r_i = R_i - P_i$) Reference Univserse의 자산 수익률과 관련이 없는(Uncorrelated) 수익률이다. 즉, $r_i \perp \Pi$ 이다. $ B_i \approx P_i$임을 가정할 경우 <span style="color:navy">Residual Return, $r_i$</span> $\approx R_i - B_i$을 가정하게 된다.

<br>

![image](/assets/images/Visualisation of Opportunity Cost Model.png)

<span style="color:red">Strategic return $R_i$</span>를 <span style="color:grey">Reference Universe $\Pi$</span> 세계의 입장에서 보면, 즉 투영하면 <span style="color:grey">Return Projection $P_i$</span>가 나와야 하는데 계산해보니 Reference Universe의 조합으로는 <span style="color:green">Funding Benchmark $B_i$</span>가 나왔다. 이 때 이 차이 $P_i - B_i$는 대체자산 수익률을 공모자산으로 표현하는 과정에서 발생하는 오차, 오류와 비슷한 개념이며, 기회비용 모델의 한계를 의미하기도 한다. $P_i$와 $B_i$의 차이가 작을수록 좋은 기회비용 모델이라고 할 수 있다.

<span style="color:navy">Residual Return $r_i$</span>는 대체자산 고유의 수익률로써 <span style="color:grey">Return Projection $P_i$</span> 및 $P_i - B_i$ 에 영향을 받지 않는 것(Orthogonal)을 가정한다. <span style="color:navy">Residual Return $r_i$</span>은  GP 매니저 역량과 좋은 투자기회 혹은 정보 비대칭 등에 기인하며, 이는 유동성 높은 공모시장에서 거래가능하지 않기 때문이다. 이것이 대체자산을 포트폴리오에 포함해야하는 이유라고 볼 수 있는데, <span style="color:navy">Residual Return $r_i$</span>은 비유동성 프리미엄 등 초과수익률을 제공하며 공모시장과 낮은 상관관계를 만들기 때문이다.

<br><br>

### Part 3: Practice

이론적으로 기회비용 모델의 액티브 리스크는 아래와 같은 세 단계를 거쳐 추정된다.

1. 각 전략의 projected return $P_i$를 추정한다.
2. liquid 부문의 추적오차(Tracking Error, TE)를 계산한다. $Var\left[ \sum_i w_i (P_i - B_i) \right]$
3. Illiquid 부문의 추적오차를 계산한다. $Var \left[ \sum_i r_i\right]$

만약 $P_i \approx B_i$를 가정할 경우 liquid 부문 추적오차는 무시한다.

