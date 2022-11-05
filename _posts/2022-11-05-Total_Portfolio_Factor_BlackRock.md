---
title: Total Portfolio Factor Allocation (BlackRock)
date: 2022-11-05
categories:
 - Quant
tags:
 - [Factor]
comments: True
use_math: True
---

자산군의 팩터 노출도를 찾는 방법론을 담은 Robert Bass, Scott Gladstone, Andrew Ang의 자료에서 필요한 부분을 정리한다.

***

전략적자산배분은 자산군을 기준으로 하는 경우가 많다. 이는 Markowitz의 평균-분산 최적화의 input으로 자산군을 직접 넣는 관습 때문이다. 

매크로 팩터 관점에서의 전략적 자산배분 프레임워크를 제시한다. 자산배분의 프레임을 재정의하고 팩터 차원에서 포트폴리오를 분석하며 팩터 기반 전략적 자산배분의 종합적인 실행 과정을 간단하고 투명하게, 그리고 직관적인 방법으로 제시한다.

2008년 금융위기 때 전통적인 자산배분 접근법은 많은 연기금에 효율적인 분산효과를 제공하지 못했다. 수많은 자산군들이 함께 하락했으며, 자산들은 공통의 팩터들에 노출되어 있었다. 

경제 성장, 실질 금리, 그리고 인플레이션 등 소수의 팩터가 전체 위험 및 액티브 위험에 지배적인 영향을 미쳤다. 그러나 많은 기관투자자들은 시장을 전망하고 수십 개의 자산군 수익률을 예측하는 데 집중했다. 간결한 팩터 세트는 이러한 가정의 복잡성을 줄이고, 기관이 가장 중요한 수익 동인에 집중할 수 있도록 한다. 

![image](\assets\images\changing approaches to investing.png)

자료: BlackRock

<br>

### Selecting a Parsiminious Set of Macro Factors

13개의 글로벌 자산군의 1997년 1월부터 2015년 9월까지의 월간 수익률의 공분산 행렬을 주성분분석(Principal Components Analysis, PCA)을 통해 매크로 팩터 세트를 선정한다. 모든 수익률은 USD로 헤지된 지수를 사용했다. 가장 높은 eigenvalue를 갖는 6개의 주성분은 전체 자산 수익률의 변동성의 95%를 설명하며, 가장 큰 eigenvalue를 갖는 3개의 주성분은 전체의 85%를 설명했다.

설명력이 높은 주성분을 매크로 팩터로 해석하는 것은 가능하다. 예를 들어,

1.  첫 번째 주성분은 동일 가중 위험 자산 포트폴리오의 수익률과 상관관계가 높았으며,
2.  두 번째 주성분은 안전 자산을 혼합한 것과 상관관계가 높았다.

이를 경제성장, 실질 금리, 그리고 인플레이션 팩터가 존재한다고 해석했다. 추가로 크레딧, 신흥 시장, 그리고 원자재 팩터를 추가적인 분석을 통해 식별했다.

<table style="text-align:center">
    <tbody>
        <tr>
            <td bgcolor="Silver" style="text-align:center"><b>팩터</b></td>
            <td bgcolor="Silver"><b>설명</b></td>
        </tr>
	    <tr>
            <td rowspan=2 style="text-align:center"><b>Equity</b></td>
            <td>글로벌 주식시장 관련 위험</td>
        </tr>
        <tr>
            <td>글로벌 주가지수</td>
        </tr>
        <tr>
            <td rowspan=2 style="text-align:center"><b>Inflation</b></td>
            <td>명목 가격 변화에 노출된 위험</td>
        </tr>
        <tr>
            <td>long 명목 국채 ＆ short 물가채</td>
        </tr>
        <tr>
            <td rowspan=2 style="text-align:center"><b>Real Rates</b></td>
            <td>실질 금리 변화에 노출된 위험</td>
        </tr>
        <tr>
            <td>물가채</td>
        </tr>
        <tr>
            <td rowspan=2 style="text-align:center"><b>Commodity</b></td>
            <td>원자재 시장과 관련 위험</td>
        </tr>
        <tr>
            <td>GSCI Commodity Index 지수</td>
        </tr>
        <tr>
            <td rowspan=2 style="text-align:center"><b>Credit</b></td>
            <td>파산 혹은 스프레드 확대 위험</td>
        </tr>
        <tr>
            <td>long 회사채 ＆ short 명목 국채</td>
        </tr>
        <tr>
            <td rowspan=2 style="text-align:center"><b>Emerging Markets</b></td>
            <td>신흥국 정부가 자본 시장 규칙을 변경할 위험</td>
        </tr>
        <tr>
            <td>long 신흥국 주식 ＆ short 선진국 주식, 신흥국 CDX, 신흥국 FX</td>
        </tr>
    </tbody>	
</table>

<br>

FX는 장기적으로 수익률 프리미엄이 없다는 점에서 수익률을 제공하는 매크로 팩터가 아니다. 하지만 FX는 포트폴리오 변동성 관점에서는 주요 동인이다.

