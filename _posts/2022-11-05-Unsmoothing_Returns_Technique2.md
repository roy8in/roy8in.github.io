---
title: Unsmoothing Returns 방법 (2)
date: 2022-11-05
categories:
 - Quant
tags:
 - [Time Series]
comments: True
use_math: True
---

대체자산의 성과를 감정평가(Appraisal) 기준으로 보고하는 경우 지수 수익률이 smoothed되는 경우가 많은데, 이를 Unsmoothing하는 기법을 다룬 Niels Pedersen, Sebastien Page, Fei He의 자료 에서 필요한 내용을 정리한다.

***

시가평가 데이터가 부재한 관계로 대체투자는 낮은 변동성과 전통자산과의 훌륭한 분산효과를 제공한다는 오해를 줄 수 있다. 이는 사모 자산의 수익률 지수가 인위적으로 평탄화(smoothed) 되기 때문이다. 페이퍼에서 소개한 Smoothed된 수익률을 Unsmoothing 하는 방법을 정리한다.

<br>

한 자산의 수익률은 리스크 팩터 수익률의 선형 결합(linear combination)으로 표현할 수 있다고 가정한다.

$$
\begin{equation}r_t = \alpha+\sum\limits_{i=1}^{N} \beta_i f_{i, t}+\epsilon_t\end{equation}
$$
여기서

&emsp;$r_t$: 자산의 수익률

&emsp;$\alpha$: 상수

&emsp;$\beta_i$: 자산의 $i$번째 팩터에 대한 노출도

&emsp;$f_i$: $i$번째 팩터의 수익률

&emsp;$\epsilon_t$: 오차항

이다. 개별 대체자산의 관측된 smoothed 수익률은 관측되지 않은 최근 실제 수익률들의 가중평균이라고 가정한다. 즉,
$$
\begin{equation}r_{obs,t} = \sum\limits_{j=0}^Q w_j r_{t-j}\end{equation}
$$
여기서

&emsp;$r_{obs, j}$: 관측된 지수 수익률

&emsp;$Q$: lag 수

&emsp;$r_t$: 관측되지 않는 실제 수익률

&emsp;$w_j$: 과거의 관측되지 않는 실제 투자 성과가 현재 관측된, smoothed 수익률에 영향을 미치는 정도

이다. 즉, 이 모델은 관측된 수익률 $r_{obs}$이 과거의 투자 수익률 $r$의 이동평균이라고 가정하는 것이다. 

<br>

식 (1)을 활용해 식 (2)를 다시 표현하면
$$
\begin{equation}\begin{split} r_{obs,t} &= \sum\limits_{j=0}^Q w_j r_{t-j} \\&=  \sum\limits _{j=0}^Q w_j \left( \alpha + \sum\limits_{i=1}^N \beta_i f_{i, t-j} +\epsilon_{t-j} \right) \\&= \alpha \sum\limits_{j=0}^Q w_j  + \sum\limits_{i=1} ^N \beta_i \sum\limits_{j=0} ^Q w_j f_{i, t-j} + \sum\limits _{j=0} ^Q w_j \epsilon_{t-j}\end{split}\end{equation}
$$
이며, 여기서 $N$은 리스크 팩터의 개수이다. 

- $\sum\limits_{j=0}^Q w_{j} =1$이라 가정하고

- $X_{i,t}:= \sum\limits_{j=0}^Q w_j f_{i, t-j}$를 $i$번째 팩터 수익률의 이동평균 수익률

- $\eta_t:= \sum\limits_{j=0}^Q w_{j} \epsilon_{t-j}$를 오차항의 이동평균 오차항

이라고 표기하면 식 (1)과 식 (3)은 다음과 같이 쓸 수 있다.
$$
r_{obs,t}= \alpha + \sum\limits_{i=1}^N \beta_i X_{i, t} + \eta_t
$$
즉, 관측된 대체자산의 수익률을 팩터 수익률의 이동평균 수익률 $ \left\\{ X_{i, t} \right\\}_{i=1}^N $의 조합으로 표현하는 것이다. 

<br>

위에서 설명한 방법론을 정리하면 크게 두 단계의 과정이 필요하다.

1. 관측된 smoothed 자산 수익률을 이용해 $w_j$를 추정한다. 각 자산별로 적절한 이동평균의 기간을 결정하는 lag parameter $Q$는 통계적 유의성에 따라 정한다.
2. 이렇게 추정한 $\{w_j\}$를 이용해 $X_{i,t}$를 만들고, 팩터 노출도(loadings) $\beta_i$를 추정한다. 이때 OLS 등을 사용할 수 있다.

<br>

이 보고서에서는 대체투자를 세 그룹으로 나누었다.

1. 사모주식과 벤처캐피탈
2. 실물 자산: 부동산, 인프라(Infrastructure), 농지(Farmland), 삼림(Timberland), 천연자원
3. 헤지펀드 및 이색 베타 전략(exotic beta)

각 대체자산에 대한 Proxy지수 및 지수의 자기상관성, 적절한 이동평균 기간 Q 및 smoothed return에 따른 변동성 감소 정도는 아래와 같다.

|         Asset-Class         |                      Proxy                       | Autocorrelation Measure | Q (Quarters) | Volatility Difference |
| :-------------------------: | :----------------------------------------------: | :---------------------: | :----------: | :-------------------: |
|       Private Equity        |  Cambridge Associates U.S. Private Equity Index  |           55%           |      5       |          11%          |
|       Venture Capital       | Cambridge Associates U.S. Venture Capital Index  |           65%           |      5       |          27%          |
|   Infrastructure (listed)   | UBS Global Infrastructure and Utilities (listed) |           16%           |      1       |          2%           |
|          Farmland           |              NCREIF Farmland Index               |           61%           |      8       |          7%           |
|         Timberland          |             NCREIF Timberland Index              |           54%           |      8       |          8%           |
|   Real Estate (Unlevered)   |              NCREIF Property Index               |           78%           |      6       |          8%           |
|     Real Estate (Core)      |                NCREIF Core Index                 |           80%           |      6       |          10%          |
|  Real Estate (Value Added)  |             NCREIF Value Added Index             |           76%           |      6       |          12%          |
| Real Estate (Opportunistic) |            NCREIF Opportunistic Index            |           75%           |      6       |          19%          |
|         Hedge funds         |               HFRI Composite Index               |           29%           |      ?       |          3%           |
|          Equities           |                      S&P100                      |           6%            |      1       |          1%           |
|      Government bonds       |   Bloomberg Barclays US Government Bond Index    |           15%           |      1       |          1%           |

<br>

***

자료: Niels Pedersen, Sebastien Page, Fei He - Asset Allocation: Risk Models for Alternative Investments (2014)





