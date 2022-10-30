---
title: Estimating Private Equity Returns from Limited Partner Cash Flows (Andrew Ang at el.)
date: 2022-10-30
categories:
 - Portfolio
tags:
 - [Opportunity Cost Model, Reference Portfolio]
comments: True
use_math: True
---

Andrew Ang, Bingxu Chen, Ludovic Phalippou, William N. Goetzmann이 작성한 《Estimating Private Equity Returns from Limited Partenr Cash Flows》 자료(2013)에서 필요한 부분을 정리하고, 내가 생각하는 방법론의 장점과 단점을 정리

***

### Introduction

<br>

사모 주식의 할인율(discount rates)을 계산할 때 순현재가치(Net Present Value, NPV) 프레임워크를 활용한다. 할인율이 정확하고 투자 수익률의 적절한 대표값이라 가정할 때, 펀드에 지급한 출자요구(Capital Calls)의 현재가치는 펀드의 성과배분(Distributions)의 현재가치와 일치해야 한다. 모든 기간과 모든 펀드를 대상으로 Limited Partner(LP) 현금흐름의 NPV가 0이 되는 것이다.

<br>

연구 결과 사모 주식의 수익률은 일반적인 산업 지수보다 더 큰 변동성을 보였다. 

1. Buyout 펀드들의 현금흐름 기반 수익률 시계열은 연간 25%의 변동성을 보였으며, 이는 Cambridge Associates buyout index의 연 11%의 변동성보다 훨씬 크다. 
2. NCREIF 부동산 지수의 연 변동성은 고작 5%밖에 되지 않지만 우리들의 접근법으로 계산한 사모 부동산 수익률의 연간 변동성은 19%로 계산되었으며, 이는 공모시장에서 거래되는 상장 REITS와 더 유사한 수준이다. 
3. Venture Capital의 변동성은 우리의 방법으로 35%로  계산되었고, 이는 Cambridge Associates의 Venture Capital Index의 27%와 유사했다.

또한 사모 주식의 수익률 시계열은 산업에서 사용하는 지수보다 약한 자기상관성을 보였다.

<br>

이 연구는 사모 주식의 수익률을 체계적(systematic) 요소와 이질적(idiosyncratic) 요소로 구분했다. 체계적 요소는 주대형주, 소형주, 가치주 및 유동성 요소를 포함한 일반적인 주식 벤치마크와 관련이 있다. 대부분의 체계적 변수는 시장 팩터이며, 사모 주식의 수익률은 이 주식시장 팩터에 1 이상의 팩터 노출도(beta loading)를 갖고 있는 것으로 나타났다.

사모 주식 수익률의 나머지 이질적인 부분을 "사모 주식 프리미엄(priave equity premium)"으로 부르기로 한다. 이는 시간에 따라 변하는 사모 주식의 알파라고 해석할 수 있다. 

<br>

<br>

### Methodology

<br>

이 추정 방법론은 서로 다른 펀드들에 대해 투자자(LP)가 지불하고 수령한 현금흐름 데이터만 필요하다.  개별 펀드의 시작과 청산 시점이 모두 다르기 때문에 직접 관찰되지 않는 숨어있는 할인율의 시계열을 추정할 수 있게 된다.

$N$개의 서로 다른 사모 주식 펀드에 각각 $i$를 indexing 한다. 즉, $i\in \{1, 2, \cdots, N \}$이다. 투자와 관련된 현금흐름 $I_{it}$는 시점 $t$에 펀드 $i$에 일어난 투자이며, 분배금 $D_{it}$는 시점 $t$에 LP가 펀드 $i$로 부터 받은 성과배분을 뜻한다. 모델이 적절히 설정되었다면, 두 현금흐름의 현재가치는 다음과 같은 조건을 만족해야 한다.

$E \left[ \sum_i I_{it} \delta_{it} \right]= E \left[ \sum_i D_{it} \delta_{it} \right]$

여기서 $\delta_{it}$는 펀드 $i$에 대해 시점 $t$에서 적용되는 현재가치를 계산해주는 요소이며, 다음과 같이 재귀적(recursively) 방법으로 표현이 가능하다.
$\delta_{it} = \delta_{i, t-1} (1+g_t)^{-1}$
이 때 펀드가 시작된 시점 $\tau$에서  $\delta_{i, \tau}=1$ 이며, $g_t$는 사모 주식의 $t$ 시점의 수익률이다. 데이터 주기는 한 개 분기로 설정했다.

<br>

예) $t=0$부터 $t=4$ 사이에 존재했던 네 개 펀드를 사용한 경우