<br>

### Mapping Assets to Macro Factors

개별 자산군 $i$의 수익률은 다음과 같이 여섯 가지 매크로 팩터 $f_j$들의 선형결합으로 표현된다.
$$
\begin{equation}r_i = a_i + \sum\limits_{j=1}^6 b_{j}^{i} f_j + \epsilon_i\end{equation}
$$
매크로 팩터 노출도 $b_{j}^{i}$를 계산하기 위해 리스크 특성치(characteristics)를 사용한다. (팩터와 특성치는 다름) 이 리스크 특성치는 주식의 베타(beta), PBR 및 OAS 스프레드 등 개별 자산에 관련된 변수들을 의미한다. 많은 리스크 모델이 자산 혹은 지수를  잠재적인 수백 수천개의 리스크 특성치에 연결(mapping)한다.

리스크 모델은 개별 자산 수익률 $r_i$를 $g_k$라는 수익률을 갖는 리스크 특성치 $\gamma_{k}^{i}$의 선형결합으로 표현한다. 이때 $k\in\\{1, \cdots,K\\}$이며 리스크 특성치의 개수 $K$는 매크로 팩터의 개수보다 훨씬 많은 것이 일반적이다.
$$
r_i = \alpha_i + \sum\limits_{k=1}^K \gamma_{k}^{i}g_{k} + u_i
$$
리스크 특성치를 식 (1)의 매크로 팩터 노출도 $b_{j}^i$를 추정하는데 사용한다. 이 때 매크로 팩터와 리스크 특성치를 연결하는 "translation matrix"를 사용하여 여섯 개의 리스크 팩터를 수천 개의 리스크 특성치와 맵핑한다.
$$
\begin{bmatrix}\tau_{1,1} & \cdots&\cdots&\cdots&\tau_{1,K} \\  \vdots & & \ddots &&\vdots\\ \tau_{6,1} & \cdots &\cdots&\cdots& \tau_{6,K}\end{bmatrix}\begin{bmatrix}\gamma_1^i \\ \vdots \\ \vdots \\ \vdots \\ \gamma_K^{i}\end{bmatrix}=\begin{bmatrix}f_1 \\ \vdots \\ f_6\end{bmatrix}
$$
개별 자산군은 리스크 특성치로 표현되고, "translation matrix"를 이용해 개별 자산군의 매크로 팩터 노출도를 얻을 수 있다.

translation matrix는 다음과 같이 추정한다. 리스크 특성치 $\gamma_k^{i}$를 매크로 팩터와 회귀분석한다.
$$
\begin{equation}\gamma_{k}^{i}=b_{1}^{i\ast}f_1 + \cdots +b_{6}^{i\ast}f_6+b_{FX}^{i \ast}f_{FX}+\nu_i  \end{equation}
$$
식 (2)의 회귀분석을 할 때 사전 경제 지식을 활용한다. 예를 들어, 국채의 경우 실질 금리 및 인플레이션 팩터에만 노출되고 경제성장 팩터에는 노출되지 않도록 제약조건을 설정한다.이러한 방법으로 모든 자산이 갖고 있는 공통의 요인이 확인할 수 있다.

<b>[그림] 자산군별 매크로 팩터 리스크 기여도</b>

![image](\assets\images\Asset Class Risk Contributions by Macro Factors.png)

글로벌 공모주식에 가장 주요한 리스크 동인은 경제성장이었으며, 글로벌 종합 채권에 가장 주요 리스크 동인은 실질금리와 인플레이션이었다. 주식과 채권으로 구성된 포트폴리오는 경제 성장과 실질 금리, 인플레이션 요인을 결합한다. 이는 전통적인 다각화된 주식-채권 포트폴리오의 팩터 기반이다.

공모주식과 사모 주식의 전체 위험의 50% 이상을 경제 성장 팩터가 차지한다. 이는 일부 사모주식 자산군이 공모 주식과 동일한 팩터 동인에 노출되어 있음을 의미한다. 사모주식의 경우 레버리지를 사용하기 때문에 공모주식보다 경제 성장에 팩터에 대한 위험 노출도가 더 큰 것으로 나타난다. "Other"는 여섯 가지 매크로 팩터로 설명되지 않는 부분이며, 공모자산과 비교하여 사모자산의 더 큰 구체적이고 이질적인, 특이한 구성 요소를 의미한다. 

글로벌 부동산 가격은 경제 성장률이 높기 때문에 경제 성장 팩터에 노출되어 있다. 부동산은 또한 채권과 비슷한 특성을 보이는데, 꾸준한 현금흐름을 제공하고 이는 실질 금리와 인플레이션 팩터 노출도를 갖는다. 사모주식처럼 부동산 또한 이질적인 요소를 많이 갖고 있다.

<br>

***

자료: Robert Bass, Scott Gladstone, and Andrew Ang - Total Portfolio Factor, Not Just Asset, Allocation (2017)





