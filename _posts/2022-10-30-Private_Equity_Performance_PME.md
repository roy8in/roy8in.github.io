---
title: Private Equity Performance_Public Market Equivalent (Kaplan)
date: 2022-10-30
categories:
 - Portfolio
tags:
 - [Opportunity Cost Model, Reference Portfolio]
comments: True
use_math: True
---

Steven N. Kaplan과 Antoinette Schoar의 《Private Equity Performance: Returns, Persistence, and Capital Flows》 자료(2005)에서 필요한 부분을 간략히 정리

***

<br>

### Private Equity Performance

사모주식 성과를 공모주식 성과와 비교한다. "대체자산에 투자했던 돈으로 S＆P500에 투자했다면 어땠을까?" 라는 생각을 숫자로 표현한 것이 Public Market Equivalent, PME이다.

사모주식 펀드에 투자한 것과 S＆P500에 투자한 성과를 직접 비교한다. 이는 사모주식 투자 수익률을 공모주식과 직접 비교하기 때문에 LP에게 실용적인 방법이다.

예를 들어 1997년 3월에 사모주식 펀드에 ＄50mn을 투자하고, 2000년 3월에 ＄100mn을 실현하면 연율화한 IRR은 26％이다.

$(\frac{100}{50})^{1/3}-1 = 0.26$

그런데 만약에 LP가 1997년 3월에 ＄50mn 을 S＆P500에 투자했다면 2000년 3월에 ＄103.5mn 을 얻을 수 있었을 것이다. 이때 PME는

$\frac{100}{103.5}=0.97$

로 계산한다. PME가 1보다 작다면 사모주식 투자보다 공모주식 투자가 더 성과가 좋았음을 의미한다.

<br>

변동성이 큰 공모주식의 특성상 기준 날짜를 언제로 하느냐에 따라 PME의 결과가 1보다 클수도, 작을수도 있다는 점은 유의해야 한다.

<br>

<br>

746개 펀드의 온전한 현금흐름 데이터를 갖고 분석을 진행하였다. 아래 표에서 첫번째 행은 median, 두번째 행은 average, 세번째 행은 (standard deviation), 네번째 행은 [25％, 75％] 구간을 의미한다.

<table style="text-align:center">
    <thead>
	    <tr>
            <th rowspan=2> Sample</th>
            <th colspan=3 style="text-align:center">Equal Weighted</th>
            <th colspan=3 style="text-align:center">Size Weighted</th>
        </tr>
        <tr>
            <th style="text-align:center">All Funds</th>
            <th style="text-align:center">VC Funds</th>
            <th style="text-align:center">Buyout Funds</th>
            <th style="text-align:center">All Funds</th>
            <th style="text-align:center">VC Funds</th>
            <th style="text-align:center">Buyout Funds</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <th rowspan=4 style="text-align:center">IRR</th>
            <td>0.12</td>
            <td>0.11</td>
            <td>0.13</td>
            <td>0.12</td>
            <td>0.13</td>
            <td>0.13</td>
        </tr>
        <tr>
            <td>0.17</td>
            <td>0.17</td>
            <td>0.18</td>
            <td>0.18</td>
            <td>0.17</td>
            <td>0.18</td>
        </tr>
        <tr>
            <td>(0.31)</td>
            <td>(0.30)</td>
            <td>(0.22)</td>
            <td>(0.26)</td>
            <td>(0.31)</td>
            <td>(0.26)</td>
        </tr>
        <tr>
            <td>[0.03;0.22]</td>
            <td>[0.03;0.22]</td>
            <td>[0.05;0.22]</td>
            <td>[0.04;0.23]</td>
            <td>[0.03;0.23]</td>
            <td>[0.06;0.20]</td>
        </tr>
        <tr>
            <th rowspan=4 style="text-align:center">PME</th>
            <td>0.74</td>
            <td>0.66</td>
            <td>0.80</td>
            <td>0.82</td>
            <td>0.92</td>
            <td>0.83</td>
        </tr>
        <tr>
            <td>0.96</td>
            <td>0.96</td>
            <td>0.97</td>
            <td>1.05</td>
            <td>1.21</td>
            <td>0.93</td>
        </tr>
        <tr>
            <td>(0.81)</td>
            <td>(0.69)</td>
            <td>(0.52)</td>
            <td>(0.70)</td>
            <td>(0.74)</td>
            <td>(0.65)</td>
        </tr>
        <tr>
            <td>[0.45;1.14]</td>
            <td>[0.43;1.13]</td>
            <td>[0.62;1.12]</td>
            <td>[0.67;1.11]</td>
            <td>[0.55;1.40]</td>
            <td>[0.72;1.03]</td>
        </tr>
	</tbody>	
</table>

수수료를 제외한 성과를 기준으로 측정한 사모주식의 성과는 샘플 기간동안 S＆P500보다 소폭 부진했다. 보수적인 수수료 수준을 13%라고 가정했을 때 수수료 제외 전 성과를 기준으로 하면 PME가 1을 충분히 상회할 것이다.

