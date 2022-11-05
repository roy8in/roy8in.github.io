---
title: 팩터-자산군 연결(mapping)
date: 2022-11-05
categories:
 - Quant
tags:
 - [Factor]
comments: True
use_math: True
---

자산군의 팩터 노출도를 찾는 방법론을 담은 David Greenberg, Abhilash Babu, Andrew Ang의 자료에서 필요한 부분을 정리한다.

***

자산군의 개수보다 팩터의 개수가 적은 것이 일반적이다.

대학 기금 등은 공모주식과 사모주식을 분리해서 취급하지만, 팩터 투자자는 성장 팩터가 두 자산에 모두 공통된 중요 드라이버라는 것을 알고 접근한다. 

팩터를 자산군에 연결함으로써 투자자는 배분 프로세스를 어떤 팩터 리스크에 노출할 지를 선택할 수 있고, 팩터의 장기 리스크 프리미엄을 추구할 수 있다.

현실에서 자산군을 팩터로 표현하는 방법은 유일하지 않으며, 투자자의 선호도에 의해 결정되는 것이 일반적이다.

<br>

### Macro Factors

여섯 가지 매크로 팩터를 사용한다.

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

### Investment Universe

개별 자산군 $i$의 수익률은 다음과 같이 매크로 팩터 $f_j$들의 선형결합으로 표현된다.
$$
r_i = \alpha_i + \sum\limits_j b_j f_j + \epsilon_i
$$
여기서 $\alpha_i$는 $0$이라고 가정한다. 매크로 팩터 노출도를 추정하기 위해 제약조건이 있는 단계적 회귀분석을 사용한다. 개별 자산군이 관련된 매크로 팩터에 대한 노출도만 있다고 가정한다. 즉, 경제적 사전 지식(domain knowledge)를 활용한다. 예를 들어 주식은 크레딧 팩터에 대한 함수가 아님을 가정한다.

<br>

***

자료: David Greenberg, Abhilash Babu, and Andrew Ang - Factors to Assets: Mapping Factor Exposures to Asset Allocations (2016)





