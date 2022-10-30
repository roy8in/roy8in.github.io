---
title: 기준포트폴리오 도입 사례 (Andrew Ang)
date: 2022-10-30
categories:
 - Portfolio
tags:
 - [Opportunity Cost Model, Reference Portfolio]
comments: True
use_math: True
---

Andrew Ang의 자료를 참고하여 CPPIB의 기준 포트폴리오 도입 사례 간단 정리

***

<br>

캐나다 CPPIB는 Canada Pension Plan(CPP)를 운용하며 {주식, 채권}의 매우 간단한 두 가지 팩터만 사용한다. CPPIB는 사모 주식, 인프라 및 기타 매력적인 비유동성 자산 등 다른 자산군을 많이 투자하고 있지만 그것들을 자산군으로 취급하지는 않는다. CPPIB는 "사모주식" 등 자산들을 살펴보고, 그것을 주식과 채권이라는 두 가지 팩터의 조합으로 취급한다.

<br>

사모주식에 ＄1 투자하는 것은 경제적으로 공모 주식에 ＄1.3를 투자하고 채권에 대해 매도 포지션을 갖는 것과 동일하다. 이것은 사모주식 투자가 레버리지를 활용하기 때문이며 CPPIB는 이것에 대해 채권을 -＄0.3 매도한 것으로 여긴다. 실제로 CPPIB는 사모주식의 업종 및 지역을 고려하고 인위적으로 낮은 변동성을 갖는 사모 주식의 수익률을 조정하기도 한다.(Unsmoothing을 말하는 듯)

<br>

<table style="text-align:right">
    <thead>
	    <tr>
            <td style="text-align:left">As at March 31, 2013</td>
            <td colspan=2 style="text-align:center">Asset Mix</td>
            <td colspan=2 style="text-align:center">Exposure Mix</td>
        </tr>
        <tr>
            <td style="text-align:center">ASSET CLASS</td>
            <td style="text-align:center">($ bn)</td>
            <td style="text-align:center">(%)</td>
            <td style="text-align:center">($ bn)</td>
            <td style="text-align:center">(%)</td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="text-align:left"><b>CANADIAN EQUITIES</b></td>
            <td><b>15.3</b></td>
            <td><b>8.4%</b></td>
            <td><b>17.6</b></td>
            <td><b>9.6%</b></td>
        </tr>
        <tr>
            <td style="text-align:left"> &nbsp; Public</td>
            <td>13.1</td>
            <td>7.2%</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td style="text-align:left"> &nbsp; Private</td>
            <td>2.2</td>
            <td>1.2%</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td style="text-align:left"><b>FOREIGN DEVELOPED MARKET EQUITIES</b></td>
            <td><b>64.0</b></td>
            <td><b>34.9%</b></td>
            <td><b>89.4</b></td>
            <td><b>48.7%</b></td>
        </tr>
        <tr>
            <td style="text-align:left"> &nbsp; Public</td>
            <td>35.4</td>
            <td>19.3%</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td style="text-align:left"> &nbsp; Private</td>
            <td>28.6</td>
            <td>15.6%</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td style="text-align:left"><b>EMERGING MARKET EQUITIES</b></td>
            <td><b>12.4</b></td>
            <td><b>6.7%</b></td>
            <td><b>12.1</b></td>
            <td><b>6.6%</b></td>
        </tr>
        <tr>
            <td style="text-align:left"> &nbsp; Public</td>
            <td>10.6</td>
            <td>5.7%</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td style="text-align:left"> &nbsp; Private</td>
            <td>1.8</td>
            <td>1.0%</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td style="text-align:left"><b>FIXED INCOME</b></td>
            <td><b>60.7</b></td>
            <td><b>33.1%</b></td>
            <td><b>53.2</b></td>
            <td><b>29.0%</b></td>
        </tr>
        <tr>
            <td style="text-align:left"> &nbsp; Non-marketable bonds</td>
            <td>24.4</td>
            <td>13.3%</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td style="text-align:left"> &nbsp; Marketable bonds</td>
            <td>28.1</td>
            <td>15.3%</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td style="text-align:left"> &nbsp; Inflation-linked bonds</td>
            <td>0.4</td>
            <td>0.2%</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td style="text-align:left"> &nbsp; Other debt</td>
            <td>8.6</td>
            <td>4.7%</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td style="text-align:left"> &nbsp; Money markets and debt financing</td>
            <td>(0.8)</td>
            <td>-0.4%</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td style="text-align:left"><b>FOREIGN SOVEREIGN BONDS</b></td>
            <td><b>-</b></td>
            <td><b>0.0%</b></td>
            <td><b>11.2</b></td>
            <td><b>6.1%</b></td>
        </tr>
        <tr>
            <td style="text-align:left"><b>REAL ASSETS</b></td>
            <td><b>31.1</b></td>
            <td><b>16.9%</b></td>
            <td><b></b></td>
            <td><b></b></td>
        </tr>
        <tr>
            <td style="text-align:left"> &nbsp; Real estate</td>
            <td>19.9</td>
            <td>10.8%</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td style="text-align:left"> &nbsp; Infrastructure</td>
            <td>11.2</td>
            <td>6.1%</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td style="text-align:left"><b>TOTAL</b></td>
            <td><b>183.5</b></td>
            <td><b>100.0%</b></td>
            <td><b>183.5</b></td>
            <td><b>100.0%</b></td>
        </tr>
	</tbody>	