<table style="text-align:right">
    <thead>
	    <tr>
            <th style="text-align:center">Times</th>
            <th style="text-align:center">PE return (g)</th>
            <th style="text-align:center">Fund 1</th>
            <th style="text-align:center">Fund 2</th>
            <th style="text-align:center">Fund 3</th>
            <th style="text-align:center">Fund 4</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <th style="text-align:center">0</th>
            <td></td>
            <td>-100</td>
            <td>-100</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <th style="text-align:center">1</th>
            <td>5.9%</td>
            <td>+53.0</td>
            <td>0.0</td>
            <td>-100.0</td>
            <td>-100.0</td>
        </tr>
        <tr>
            <th style="text-align:center">2</th>
            <td>17.5%</td>
            <td>+31.1</td>
            <td>+124.4</td>
            <td>+117.5</td>
            <td>0.0</td>
        </tr>
        <tr>
            <th style="text-align:center">3</th>
            <td>-4.8%</td>
            <td>+29.6</td>
            <td></td>
            <td>-100.0</td>
            <td>+111.9</td>
        </tr>
        <tr>
            <th style="text-align:center">4</th>
            <td>31.7%</td>
            <td></td>
            <td></td>
            <td>+131.7</td>
            <td></td>
        </tr>
	</tbody>	
</table>

<br>

펀드가 정확히 프라이싱 되었다고 가정할 경우, 펀드 투자는 NPV 조건을 만족해야만 한다. 즉, $PV(I) = PV(D)$ 이다.

네 펀드에 대한 NPV 조건은 다음과 같으며

* Fund 1: $100 = {\frac{53}{(1+g_1)}}+\frac{31.1}{(1+g_1)(1+g_2)}+\frac{29.6}{(1+g_1)(1+g_2)(1+g_3)}$
* Fund 2: $100 = \frac{124}{(1+g_1)(1+g_2)}$
* Fund 3: $100 + \frac{100}{(1+g_1)(1+g_2)} = \frac{117.5}{(1+g_2)}+\frac{131.7}{(1+g_2)(1+g_3)(1+g_4)}$
* Fund 4: $100 = \frac{111.9}{(1+g_2)(1+g_3)}$

을 함께 풀면 $\{g_1, g_2, g_3, g_4\}$를 계산할 수 있다.

<br>

<br>

시점 $t$에서 $g_t$가 사모 주식의 할인율이라고 할 때, 무위험 수익률 $r_t^f$ 대비 초과 할인율(Excess discounted rate) $g_t^e$를 계산할 수 있다.

$g_t = g_t^e + f_t^f$

사모 주식의 할인율 $g_t$는 사모 주식 데이터를 통해서는 직접 관찰할 수 없는 수익률이다 사모주식의 성과가 $J$개의 거래 가능하며, 공모 시장에서 관측 가능한 공통의 팩터

${\mathbf{F_t}} = \left[F_{1, t}, \cdots, F_{J, t}\right]$

에 의해 결정된다고 가정한다. 이 팩터는 주식시장이 될 수도 있고($J=1$), Fama와 French의 3팩터가 될 수도 있고($J=3$), Pastor와 Stambaugh가 제안한 것처럼 유동성 요소를 추가($J=4$)할 수도 있다.

추가로 자산 고유의 잠재 요소(latent factor)인 $f_t$가 존재한다고 가정한다.

이를 종합하면 사모주식의 리스크 프리미엄($g_t^e$)은 다음과 같이 표현할 수 있다.

$g_t^e = \alpha + {\mathbf{\beta}}^{T}{\mathbf{F_t}}+f_t$

여기서 $\bf{\beta}$는 공통의 팩터 $\mathbf{F_t}$의 계수(loadings, betas) 벡터를 뜻한다.

${\bf{\beta}}=\begin{bmatrix}\beta_1 \\ \vdots \\ \beta_J\end{bmatrix}$

연구에 따르면 사모 주식 수익률 팩터 $f_t$는 1차 자귀회귀모형 $AR(1)$ 유형인 것을 알 수 있다.

$f_t = \phi f_{t-1}+ \sigma_f \epsilon_t$

연구에 따르면 $f_t$의 평균은 0이기 때문에 위 식에서 $\alpha$는 체계적 및 유동성 요소 대비 사모주식의 평균적인 초과성과를 의미한다.

$E\left[g_t^e\right] = E \left[\alpha +{\mathbf{\beta}}^{T}{\mathbf{F_t}}\right]=\alpha + {\mathbf{\beta}}^{T}E\left[{\mathbf{F_t}}\right]+E\left[f_t\right]=\alpha + {\mathbf{\beta}}^{T}E\left[{\mathbf{F_t}}\right]$

<br>

<br>

### 장점

1. 모든 대체자산군에 대해 동일한 방법론을 적용할 수 있다.
2. 대체자산 특성을 고려하여 데이터만 충분하다면 원하는 만큼 세분화할 수 있다.
3. 대체자산의 Proxy 지수를 설정할 필요 없다.
4. 펀드 투자시 발생하는 현금 유출과 유입을 구분하여 고려할 수 있다.

<br>

### 단점

1. 많은 실증 펀드 데이터가 필요하다.
2. 사용한 데이터가 대체투자 수익률의 대표성을 갖고 있다고 보기 어려울 수 있다.