</table>

<br>

CPPIB 펀드는 기준포트폴리오의 요소 중 하나인 해외국채를 전혀 갖고 있지 않지만 해외 국채에 대한 경제적 노출도(economic exposure)는 6.1％로 계산된다. 이는 부동산과 사모주식, 그리고 인프라를 통해 해외 국채에 대한 경제적 노출도를 갖기 때문이다.

거꾸로 CPIB는 전체 포트폴리오의 16.9％를 부동산 및 인프라에 투자하고 있으나 이 자산들은 기준 포트폴리오의 요소(factor)가 아니기 때문에 경제적 노출도는 0.0％로 취급한다. CPPIB에게 부동산과 인프라는 단지 기준포트폴리오의 팩터 노출도 및 추가 프리미엄을 얻기 위함이고 그 자체로는 자산군이 아니다.

CPPIB의 Governance Structure는 기관의 팩터 투자 및 유능한 인재 채용을 추구한다. 전 CEO인 Denison은 "기준 포트폴리오는 운용은 지출한 모든 비용에 대해 전적으로 책임을 지는 것을 의미한다. 이는 더욱 집중되고 책임있는 운용을 가능하게 한다."라고 말한다.

CPPIB가 이렇게 할 수 있는 것은 정치적 개입으로부터 독립적으로 분리되어있기 때문이다. CPPIB는 투자 전략이나 경영 계획에 대해 정부의 승인을 받을 필요가 없으며, 직원 보상 정책에 대해서도 승인을 받을 필요가 없다.

<br>

<br>

팩터 투자의 가장 큰 장점은 투자하는 자산을 움직이는 동인을 더 명확하게 파악할 수 있다는 것이며, 현재 포트폴리오가 잘못될 수 있는 환경을 더 잘 이해할 수 있다는 것에 있다.

캐나다 CPPIB의 벤치마크 역할을 하는 주식과 채권으로 구성된 포트폴리오는 기준 포트폴리오(Reference Portfolio)라고 부르며 12-15명의 인력으로 저비용, 패시브 인덱스 펀드로 운용한다.

![image](\assets\images\Reference Portfolio_base CPP.png)

<br>

CPPIB의 운용 본부는 기준 포트폴리오로부터의 모든 괴리에 대해 책임을 지며, 그 괴리를 정당화할 수 있어야만 한다. 이에 대해 CPPIB의 전 CEO David Denison은 다음과 같이 설명했다.

<div style="border:1px dashed; padding:10px">
기준 포트폴리오로부터의 이탈은 우리 모두의 책임입니다. 우리가 새로운 부동산 팀을 만들고 싶다면 우리는 그것에 수반되는 모든 비용을 만회할 수 있어야만 합니다. 우리가 진정으로 기꺼이 추가 비용을 지불하면서 부동산 투자팀을 만들 것인지 결정해야 합니다. 모든 비용을 제하고도 추가 수익을 얻어 Canada Pension Plan Fund에 추가 성과를 가져다줄 수 있다고 확신할 수 있어야 합니다.<br>
- David Denison, 전 CEO, CPPIB
</div>
