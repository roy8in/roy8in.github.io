---
layout: post
title: 『Central Banking 101』 NOTE (진행 중)
date: 2022-09-03
categories: 
    - Monetary_System
tag: 
    - [Monetary System, Fed, Finance]
comments: True
use_math: True
---

뉴욕 연은의 Open Markets Desk에서 트레이더로 일했던 조셉 왕(Joseph Wang)이 쓴 [『Central Banking 101』](https://www.amazon.com/Central-Banking-101-Joseph-Wang/dp/0999136747)을 번역/정리하며 미국 단기자금시장에 대한 이해를 높인다.

내용이 많아서 당장 필요한 부분부터 읽고, 지속적으로 채워나갈 예정.

***

## Section Ⅰ.  Money and Banking

### Chapter 1 - Types of Money

돈이란 무엇일까? 대부분의 사람이 돈에 대해 생각할 때 그들은 지폐(**Fiat Currency**)라고 부르는 정부에서 찍어낸 종이를 떠올리게 된다. 하지만 통화는 현대 금융 시스템에서는 매우 작은 부분에 불과하다. 대부분의 사람들은 급여가 은행 계좌와 연결되어 있고, 전자 지불로 돈을 사용한다. 은행 계좌에 나타나는 숫자를 은행 예금(**Bank Deposits**)라고 부르며, 정부가 아닌 상업 은행이 창조한 돈이다. 은행 예금은 대부분의 대중이 생각하는 돈이다.

<span style="color:blue">(중앙은행과 일반 시중 은행을 구분하기 위해 '상업은행'이라는 표현을 쓰기로 함)</span>

은행이 창조한 화폐인 은행 예금은 ATM 기계 등을 통해 언제든지 지폐로 교환할 수 있다. 그러나 둘은 다르다. 은행 예금은 은행에 책임이 있으며, 해당 은행이 파산할 경우 사라질 위험이 있다. 반면 ＄100의 지폐는 미국 정부 산하 연준(Federal Reserve)가 발행한 돈으로 미국이  존재하는 한 가치를 인정받는다. 다만 은행이 망하더라도 예금에 대해서는 연방예금보험공사(FDIC)가 &#36;250k까지 보증 보험을 제공하기 때문에 사람들은 은행 예금을 지폐 만큼 안전하다고 느낀다.

세 번째 돈은 연준이 발행하고 상업은행만 갖고 있을 수 있는 중앙은행 지급 준비금(**Reserves**, 지준)이다. 고객 은행 예금이 상업 은행의 차용증서(a bond of debt, IOU)인 것처럼 중앙은행 준비금은 연준의 차용증서이다. 상업 은행의 관점에서 보면 통화와 은행 준비금은 교환 가능하다. 상업은행은 연준에 요청하여 그들의 준비금을 지폐로 바꿀 수 있다. 상업은행이 연준에게 ＄1,000의 돈을 화폐로 요구하면 연준에 있는 상업은행 계좌에서 준비금 ＄1,000이 감소한다. 상업은행은 연준에 계정을 갖고 있는 상업은행들과 서로 준비금을 화폐 혹은 예금과 교환할 수 있다.있다.

마지막 유형의 돈은 이자를 지급하는 재무부 채권(**Treasuries**, 국채)이다. 지폐와 중앙은행 지준처럼 국채는 미국 정부(재무부)가 발행한다. 국채는 시장에 매도함으로써 쉽게 은행 예금으로 바꿀 수 있고, 국채를 담보로 대출을 빌릴 수 있도 있다. 내가 대형 기관 투자자 혹은 수백만 달러의 돈을 가진 부자라고 가정해보자. 나는 상업은행이 아니기 때문에 중앙은행에 준비금을 예치할 수 없고, FDIC가 보증하는 범위 이상을 상업은행에 예치하는데 부담을 느낄 수 있다. 또한 모든 부를 지폐로 보유하는 것은 말이 안된다. 따라서, 이런 부류의 사람들에게 국채는 돈이다.

|                  돈의 종류                   |  발행자   |  보유자  |   규모    |
| :------------------------------------------: | :-------: | :------: | :-------: |
|             지폐 (Fiat Currency)             | 미국 정부 |  누구나  | ＄2.276T  |
|          은행 예금 (Bank Deposits)           | 상업 은행 |  누구나  | ＄18.109T |
| 중앙은행 지급 준비금 (Central Bank Reserves) | 미국 정부 | 상업은행 | ＄3.249T  |
|         재무부 증권 (Treasury, 국채)         | 미국 정부 |  누구나  | ＄22.424T |

자료: 

1. 지폐, 지준 - [The Fed - Factors Affecting Reserve Balances - H.4.1](https://www.federalreserve.gov/releases/h41/)

2. 은행 예금 - [Federal Reserve Board - Assets and Liabilities of Commercial Banks in the United States - H.8](https://www.federalreserve.gov/releases/h8/)

3. 재무부 증권 - [Market Value of U.S. Government Debt - Dallasfed.org](https://www.dallasfed.org/research/econdata/govdebt)



금융 시스템이 정상적으로 작동하면 모든 종류의 돈은 서로 자유롭게 교환될 수 있다. 만약 이러한 교환에 문제가 생기면 금융 시스템에 심각한 문제가 발생하게 된다. 

<br>

#### A. Central Bank Reserve

중앙은행 지급 준비금은 중앙은행이 금융 자산을 매입하거나 부채를 차입을 할 때 생긴다. 중앙은행은 지급 준비급을 만들 수 있는 유일한 주체이며 금융 시스템 내 지급 준비금의 총합은 중앙은행의 행동에 의해 결정된다. 예를 들어, 미국 연준이 ＄10억의 국채의 살 때, 연준은 ＄10억의 중앙은행 준비금을 창조해 지불한다. 

연준이 국채를 매입할 때 국채 매도자가 상업은행인지 은행이 아닌 주체인지는 중요하지 않다. 

<b>⒜ 연준이 국채를 상업은행으로부터 매입할 때</b>

상업은행의 국채 자산은 중앙은행 지급 준비금으로 바뀐다.

<table>
    <caption>
        <h4>
            상업은행 대차대조표
    	</h4>
    </caption>
    <colgroup>
        <col style="width:35%">
        <col style="width:15%">
        <col style="width:35%">
        <col style="width:15%">
    </colgroup>
    <tr style="background-color:whitd">
        <td style="text-align:center" colspan=2><b>자산</b></td> 
        <td style="text-align:center" colspan=2><b>부채</b></td> 
    </tr>
    <tr style="background-color:white">
        <td>Treasuries</td>
        <td style="text-align:right">(＄10억)</td>
        <td></td>
        <td></td>
    </tr>
    <tr style="background-color:white">
        <td>Reserves</td>
        <td style="text-align:right">+＄10억</td>
        <td></td>
        <td></td>
    </tr>
</table>

<table>
    <caption>
        <h4>
            연준 대차대조표
    	</h4>
    </caption>
    <colgroup>
        <col style="width:35%">
        <col style="width:15%">
        <col style="width:35%">
        <col style="width:15%">
    </colgroup>
    <tr style="background-color:whitd">
        <td style="text-align:center" colspan=2><b>자산</b></td> 
        <td style="text-align:center" colspan=2><b>부채</b></td> 
    </tr>
    <tr style="background-color:white">
        <td>Treasuries</td>
        <td style="text-align:right">+＄10억</td>
        <td>Reserves</td>
        <td style="text-align:right">+＄10억</td>
    </tr>
</table>

<br>

<b> ⒝ 연준이 국채를 상업은행이 아닌 주체로부터 매입할 때 </b>

상업은행이 아닌 주체는 연준 계정이 없어(연준의 직접 거래 대상이 아님) 준비금을 자산으로 가질 수 없어서 국채는 상업은행을 거쳐 중앙은행에게 가는 모양이 된다.

<table>
    <caption>
        <h4>
            기업 대차대조표
    	</h4>
    </caption>
    <colgroup>
        <col style="width:35%">
        <col style="width:15%">
        <col style="width:35%">
        <col style="width:15%">
    </colgroup>
    <tr style="background-color:whitd">
        <td style="text-align:center" colspan=2><b>자산</b></td> 
        <td style="text-align:center" colspan=2><b>부채</b></td> 
    </tr>
    <tr style="background-color:white">
        <td>Treasuries</td>
        <td style="text-align:right">(＄10억)</td>
        <td></td>
        <td></td>
    </tr>
    <tr style="background-color:white">
        <td>Bank Deposits</td>
        <td style="text-align:right">+＄10억</td>
        <td></td>
        <td></td>
    </tr>
</table>



<table>
    <caption>
        <h4>
            상업은행 대차대조표
    	</h4>
    </caption>
    <colgroup>
        <col style="width:35%">
        <col style="width:15%">
        <col style="width:35%">
        <col style="width:15%">
    </colgroup>
    <tr style="background-color:whitd">
        <td style="text-align:center" colspan=2><b>자산</b></td> 
        <td style="text-align:center" colspan=2><b>부채</b></td> 
    </tr>
    <tr style="background-color:white">
        <td>Reserves</td>
        <td style="text-align:right">+＄10억</td>
        <td>Deposits to 기업</td>
        <td style="text-align:right">+＄10억</td>
    </tr>
</table>

<table>
    <caption>
        <h4>
            연준 대차대조표
    	</h4>
    </caption>
    <colgroup>
        <col style="width:35%">
        <col style="width:15%">
        <col style="width:35%">
        <col style="width:15%">
    </colgroup>
    <tr style="background-color:whitd">
        <td style="text-align:center" colspan=2><b>자산</b></td> 
        <td style="text-align:center" colspan=2><b>부채</b></td> 
    </tr>
    <tr style="background-color:white">
        <td>Treasuries</td>
        <td style="text-align:right">+＄10억</td>
        <td>Reserves</td>
        <td style="text-align:right">+＄10억</td>
    </tr>
</table>

<br>

***

<br>

중앙은행 지급준비금은 연준의 대차대조표를 절대 벗어나지 않지만, 상업 은행이 매일 서로 결제 지급을 함에 따라 계정이 계속 바뀌게 된다. A은행을 이용하는 한 기업이 B은행을 사용하는 거래 상대방(공급업자)에게 총 거래 금액＄10억의 절반인 ＄5억을 지급했다고 하자. 기업의 A은행 계좌의 예금 잔액이 ＄5억 감소하고, 공급업자는 B은행 계좌에 예금 ＄5억이 증가하게 된다. 이러한 거래 이면에는 A은행이 연준에 예치한 ＄5억의 지급준비금이 B은행으로 이동하는 거래가 발생한다.

<b>기업이 ＄5억을 공급업자에게 지급했을 때</b>

<table>
    <caption>
        <h4>
            (기업의 거래 은행인) A은행 대차대조표
    	</h4>
    </caption>
    <colgroup>
        <col style="width:35%">
        <col style="width:15%">
        <col style="width:35%">
        <col style="width:15%">
    </colgroup>
    <tr style="background-color:whitd">
        <td style="text-align:center" colspan=2><b>자산</b></td> 
        <td style="text-align:center" colspan=2><b>부채</b></td> 
    </tr>
    <tr style="background-color:white">
        <td>Reserves</td>
        <td style="text-align:right">＄10억</td>
        <td>Deposits to 기업</td>
        <td style="text-align:right">＄10억</td>
    </tr>
    <tr>
        <td>Reserves sent to B은행</td>
        <td style="text-align:right">(＄5억)</td>
        <td>Deposits to 기업</td>
        <td style="text-align:right">(＄5억)</td>
    </tr>
</table>



<table>
    <caption>
        <h4>
            기업 대차대조표
    	</h4>
    </caption>
    <colgroup>
        <col style="width:35%">
        <col style="width:15%">
        <col style="width:35%">
        <col style="width:15%">
    </colgroup>
    <tr style="background-color:whitd">
        <td style="text-align:center" colspan=2><b>자산</b></td> 
        <td style="text-align:center" colspan=2><b>부채</b></td> 
    </tr>
    <tr style="background-color:white">
        <td>Bank Deposits</td>
        <td style="text-align:right">＄10억</td>
        <td></td>
        <td></td>
    </tr>
    <tr style="background-color:white">
        <td>Bank Deposits</td>
        <td style="text-align:right">(＄5억)</td>
        <td></td>
        <td></td>
    </tr>
    <tr style="background-color:white">
        <td>재고</td>
        <td style="text-align:right">+＄5억</td>
        <td></td>
        <td></td>
    </tr>
</table>



<table>
    <caption>
        <h4>
            (공급업자의 거래 은행인) B은행 대차대조표
    	</h4>
    </caption>
    <colgroup>
        <col style="width:35%">
        <col style="width:15%">
        <col style="width:35%">
        <col style="width:15%">
    </colgroup>
    <tr style="background-color:whitd">
        <td style="text-align:center" colspan=2><b>자산</b></td> 
        <td style="text-align:center" colspan=2><b>부채</b></td> 
    </tr>
    <tr style="background-color:white">
        <td>Reserves from 은행 A</td>
        <td style="text-align:right">+＄5억</td>
        <td>Deposits to 공급업자</td>
        <td style="text-align:right">+＄5억</td>
    </tr>
    </tr>
</table>



<table>
    <caption>
        <h4>
            공급업자 대차대조표
    	</h4>
    </caption>
    <colgroup>
        <col style="width:35%">
        <col style="width:15%">
        <col style="width:35%">
        <col style="width:15%">
    </colgroup>
    <tr style="background-color:whitd">
        <td style="text-align:center" colspan=2><b>자산</b></td> 
        <td style="text-align:center" colspan=2><b>부채</b></td> 
    </tr>
    <tr style="background-color:white">
        <td>재고</td>
        <td style="text-align:right">(＄5억)</td>
        <td></td>
        <td></td>
    </tr>
    <tr style="background-color:white">
        <td>Bank Deposits</td>
        <td style="text-align:right">+＄5억</td>
        <td></td>
        <td></td>
    </tr>
</table>

<br>

***

<br>

2008년 금융위기 이전에 연준은 준비금 부족 제도(reserve scarcity regime) 하에서 통화정책을 운영하며 은행 시스템에 있는 지준에 적용되는 단기 금리를 조절하였다. 그 당시 전체 은행 시스템에는 ＄300억 규모의 지급 준비금이 있었다. 오늘 날 ＄3조 달러의 지준과 비교하면 적은 수준이다. 연준은 양적완화(QE) 프로그램을 통해 지준을 늘려 장기 국채를 매입함으로써 장기 금리를 낮추고자 했다. 오늘날 연준은 은행의 초과 지준(excess reserves)에 적용되는 단기 금리를 조절하고 참가자가 연준에 돈을 맡길 수 있는 프로그램인 하루 짜리 역RP 기구(Overnight Reverse Repo Facility)에 적용되는 금리를 결정한다. 연준의 운영 체계는 다음에 다룬다.

<br>

#### <b>B. Bank Deposits</b>

은행 예금은 상업 은행이 대출 혹은 금융 자산을 구매하기 위해 창조된다. 예금에 대한 흔한 오해는 은행이 예금을 수취한 다음 그것을 다른 사람에게 대출한다는 인식이다. 예금을 대출해주기 보다는 은행은 대출해 줄 때 단순히 은행 예금을 창조한다. 이것은 중앙은행이 지급 준비금을 창조하는 것과 유사한 방식이다. 중앙은행은 상업은행들의 은행으로 작용하고, 상업은행은 개인과 비은행 기업들의 은행으로 작용한다.

상업은행은 시중에 다양하게 존재하는 반면 중앙은행은 유일하다는 점은 큰 차이점이다. 중앙은행은 유일하기 때문에 모든 준비금은 중앙은행의 대차대조표 내에서 창조되고 서로 다른 상업은행들의 거래를 통해 상업은행 계정끼리 교환된다. 상업은행의 경우 각각의 상업은행은 그들만의 대차대조표가 있고 각자의 예금을 창조한다. 그러므로 예금자가 은행 예금을 다른 은행으로 이체할 경우 한 은행의 대차대조표에서 다른 은행의 대차대조표로 이동하게 된다. 이 경우 한 은행이 다른 은행에 반드시 지불 해야 한다. 이 지불은 중앙은행의 준비금 형태를 통해 이루어진다.

상업은행이 예금을 갑자기(out of thin air) 창조하기 때문에 상업은행 예금은 중앙은행 준비금보다 더 많다. 상업은행은 매일 대규모의 인출과 출금이 이루어진다. 매일 입출금이 끝난 후 정산할 때 지급준비금의 변화는 그다지 크지 않기 때문에 상업은행들은 창조한 예금보다 적은 규모의 준비금을 갖고 있는다. 이것을 부분지급준비금 제도(Fractional Reserve Banking)라고 부른다. 만약 많은 규모의 인출이 예상된다면 상업은행은 다른 상업은행 혹은 연준으로부터 준비금을 빌려야 한다.

가장 흔한 형태의 돈인 은행 예금은 덜 안전하다. 은행 예금은 민간 부문에서 창조된 것이기 때문에 무위험 자산은 아니다. 은행이 갖고 있는 너무 많은 악성 대출이 지급 불능이 되었을 때 은행업 위기는 발생한다. 이 경우 은행의 예금은 통화와 1:1로 전환되지 않을 수도 있어 은행 예금 ＄100이 지폐 ＄100로 교환되지 않을 수 있다. 많은 예금자들이 혼란에 빠지고 동시에 예금을 인출하려고 할수록 은행의 종말은 가속된다. 19세기 살쾡이 은행([Wildcat banking](https://en.wikipedia.org/wiki/Wildcat_banking)) 시대에는 통일된 화폐가 없어 각각의 상업 은행이 각자 예금을 만들어냈고 각자 지폐를 주조했다. 은행 폐업이 너무 잦았기 때문에 각 은행에서 만든 지폐는 채무 불이행 위험을 반영하여 액면가 이하로 할인된 금액으로만 거래되었다.

이후 미국 정부는 은행 위기 위험을 줄이기 위해 은행 예금 보증, 강도 높은 은행 규제, 연준의 할인 창구를 통한 긴급 대출 등의 많은 발전을 이루었다. 이러한 조치들은 효과적으로 은행 예금을 더욱 무위험스럽게 만들어 주었고, 중앙은행 준비금이나 화폐처럼 좀 더 돈처럼 것으로 만들어 주었다. ＄25만의 FDIC 예금 보증은 대부분 예금자의 예금을 보호한다. 이러한 사람들에게 은행 예금은 위험이 없는 돈이다.

<br>

#### <b>C. Treasuries</b>

재무부 증권(국채)은 연방 정부가 발행한 부담보 부채이며, 안정성과 유동성 때문에 금융 시스템 내에서 지배적인 화폐의 역할을 한다. 은행 예금과 다르게 미국 연방 정부로부터 100% 보장되기 때문에 무위험이다. 중앙은행 지급 준비금과 달리 국채는 누구나 소유할 수 있다. 개인 투자자의 경우 대부분 은행 예금의 형태로 돈을 보유하지만, 기관 투자자는 국채를 활용해 돈을 보유한다. 재무부 채권은 규모가 큰 투자자에게 돈이다.

국채는 다른 종류의 돈들과는 화폐성(moneyness)에서 차이가 있다. ＄100의 은행 예금, ＄100의 중앙은행 지급 준비금, ＄100의 지폐는 언제나 ＄100의 명목 가치를 갖는다. 그러나 오늘 ＄100 가치의 국채를 매입해도 시장에서 형성되는 가격(pricing)에 따라 그 명목 가치는 수시로 변한다. 만기가 긴 국채는 예상되는 인플레이션과 금리 변화에 더 민감하여 만기가 짧은 채권에 비해 시장 가치가 크게 변한다. 만기까지 보유할 경우 이러한 가치 변화는 중요하지 않지만, 만기 이전에 매도할 경우 수익 혹은 손실이 발생할 수 있다.

국채는 투자자에게 큰 규모의 돈을 저장할 수 있게 해준다. 투자자는 국채로 식료품을 직접 살 수 없으나, 국채를 매도하거나 빌려줌으로써 쉽게 은행 예금으로 바꿀 수 있다. 국채 시장과 레포 대출 시장은 매우 유동성이 높고 전세계 금융 센터에서 거래할 수 있다. 투자자는 국채로 실물 경제 물품을 구매하는데 사용하지 않지만 다른 투자를 위해 사용한다. 투자자는 국채를 담보로 맡기고 금융 자산을 매수한다. 결국 투자자는 국채를 이용해 주식이나 채권과 같은 금융 자산을 매입하는 것이다.

재무부 증권은 미국 재무부가 화폐를 창조하는 방법이다. 미국 재무부가 ＄100의 재무부 증권을 투자자에게 발행하면 투자자는 은행 예금 ＄100을 국채 ＄100로 교환한다. 투자자 입장에서 단지 한 형태의 돈을 다른 형태로 바꾼 것 뿐이다. 재무부 입장에서는 국채를 발행함으로써 실물 경제의 재화와 서비스를 구매할 수 있게 된다. 돈의 흐름을 함께 보면 이해가 쉽다.

<b>재무부가 ＄100의 국채를 발행하고 그것을 노인의료보험제도(medicare) 지원에 사용</b>

<table>
    <caption>
        <h4>
            재무부 대차대조표
    	</h4>
    </caption>
    <colgroup>
        <col style="width:35%">
        <col style="width:15%">
        <col style="width:35%">
        <col style="width:15%">
    </colgroup>
    <tr style="background-color:whitd">
        <td style="text-align:center" colspan=2><b>자산</b></td> 
        <td style="text-align:center" colspan=2><b>부채</b></td> 
    </tr>
    <tr style="background-color:white">
        <td>Reserves</td>
        <td style="text-align:right">+＄100</td>
        <td>Treasury Debt</td>
        <td style="text-align:right">+＄100</td>
    </tr>
    <tr>
        <td>Reserves</td>
        <td style="text-align:right">(＄100)</td>
        <td>Medicare payment</td>
        <td style="text-align:right">(＄100)</td>
    </tr>
</table>



<table>
    <caption>
        <h4>
            은행 시스템 대차대조표
    	</h4>
    </caption>
    <colgroup>
        <col style="width:35%">
        <col style="width:15%">
        <col style="width:35%">
        <col style="width:15%">
    </colgroup>
    <tr style="background-color:whitd">
        <td style="text-align:center" colspan=2><b>자산</b></td> 
        <td style="text-align:center" colspan=2><b>부채</b></td> 
    </tr>
    <tr style="background-color:white">
        <td>Reserves to settle Treasury purchase</td>
        <td style="text-align:right">(＄100)</td>
        <td>Investor's Deposits to purchase Treasury</td>
        <td style="text-align:right">($100)</td>
    </tr>
    <tr style="background-color:white">
        <td>Reserves to Medicare payment</td>
        <td style="text-align:right">+＄100</td>
        <td>Doctor's deposits for Medicare service</td>
        <td style="text-align:right">+＄100</td>
    </tr>
</table>



<table>
    <caption>
        <h4>
            투자자 대차대조표
    	</h4>
    </caption>
    <colgroup>
        <col style="width:35%">
        <col style="width:15%">
        <col style="width:35%">
        <col style="width:15%">
    </colgroup>
    <tr style="background-color:whitd">
        <td style="text-align:center" colspan=2><b>자산</b></td> 
        <td style="text-align:center" colspan=2><b>부채</b></td> 
    </tr>
    <tr style="background-color:white">
        <td>Bank Deposits</td>
        <td style="text-align:right">(＄100)</td>
        <td></td>
        <td></td>
    </tr>
    <tr style="background-color:white">
        <td>Treasuries</td>
        <td style="text-align:right">+＄100</td>
        <td></td>
        <td></td>
    </tr>
</table>



<table>
    <caption>
        <h4>
            의사 대차대조표
    	</h4>
    </caption>
    <colgroup>
        <col style="width:35%">
        <col style="width:15%">
        <col style="width:35%">
        <col style="width:15%">
    </colgroup>
    <tr style="background-color:whitd">
        <td style="text-align:center" colspan=2><b>자산</b></td> 
        <td style="text-align:center" colspan=2><b>부채</b></td> 
    </tr>
    <tr style="background-color:white">
        <td>Receivables</td>
        <td style="text-align:right">(＄100)</td>
        <td></td>
        <td></td>
    </tr>
    <tr style="background-color:white">
        <td>Bank Deposits</td>
        <td style="text-align:right">+＄100</td>
        <td></td>
        <td></td>
    </tr>
</table>

<br>

투자자는 국채를 매입함으로써 은행 예금이 ＄100 감소하고, 투자자가 거래하는 은행은 지급 준비금 ＄100을 중앙은행에 보내고 투자자를 대신해 국채 거래를 해준다. 미국 재무부는 연준에 계좌를 갖고 있으며 중앙은행 지급 준비금을 보유할 수 있다. 미국 재무부가 국채 발행으로 조달한 ＄100을 사용할 때, ＄100의 중앙은행 지급준비금은 결구 상업 은행 시스템으로 다시 들어가게 된다. 예를 들면 미국 재무부가 조달한 ＄100을 메디케어 지출에 사용한다고 하자. 이 돈을 받은 의사는 거래하는 은행에 예치하고, 이를 중앙은행에 지급준비금으로 예치한다. 정산할 때 은행 예금의 양과 중앙은행의 지급 준비금은 바뀌지 않지만 이전에 없던 ＄100의 국채가 생겼다. 투자자는 국채 ＄100를 사고, 그것을 활용해 다른 금융 자산을 매수하거나 은행에 국채를 팔아 은행 예금으로 바꿔 실물 경제 재화를 구매할 수 있다.

국채 외에도 화폐성이 뛰어난 정부 발행 증권이 있다. 국채 다음으로 유동성이 높고 안전한 자산은 Agency RMBS이다. 이것은 정부로 부터 보증된 주택담보대출(Residential Mortgage-Backed Securities)이다. 위험이 없고 활발하게 거래되나 국채보다 유동성은 떨어진다. 연준은 국채를 매입하는 통화 정책을 선호하지만 양적완화를 할 때는 기관 MBS도 활발히 매입했다.



<div style="border:1px dashed; padding:10px">
<br>
<b>국채 시장이 고장나면...</b>
<br><br>
전세계 투자자들은 미국 국채를 손쉽게 은행 예금으로 바꿔 지불하고자 한다. 이것은 모두가 ATM으로 가서 그들의 은행 예금을 지폐로 바꾸는 것으로 생각할 수 있다. 만약 어느 날 모든 ATM이 "지급 불가능" 표시가 뜬다면 대중은 패닉에 빠질 것이다. 이것은 2020년 3월 COVID-19 팬데믹 기간에 미국 국채 시장에서 발생했던 일이다.
<br><br>
2020년 3월 전세계 사람들은 겁을 먹고 달러를 보유하길 원했다. 투자자들은 그들의 투자 펀드를 환매하고 외국인 투자자들 그들의 자국 통화를 팔아 미국 달러를 보유하고자 했다. 이러한 환매에 대응하기 위해 투자 펀드와 해외 중앙은행은 ATM에서 현금을 인출하듯이 그들이 보유하고 있는 미국 국채를 매도하였다. 그러나 당시에는 큰 폭의 할인 없이는 그들이 보유한 국채를 충분히 매도할 수 없었다. ATM 기계가 고장난 것이다.
<br><br>
기관투자자가 증권을 매도할 때 딜러를 통하게 되는데 딜러가 가격을 제시해주길 기대한다. 딜러는 일반적으로 증권을 매입하고 보유하다가 다른 투자자에게 매도하며 매수/매도 가격 차이를 수익으로 취한다. 2020년 3월 수많은 투자자들이 딜러에게 전화에 걸어 보유중인 증권을 매도하고자 했다. 돈을 빌려 모기지 증권에 투자하는 모기지 리츠(REITs)는 이러한 대출을 상환하기 위해 대규모 기관 MBS를 매도하였다. 회사채 ETF는 투자자 환매에 대응하기 위해 보유 중인 채권을 매도하기 위해 노력했다. MMF는 같은 이유로 CP를 매도하고자 했다. 딜러는 갑자기 증권을 너무 많이 받게 되었고 보유 한도를 초과하게 되었다.
<br><br>
2008년 금융위기 당시 투자자가 재무 상황에 대한 우려로 딜러들에게 대출을 거부함에 따라 딜러들에 대한 매도  요구가 급증했다. 이에 딜러들은 보유한 증권을 급매할 수 밖에 없었고 이는 금융시장 패닉을 악화시켰다. 이 사건 이후 규제 당국은 딜러가 많은 증권을 보유하기 어렵게 규제를 강화하였고 위험자산을 보유하는 비용을 높게 만들었다. 그러나 2020년 3월 딜러들의 요구를 수행하는데 방해 요소로 작용했다. 딜러들은 보유 한도에 도달하였고, 미국 국채 조사 더 이상 매수할 수 없었다.
<br><br>
투자자들은 금융시장에 큰 혼란이 생긴 것은 알았으나 미국 국채 조차 매도할 수 없다는 사실에 놀랐다. 이것은 매도할 수 있는 모든 것이 매도되는 엄청난 패닉으로 이어졌다. 모든 금융 시장이 붕괴되었다. 금융시장은 연준이 개입하기 전까지 안정되지 않았다.
<br>
<br>
딜러의 대차대조표의 한계가 있다는 것을 인지하고 연준은 세 가지를 수행했다. 첫째, 연준은 은행 지주 회사에 대차대조표 크기를 제한하는 일부 규정을 일시적으로 유예했다. 둘째, 새로운 해외 레포 상설기구(Repo Facility)를 개설하여 해외 중앙은행이 그들의 국채를 매도하지 않고 미국 달러를 구할 수 있도록 했다. 셋째, 연준은 대규모 양적 완화를 다시 시행했고, 시장을 안정시켰다. 몇 주 만에 연준은 거의 ＄2조 규모의 국채와 기관 MBS를 딜러로부터 매입했다. 이 매수는 딜러의 증권 보유 한도에 여유를 주었고 고객의 매도 주문을 받을 수 있게 해주었다. 이는 국채의 현금성을 회복시켰고 해외 시장의 안정에 도움을 주었다.
<br><br>
</div>

<br>

#### D. Fiat Currency

낯선 용어지만 명목 화폐(fiat currency)는 가장 쉽게 볼 수 있는 돈의 형태이다. 통화는 정부가 발행하고 정부로부터 보증된다.  예금자는 은행이나 ATM기계에서 은행 예금을 화폐로 바꿀 수 있다. 상업 은행은 금고에 충분한 화폐를 보유함으로써 은행 예금이 명목 화폐로 교환될 수 있게 한다. 상업 은행은 중앙은행 지급준비금을 연준에 요구하면 화폐로 바꿀 수 있다. 연준은 상업은행의 수요를 충족시키기 위해 언제나 준비하고 있다.

돈을 화폐로 보유하는 것은 다른 형태로 보유하는 것보다 큰 이점은 없다. 금이나 은처럼 화폐는 현물로 존재하며 누가 갖고 있든지 가치가 인정된다. 정부는 중앙은행과 상업은행에 대한 영향력이 있기 때문에 금융 시스템의 모든 것을 관리한다. 법적으로 금융 시스템에 접근할 수 없는 사람도 있지만 물건을 구매할 때 화폐를 사용할 수 있다. 화폐를 제외한 다른 형태의 모든 돈은 단지 컴퓨터 스크린에 찍히는 숫자일 뿐이다. 정부의 조사를 피하기 위해 수많은 ＄100 지폐가 개인들의 금고에 보관되어 있다는 증거가 있다.

<div style="border:1px dashed; padding:10px">
<br>
<b>대부분의 화폐는 해외에 있다.</b>
<br><br>
전자 결제가 증가함에도 유통 통화는 지속적으로 증가하여 2020년 약 ＄20조에 달한다. 유통통화 중 ＄100 지폐가 가장 많다는 거은 흥미롭다. 약 150억 장의 ＄100 지폐가 유통되고 있으며, 130억 장의 ＄1 지폐와 115억 장의 ＄20 지폐가 유통되고 있다. 달러 가치 측면에서 보면 약 ＄2조의 유통화폐 중 80%가 ＄100 지폐의 형태로 존재하는 것이다.
<br><br>
＄100 지폐가 가장 많이 유통됨에도 대부분의 미국인은 일상생활에서 ＄100 지폐를 보기 어렵다. 대신 미국인들은 ＄20 지폐나 더 적은 규모의 지폐를 주로 사용한다. 연구에 따르면 대부분의 ＄100 지폐는 미국 외 지역에 있다.<br><br>
많은 미국 달러가 해외에 존재하는 데는 몇 가지 이유가 있다. 아르헨티나와 같은 신흥국 국가의 부자들은 그들의 부를 미국 달러같은 주요 통화로 보유하는 것을 선호한다. 왜냐하면 신흥국은 잘 관리되지 않아 두 자리수의 인플레이션을 보이는 경우가 많다. 실제로 엘살바도르와 같은 일부 신흥국의 경우 그들의 통화 정책을 완전히 버리고 미국 달러를 공용 통화로 사용한다. 또한, 범죄자들은 이동이 쉽고 추적이 불가능한 점을 이용해 부를 미국 달러로 보유한다. 해외 마약 카르텔을 급습한 경찰이 수억 달러 규모의 돈뭉치를 발견하곤 한다.
<br><br>
전세계적으로 달러 화폐는 금본위제 때 금이 그랬던 것처럼 가치 저장의 수단으로 널리 통용된다. 우리는 달러본위제 세상(dollar-standard world)에 살고 있고, 미국 달러는 전세계에서 거래되고 안전하다고 여겨진다. 이는 해외 달러 은행 업무의 활성화로 연결되었으나 해외의 달러 화폐 수요로 이어지기도 했다.
<br><br>
</div>

<br>

#### 흔히 나오는 질문들

이번 장은 오늘 날의 통화 시스템을 이해하기 위한 체계를 제공함이 목적이다. 이러한 체계를 이해함으로써 중앙은행의 행동을 이해하고 흔한 오해를 해소할 수 있어야 한다. 관련하여 몇 가지 흔한 질문들이 있다.

<br>

<b>은행은 왜 지급준비금을 대출하지 않습니까?</b>

양적완화가 처음 도입되었을 때 많은 시장 평론가들은 상업은행의 지급준비금이 폭발적으로 커지는 것을 보고는 왜 은행들이 지급준비금을 대출하지 않는지 의아해했다. 중앙은행은 지급준비금은 상업은행만 가질 수 있고 연준의 대차대조표를 벗어날 수 없다. 상업은행이 보유한 중앙은행 지급준비금 규모는 연준에 행동에 의해 결정되고, 상업은행의 대출 규모에는 영향을 받지 않는다. 실제로 상업은행은 언제든지 준비금을 빌릴 수 있기 때문에 대출을 함에 있어 준비금의 제한을 받지 않는다.

상업은행의 대출 제약요건은 규제이거나 기업 여건 때문이다. 상업은행은 그들의 잔고 규모, 보유 자산의 질, 부채의 구성 등에 수많은 제약을 받고 있다. 이러한 규제는 은행 시스템을 더 안전하게 하지만 가능한 대출 규모를 제한하기도 한다. 상업은행은 그들이 수익을 낼 수 있을 때만 대출에 관심이 있으며 수익성 있는 대여자는 파산 가능성이 높은 침체 기간에는 찾기 힘들다. 2008년 금융위기 이후가 그랬다.

<br>

<b>대기중인 현금 때문에 주식 시장이 급등할 것 같습니까?</b>

때때로 평론가들은 은행 시스템의 예금 잔고 수준을 보고는 예금이 모두 사용된다면 금융 자산 가격이 폭등할 것이라고 한다.

중앙은행 지급준비금 수준이 연준에 의해 결정되듯, 은행 예금 잔고 규모는 상업은행의 집단  행동에 의해 대부분 결정된다. 은행 예금 잔고는 상업은행이 자산을 구매하거나 대출을 만들 때 증가하고 대출이나 자산이 환매될 때 감소한다. 은행 예금 잔고 수준은 은행 시스템이 만든 대출 규모의 지표이다. 

투자자들이 은행 예금으로 주식이나 채권을 살 때, 그것을 매도한 사람들의 은행 예금으로 들어간다. 은행 예금의 총량은 변하지 않는다. 은행 예금은 상업은행 시스템 내에서 순환할 뿐 증가하거나 감소하지 않는다. 대규모 투자는 은행 예금의 총량을 줄이거나 높일 수 있다.

<br>

<br>

### Chapter 2 - The Money Creators

이번 장에서는 돈을 만들어내는 세 주체(연준, 상업은행, 재무부)에 대해 알아본다.

#### A. The Fed

연준은 '완전 고용'과 '물가 안정'이라는 이중책무를 갖고 있다. 실제로 연준은 어느 정도의 실업률이 완전 고용 수준인지 알지 못하고, 오랜 기간 인플레이션 목표치인 2%에 물가를 고정시킬 수 없다. 연준의 인플레이션에 대한 경험은 일본중앙은행(BOJ)과 유럽중앙은행(ECB)처럼 과거 10년간 노력했으나 인플레이션 목표치에 도달하지 못했던 다른 중앙은행들의 경험과는 다르다. 연준의 이중 책무를 달성하기 위한 노력은 연준의 정책 도구를 점차 확장시켰고 대규모 화폐 공급을 포함한 비전통적 통화정책을 하게 만들었다.

연준은 책무를 달성하는데 핵심 도구인 금리를 통해 경제를 바라본다. 연준의 눈에는 r\*("r star") 라고 부르는 경제가 확장되거나 수출되지 않는 중립금리라는 것이 있다. 이자율이 r\*를 하회하면 경제는 확장하고 물가는 상승하며 실업률은 낮아진다. 이자율이 r\*를 상회하면 경제는 둔화되고 물가는 내려가며 실업률은 점차 상승한다. 연준은 경제학 박사를 고용하여 그 순간 r\* 수준을 추정하고, 이중책무를 성공시키기 위해 기준금리를 오릴지 내릴지를 결정한다. 연준의 통화 공급은 장기 금리를 조절하기 위한 노력이다.

경제가 곤경에 빠지고 연준의 모델이 중립금리가 매우 낮거나 심지어 음수일 경우 경제 성장을 도모하기 위해 연준은 모든 것을 다 해서 금리를 r\* 이하로 만들 것이다. 먼저 하루짜리 목표금리를 0%로 내리고, 장기 국채를 대규모 매입함으로써 장기 금리도 낮추기 위해 노력할 것이다. 이는 미국 국채 가격을 올리고 수익률을 낮춘다. 장기 국채는 하루짜리 단기 금리에 덜 민감하기 때문에 연준은 QE를 통해 장기 국채 금리에 간접적인 영향을 준다.

연준은 은행 지급준비금을 창조하여 금융자산을 매입한다. 상업은행이 아닌 주체들은 연준 계정이 없기 때문에 지급준비금을 가질 수 없다. 연준이 금융자산을 비은행 투자자들로부터 매입할 때 연준은 지급준비금을 투자자의 거래 은행에 보낸다. 사업은행은 투자자 계좌에 넣어준다. 이 예에서 상업은행은 연준과 투자자 사이를 이어주는 중개자 역할을 한다. 연준의 자산 매입은 중앙은행 지급준비금과 상업은행의 예금 잔액을 늘린다.

연준이 양적완화(QE)를 하는 목적은 장기 국채 금리를 낮추고 지급 준비금을 늘리는 것이며 그 분산물로 은행 예금 잔액이 증가한다. 학계의 연구에 따르면 양적완화가 국채 금리를 낮추는데 효과적이고 인플레이션을 자극한다고 한다. 그러나 미 연준(Fed), 일본 중앙은행(BOJ), 유로존 중앙은행(ECB)은 모두 대규모 QE를 했으나 인플레이션의 상승을 경험하지는 않았다. 언급한 세 주요 중앙은행들은 지난 십년간 인플레이션을 목표에 도달하는데 어려움을 겪었지만, 양적완화의 유용성을 계속 믿고 있다.

양적완화는 금융 자산 가격은 부양한 것 처럼 보이지만 실물 경제 활동을 부양하지는 못했다. 양적완화는 국채를 은행 예금과 지급준비금으로 바꿨다. 즉, 상업은행은 중앙은행 지급준비금의 형태로 더 많은 돈을 보유하게 되었고, 은행이 아닌 주체들은 은행 예금 형태로 더 많은 돈을 보유하게 되었다. 인플레이션은 경제내 수요가 공급을 초과할 때 발생하며, 국채에 저장된 돈은 실물 경제에 활용되지 않는다. 연준이 국채를 매임함에 따라 은행 예금을 갖게 된 비은행 투자자들은 은행 예금을 더 높은 금리를 제공하는 회사채 혹은 주식 투자에 사용할 수 있다. 규제로 인해 투자 옵션에 제약이 많은 상업은행의 경우 지급 준비금을 더 높은 금리를 제공하는 기관 MBS을 매수하는데 사용할 수 있다. 이러한 비은행과 은행의 거래는 자산 가격을 끌어올린다.

중앙은행이 할 수 있는 양적완화 규모의 제한은 없는 것 처럼 보인다. 연준이 수 조 달러의 자산을 매입했지만 이는 미국 GDP의 일부에 불과하다. BOJ는 일본 GDP의 100%가 넘는 양의 자산을 매입하고 있지만 금융 불안정이나 통화 약세의 신호는 나타나지 않고 있다. 그러나 BOJ의 대규모 정부 채권 보유는 일본 채권 시장을 망가뜨리고 있다. 경제 여건을 반영하기 보다는 일본 채권 시장은 일본의 정책 담당자의 의도만을 반영한다. 언젠가 일본 국채는 더 이상 거래되지 않을 것이다.

<br>

#### B. The Commercial Banks

상업 은행은 정부로 부터 돈을 만들어 낼 수 있는 권한을 부여받은 특별한 비즈니스 주체다. 일반 대중이 사용하는 돈의 대부분은 상업은행이 창조한 것이다.  은행이 더 많은 돈을 만들어 낼수록 더 많은 경제 성장이 생기기 때문에 은행 경제 내 중요한 부분을 차지한다. 상업은행의 기본적인 비즈니스 모델은 예금과 대출 금리 사이의 차이에서 발생한다. 은행이 보유한 자산은 일반적으로 모기지 대출, 상업 대출, 소비자 대출 등 대출의 형태이다. 상업은행은 국채나 기관 MBS와 같은 고품질 증권을 자산으로 갖고 있다. 

부채 사이드에는 개인들의 소매 예금(retail deposits)이 주를 이룬다. 다른 부채 항목은 MMF와 같은 기관 투자자들이 맡긴 도매 예금(wholdesale deposits) 등이 있다. 상업은행은 낮은 금리 비용과 안정적인 수준을 유지하는 소매 예금을 더 선호한다. 소매 예금 이자는 매우 낮고, 도매 예금 이자를 시장 금리를 적용받는 편이다. 이는 개인들이 이자가 거의 없더라도 은행에 예금을 예치하려는 경향이 있기 때문에 소매 예금은 시장 금리에 덜 민감하기 때문이다. 반대로 기관 투자자들은 금리에 매우 민감하고, 약간이라도 더 높은 금리를 제공하는 은행으로 돈을 옮길 수 있다. 기관 투자자들은 시장에서 문제가 발생할 조짐이 보이면 예끔을 인출하는 경향이 있으며, 이러한 예금에 의존하는 상업 은행은 자금 조달을 위해 고군분투 한다.

상업은행은 대출을 하고, 예금을 창조하고, 들어 오는 이자 수익을 보는 것은 훌륭한 비즈니스처럼 보인다. 이를 원활하게 돌아가게 하기 위해 아래에 여전히 몇 가지 작업이 있다. 상업은행은 지불능력(solvency)와 유동성(liquidity)이라는 두 가지 근본적인 문제를 마주하게 된다. 지불능력은 은행 예금이 건전한 대출로 뒷받침되는지 확인하는 것이고 유동성은 예금이 다른 상업은행이 창조한 예금과 지폐로 자유롭게 교환되는 지 확인하는 것이다. 

최상의 시나리오는 상업은행이 대출자에게 대출을 하고, 대출자는 대출에 대한 원금과 이자를 성실히 갚는 것이다.  미국의 부분준비급제도에서는 상업은행은 ＄100의 대출과 예금을 창조하기 위해 ＄5만 보유하고 있으면 된다. 비즈니스가 잘 되면 은행 소유자는 ＄5만를 투자하여 ＄100에 대한 이자를 수취할 수 있다. 그러나 만약 대출자가 채무를 갚지 않으면 상업은행은 손실을 피할 수 없다. ＄5 상당의 대출이 연체되고 상각되면 상업은행은 지급 불능상태가 되어 파산 신청을 해야할 수도 있다.

상업은행의 높은 레버리지 체계는 은행이 많은 돈을 벌 수도 있지만 그만큼 빠르게 파산할 수도 있음을 의미한다. 역사상 은행업 위기는 자주 발생하였다. 결과적으로 상업은행은 대출을 할 때 매우 조심스러워야 한다. 대출자의 재무 상황이나 대출의 목적을 확인하고 필요시 담보를 요구하기도 한다. 예를 들어 모기지 대출은 매입하고자 하는 주택을 담보로 한다. 디폴트 발생시 은행은 주택을 수취하고 그것을 팔아 대출액을 상환한다.

은행이 반드시 해결해야하는 두 번째 문제는 유동성이다. 은행이 ＄100의 대출을 하고 대출자가 즉시 돈을 인출하여 다른 은행을 이용하는 공급업자에게 지불했다고 하자. 상업은행은 충분한 중앙은행 지급준비금을 보유하고 있어 다른 상업은행에게 지불할 수 있어야 하고, 인출에 대비해 충분한 양의 현금을 갖고 있어야 한다. 상업은행이 지급준비금 혹은 지폐을 너무 적게 갖고있고 매도가 용이치 않은 유동성이 부족한 자산을 갖고 있다면 문제가 될 수 있다. 펀더멘탈이 건강한 은행이라도 예금자의 지불 요구에 대응하지 못한다면 혼란이 발생한다.

유동성 문제를 해결하기 위해 상업은행은 일간으로 고객에게 지불해야될 금액을 예상하고 충분한 양의 유동성 높은 자산을 보유하고 있어야 한다. 이러한 자산은 일반적으로 보통 중앙은행 지급준비금이지만 국채라든가 기관 MBS도 가능하다. 은행이 필요 유동자산을 낮게 추정하였다면 다른 상업은행이나 기관투자자에게 빌릴 수도 있다. 상업은행은 최종대부자인 연준의 할인 창구(Discount Window)로부터 차입할 수도 있다. 이 마지막 옵션과 관련해서는 강력한 낙인효과가 있는데 은행에게 민간 부문의 누구도 대출하지 않을 정도로 은행이 심각한 곤경에 처해 있음을 시사하기 떄문이다. 할인 창구 대출은 상업은행에게 절대적으로 최종 대부자의 역할을 하게 된다.

은행이 하나 뿐인 세계와 은행이 두 개인 세계 두 가지 시나리오에서 지급이 어떻게 이루어지는 지 예를 보자.

<b>⒜ A World with only one bank</b>

<table>
    <caption>
        <h4>
            Alpha 은행 대차대조표
    	</h4>
    </caption>
    <colgroup>
        <col style="width:35%">
        <col style="width:15%">
        <col style="width:35%">
        <col style="width:15%">
    </colgroup>
    <tr style="background-color:whitd">
        <td style="text-align:center" colspan=2><b>자산</b></td> 
        <td style="text-align:center" colspan=2><b>부채</b></td> 
    </tr>
    <tr style="background-color:white">
        <td>Reserves</td>
        <td></td>
        <td>Equity</td>
        <td></td>
    </tr>
    <tr style="background-color:white">
        <td>loan to John</td>
        <td style="text-align:right">+＄1백만</td>
        <td>deposits to John</td>
        <td style="text-align:right">+＄1백만</td>
    </tr>
    <tr style="background-color:white">
        <td></td>
        <td></td>
        <td>sent to Tim</td>
        <td style="text-align:right">(＄1백만)</td>
	</tr>
    <tr style="background-color:white">
        <td></td>
        <td></td>
        <td>deposits to Tim</td>
        <td style="text-align:right">+＄1백만</td>
	</tr>
</table>

Alpha 은행만 존재하는 세상을 생각해보자. 농부 John이 Alpha 은행에 가서 ＄1백만의 대출을 받고, 이를 나무꾼 Tim에게 목재 값으로 지불하고자 한다. Alpha 은행은 John의 재정상태를 점검한 뒤 좋은 신용을 확인하고 대출을 해줬다. Alpha 은행은 몇 번의 타이핑으로 John의 은행 계좌에 ＄1백만을 입력했다. John은 은행 계좌에 접근하여 ＄1백만을 확인하고 이를 Tim에게 송부했다. 전세계에 은행은 Alpha 은행이 유일하기 때문에 Alpha 은행은 전산으로 John의 계좌에서 Tim의 계좌로 ＄1백만을 옮기기만 하면 된다. 오직 하나의 은행만 존재하는 세상에서는 모든 것이 은행의 대차대조표 내에서 이루어지기 때문에 유동성 문제는 발생하지 않는다.

<br>

<b>⒝ A World with two banks</b>

Alpha 은행과 Zed 은행이라는 두 은행이 존재하는 세상을 가정해보자. 농부 John은 Alpha 은행을 사용하고 나무꾼 Tim은 Zed 은행을 사용한다. John이 Alpha 은행에서 ＄1백만을 대출받은 뒤 이를 Zed 은행의 Tim의 계좌로 보내려고 한다. 이 때 Alpha 은행은 단순히 사내 전산에서 숫자를 조정하는 것이 아니라 Zed 은행에 실제로 돈을 보내야 한다. Alpha 은행은 ＄1백만의 중앙은행 지급준비금을 Zed 은행에 송부하고, Zed 은행은 이를 Tim의 계좌에 넣어준다.

<table>
    <caption>
        <h4>
            Alpha 은행 대차대조표
    	</h4>
    </caption>
    <colgroup>
        <col style="width:35%">
        <col style="width:15%">
        <col style="width:35%">
        <col style="width:15%">
    </colgroup>
    <tr style="background-color:whitd">
        <td style="text-align:center" colspan=2><b>자산</b></td> 
        <td style="text-align:center" colspan=2><b>부채</b></td> 
    </tr>
    <tr style="background-color:white">
        <td>Reserves</td>
        <td></td>
        <td>Equity</td>
        <td></td>
    </tr>
    <tr style="background-color:white">
        <td>loan to John</td>
        <td style="text-align:right">+＄1백만</td>
        <td>deposits to John</td>
        <td style="text-align:right">+＄1백만</td>
    </tr>
    <tr style="background-color:white">
        <td>reserves to Zed 은행</td>
        <td style="text-align:right">(＄1백만)</td>
        <td>John sent to Tim</td>
        <td style="text-align:right">(＄1백만)</td>
    </tr>
</table>



<table>
    <caption>
        <h4>
            Zed 은행 대차대조표
    	</h4>
    </caption>
    <colgroup>
        <col style="width:35%">
        <col style="width:15%">
        <col style="width:35%">
        <col style="width:15%">
    </colgroup>
    <tr style="background-color:whitd">
        <td style="text-align:center" colspan=2><b>자산</b></td> 
        <td style="text-align:center" colspan=2><b>부채</b></td> 
    </tr>
    <tr style="background-color:white">
        <td>Reserves</td>
        <td></td>
        <td>Equity</td>
        <td></td>
    </tr>
    <tr style="background-color:white">
        <td>reserves from Alpha 은행</td>
        <td style="text-align:right">+＄1백만</td>
        <td>deposits to Tim</td>
        <td style="text-align:right">+＄1백만</td>
    </tr>
</table>


Alpha 은행이 충분한 지급준비금을 갖고 있지 않다면 누군가에게 빌려야만 한다. Alpha 은행은 중앙은행 지급준비금을 Zed 은행에게 빌릴 수 있고, 이를 Tim을 대신하여 준비금을 바로 보낼 수 있다. Alpha 은행은 최종 대부자인 연준의 할인 창구를 통해 지급준비금을 빌릴 수도 있다. Alpha 은행은 MMF와 같은 비은행 주체로부터 빌릴 수도 있다. 비은행 주체들은 중앙은행 지급준비금은 없지만, 비은행 주체의 거래은행은 Alpha 은행에게 지급준비금을 보내 이 거래를 처리할 수 있다 .  Alpha 은행은 비은행 주체의 예금을 부채에 기록하고 중앙은행 지급준비금을 자산으로 기록한다.

***

상업은행은 돈을 무한히 만들어낼 수 있는 마법의 돈 나무처럼 보이지만 상업은행이 만들어낼 수 있는 돈의 규모는 한계까 있다. 이 한계를 규제와 수익성을 통해 형성된다. 역사적으로 은행들은 은행업 위기에 빠질 수 있기 때문에 엄격한 규제가 적용된다. 주기적인 정기 보고 외에도 초대형 은행은 매일 매일 은행 활동을 감시하는 사내 감독관이 있다. 손실을 흡수할 수 있는 자본 규모 대비 상업은행의 대차대조표 크기를 규제하는 레버리지 비율 규제가 있다. 예를 들면, 20배 레버리지 한도 규정 내에서는 ＄5의 자본을 가진 은행은 ＄100까지 자산을 보유할 수 있다. 레버리지 규제는 은행이 잠재적 손실을 충분히 감내할 수 있도록 한다.

상업은행의 신용창조는 가능한 투자 기회에 의해 제한된다. 은행의 주식 투자 부서는 투자로부터 높은 수익을 내고 싶기 때문에 은행이 높은 이자 수익을 얻는 투자를 하기를 원한다. 경제가 좋을 때 많은 차입자들이 수익성 좋은 프로젝트의 자금 조달을 위해 기꺼이 높은 이자를 지불하고자 하지만, 침체기에는 그런 기회가 확연히 줄어든다. 따라서 은행은 호황기에 최대한 많은 대출을 통해 더 많은 돈을 창조하고자 한다. 불황기에는 경제의 돈에 대한 수요가 감소하기 때문에 은행은 대출을 줄이고 통화 공급을 줄인다.

<br>

#### C. The Treasury

미국 재무부는 세금을 징수하고 국채를 발행한다. 재무부는 부채를 얼마나 발행할지 결정하지 않는다. 이는 연방 정부의 적자이며 의회가 결정한다. 의회는 연방 정부의 지출과 세수를 결정하는 법률을 제정하고, 지출과 세수의 차이를 재정적자라고 한다.

그러나, 재무부는 재정적자를 어떻게 조달할지 결정한다. 이 때문에 재무부는 수익률 곡선의 모양에 영향을 주게 되는데, 더 많은 장기 채권을 발행하기로 결정하면 수익률 곡선이 가팔라지고, 더 많은 단기채권을 발행하기로 결정하면 수익률 곡선이 평평해진다. 재무부의 부채 관리 전략의 가장 중요한 원칙은 가장 저렴한 비용으로 자금을 조달하여 납세자에게 제공하는 것이다. 재무부는 민간 부문의 요소를 고려한 자체 분석을 통해 재정 적자를 가장 저렴하게 조달할 수 있는 방안을 찾는다. 예를 들어 연준이 양적완화를 통해 장기 국채를 낮출 때 재무부는 장기 국채 발행량을 조절하여 장기 금리를 낮추는 데 일조한다.

재무부는 국채를 주기적이고 예측 가능한 속도로 발행하고자 하며 분기별로 규모와 주기를 소폭 조정한다. 이는 최근 몇 년동안 수조 달러에 달하는 연간 발행 규모 때문에 중요하다. 채권시장은 발행 규모가 예측 가능할 경우 신규 발행을 더 쉽게 소화할 수 있다. 시장을 놀래키면 수익률이 급등할 수 있고, 이는 안 좋을 수 있다. 매 분기 초 재무부는 예상되는 연방 지출 규모와 조세 수입, 부채 만기, 분기 말 규모 등을 고려하여 필요한 자금 조달 규모를 발표한다. 재무부는 5일 간의 지출을 커버할 수 있는 충분한 현금을 보유하고자 한다.

예상치 못한 부채 발행 규모를 조정해야할 때 재무부는 필요분 만큼을 단기 부채를 발행하여 조달한다. 이는 시장이 장기 채권보다는 단기 채권을 더 잘 소화하기 때문이다. 예를 들어 미 의회가 2020년 3월 ＄2.2조 규모의 CARES 패키지를 통과시켰을 때 재무부는 ＄1.5조를 만기 1년 미만 단기 국채(Bill)를 발행했다. 단기 국채는 ＄4조 이상을 지속적으로 롤오버 해야하는 MMF를 통해 쉽게 소화되었다. 한편 장기 국채 시장 참여자는 장기 시계를 가진 투자자들이며 단기 변화에 덜 민감하게 반응한다. 연기금, 보험사, 국부펀드 등을 포함한 이런 종류의 투자자들은 장기 국채 발행이 급증할 때 그것을 투자할만큼의 충분한 여유 자금을 갖고 있지 않다.

중앙은행의 지급준비금이나 은행 예금과 달리 재무부의 국채는 미국 정부의 신뢰를 담보로 발행된다. 중앙은행 지급준비금은 그들이 매입한 안전자산으로 의해 보증되며 이는 한 종류의 돈이 다른 종류의 돈으로 교환하는 것이다. 은행 예금은 이는 창조된 돈을 되돌리는 역할을 하는, 상환되어야 하는 대출로 담보된다. 재무부가 수조 달러의 국채를 발행하지만 그것을 상환한다는 계획은 없다. 대신, 아직 만기가 도래하지 않은(outstanding) 국채의 규모는 빠른 속도로 증가하고 있다. 재화와 서비스가 재무부가 찍어낸 돈(printing money)으로 구매되기 때문에 인플레이션을 상승시키는 영향을 갖고 있지만, 이는 물가를 상승시키는 수 많은 요소 중 하나일 뿐이다.

많은 시장 참여자들이 미국의 부채 규모가 증가하는 것을 보고 부채 위기가 임박했다고 한다. 그러나 일본처럼 GDP 대비 부채 규모가 미국 보다 높은 국가가 있고, 국채 발행량이 급증해도 국채 수익률은 가차없이 하락했다. 재무부가 발행할 수 있는 부채(국채)의 양에는 분명한 제한이 있지만, 그 한도가 몇인지는 분명하지 않다.

<br>

<br>

### Chapter 3 - The Shadow Banks

<br>

#### Primary Dealers

<br>

#### Money Market Mutual Funds(MMF)

<br>

#### Exchange Traded Funds(ETF)

<br>

#### Mortgage REITs(mREITs)

<br>

#### Private Investment Funds

<br>

#### Securitization

<br>

<br>

***

## Section Ⅲ. Fed Watching

### Chapter 8 - Crisis Monetary Policy

전통적인 통화정책에서는 중앙은행이 상업은행의 최종 대부자이며, 중앙은행이 단기 금리를 조절하여 경제 활동에 영향을 준다. 재무적으로 건강한 은행이 감당할 수 없을 만큼의 갑작스러운 인출이 발생했을 때 중앙은행이 개입하여 패닉을 방지한다. 경제가 침체에 빠지면 중앙은행은 금리를 낮춰 소비와 투자를 진작시키고 경제가 과열되면 금리를 올려 경제 활동을 억누른다.

그러나, 기준금리가 이미 0% 수준일 때 그림자 은행 시스템에 패닉이 발생하면 중앙은행이 경제 활동에 어떻게 영향을 줄 수 있을까? 이는 미 연준이 2008년 금융위기와 2020년 COVID-19 팬데믹 때 마주했던 상황이다. 이에 대응해 연준은 새로운 통화정책 도구를 창안해냈다.

#### Democratizing the Fed

연준은 상업은행이 금융 시스템의 지배적인 위치에 있을 때 설립되었고, 연준의 관심은 자연스럽게 상업 은행에 집중되었다. 연준은 국내 상업은행을 규제하고 상업은행이 성실하게 운영되고 상업은행에 할인창구를 통해 긴급 대출을 지원하여 예상하지 못한 유동성 부족을 해결해 중ㅆ다. 그러나 그림자 은행과 역외 은행업의 성장은 연준의 활동 /관리 영역을 벗어난 곳에서 금융 활동이 점차 확대됨을 의미했다. 2008년에 그림자 은행과 역외 은행업에서 패닉이 발생하였다. 금융 시스템을 구원하기 위해 연준은 [연준법 13조 3항](https://www.bok.or.kr/portal/bbs/P0002223/view.do?nttId=10057440&menuNo=200082)에 의거한 다양한 대출 프로그램을 활용해 누구에게나 돈을 빌려줄 수 있게 했다.

2008년 그림자 은행업 세계는 무너지고 있었다. 프라이머리 딜러(primary dealer), MMF, 증권화 상품, 헤지펀드에 대한 인출이 지속되었다. 상업은행도 그림자 은행에 깊게 관여하고 있었기 때문에 안전하지 못했다. 그들은 그림자 은행의 많은 계약에 대한 보증을 섰고 그들에게 많은 돈을 대출해줬었다. 주가지수는 문제에 민감하게 반응하고 붕괴했다. 전반적인 금융 시스템의 붕괴였다.

연준은 핵심 그림자 은행 업종들을 포함한 거래상대방을 확장하며 위기를 대처했다. 프라이머리 딜러를 위한 Primary Dealer Credit Facility, MMF를 위한 Money Market Investor Liquidity Facility, 그리고 증권화 상품을 위한 Asset-Backed Commercial Paper and Term Auction Securitization Facility, 심지어 대마불사 은행들을 위한 특별 대출 등이 여기에 해당된다. 연준은 상업은행의 최종 대부자일뿐만 아니라 다른 그림자 은행들을 위한 최종 대부자가 되었다. 

비슷한 위기가 해외의 역외 달러 은행 시스템에서도 일어났다. 미국 상업은행과 그림자 은행이 서브프라임 모기지와 관련된 투자에서의 손실로 붕괴된 것처럼 해외 상업은행도 동일 투자건으로 위기에 빠졌다. 유럽 은행들은 미국 모기지 관련 자산에 대규모 투자를 했었고 손실 때문에 잠재적 지불불능 상태였다. 그러나 해외 은행은 미국에 위치하지 않았기 때문에 연준의 권한에서 더욱 멀어졌다. 해외 은행을 연준이 구제하는 것은 좋지 않아보일 수 있었다. 그러나 해외 은행들의 미국 단기 금리를 어지러운 수준까지 밀어 올렸기 때문에 미국 시장에 미치는 영향은 부인할 수 없었다. 

시장 참여자는 은행간 3개월 LIBOR 금리와 예상되는 향후 3개월 기준금리인 3개월 Overnight Index Swap(OIS)의 금리 사이의 차이인 [Libor-OIS spread ](https://www.risk.net/definition/libor-ois-spread)를 통해 금융시장 스트레스를 측정한다. 스프레드가 확대된다는 것은 시장 금리가 연준의 정책 금리보다 높다는 의미이며 금융시장내 문제가 있다는 의미이다. 평온한 시기에는 0%p보다 살짝 높은 수준이지만 2008년 글로벌 금융위기 시기에는 4%p 근처까지 상승하기도 했다. 투자자들은 해외 은행에 돈을 빌려주는 것을 우려했고 해외 은행은 3개월 차입에도 높은 금리를 제시해야만 했다.

연준은 일부 해외 은행에도 중앙은행 스왑 라인을 통해 대출해주기로 결정했다. 연준이 해외 중앙은행에 달러를 빌려주면, 해외 중앙은행은 관할 상업은행에게 달러를 빌려주는 형식이었다. 스왑 라인은 글로벌 달러 부족을 해결하였지만, 연준은 미국 내·외에서 글로벌 달러 시스템의 후원자가 되었다.

결과적으로 금융 시스템이 안정되었고 연준이 상업은행과 그림자 은행, 그리고 해외 은행의 최종 대부자 역할을 하는 선례를 남겼다. 2020년 COVID-19 패닉 기간에 2008년의 연준법 13조 3항을 활용한 선례를 더욱 확고히 하였다. 한 걸음 더 나아가 연준은 민간 비즈니스 부문의 최종대부자 역할까지 하였다.

2020년 [3월](https://www.federalreserve.gov/newsevents/pressreleases/monetary20200323b.htm)과 [4월](https://www.federalreserve.gov/newsevents/pressreleases/monetary20200409a.htm), 상업은행을 통한 소규모 기업 지원과 자본시장을 활용한 대기업 지원이 가능한 새로운 정책 기구(facilities)를 발표했다. 발행시장을 통한 회사채 매입 기구(Primary Market Corporate Credit Facility, [PMCCF](https://www.federalreserve.gov/monetarypolicy/pmccf.htm))와 유통시장을 통한 회사채 매입기구(Secondary Market Corporate Credit Facility, [SMCCF](https://www.federalreserve.gov/monetarypolicy/smccf.htm))이다. 또한 연준은 실물시장 지원을 위해 SPV를 설립하여 상업은행의 소규모 비즈니스 대출을 매입하는 [Main Street Lending Program](https://www.federalreserve.gov/monetarypolicy/mainstreetlending.htm)을 운영하였다. 상업은행에 유동성을 공급하던 전통적인 역할을 넘어 미국의 기업들에게도 유동성을 지원한 것이다. 개인을 제외한 거의 모든 사람들이 연준 대차대조표에 접근할 수 있게 된 것이다.

연준의 대출 범위 확장과 관련하여 모랄 해저드를 발생시킬 수 있다는 지적이 많다. 2008년 GFC 당시 많은 평론가들이 잘못된 의사결정을 한 투자자들을 구원하는 것은 투자자들이 연준이 구원해줄 것이라 생각할 것이기 때문에 더 나쁜 투자 결과를 초래할 수 있다고 지적했다. 이러한 지적은 리만 브라더스 파산에 일정 부분 기여했다. 리만 브라더스의 파산은 모랄 해저드를 걱정했던 사람들이 존재하지 않을 만큼 금융 자산의 끔찍한 하락을 야기했다.

연준은 규제를 통해 모럴 해저드 이슈를 해결하기로 결정했다. 위기 이후 연준과 전세계 규제당국은 은행에 대한 규제를 강화했고 은행들은 이전 만큼 위험을 떠안을 수 없게 되었고, 은행들은 연준의 또다른 구제의 필요성이 낮아졌다. 이러한 조치는 COVID-19 팬데믹에도 미국내 상업은행이 거의 이슈 없이 운영된 것으로 미루어 보아 성공적인 것으로 평가되고 있다.

새로운 규제는 프라이머리 딜러와 MMF 같은 주요 그림자 은행 개혁에도 적용되었다. COVID-19 기간에 프라임 MMF만 약간의 문제를 경험했을 뿐 별다른 문제는 없었다. 그러나 모기지 리츠(mREITs), ETF, 사모 투자 펀드와 같은 다른 그림자 은행은 강화된 규제의 대상이 아니다. 많은 부분이 팬데믹 기간 동안 큰 손실을 기록했고 연준의 조치로 구제되었다.

<br>

<br>

### Chapter 9 - How to Fed Watch

연준 의사결정의 중요도가 커지며 "Fed Watchers"<span style="color:blue">(Fed Watcher에 대한 적절한 한국어 표현은 아직까지 없는 것 같아 그냥 영어로 쓰기로 함)</span> 라는 영역이 성장하게 되었다. 이들은 흔히 연준에서 수년간 일하다가 연봉을 두 배 이상 튀겨 투자은행에 전략가 혹은 이코노미스트 타이틀을 갖고 일하는 사람들<span style="color:blue">(대표적으로 Credit Suisse의 Zoltan Pozsar)</span>이다. 이들은 주로 연준의 행동 분석하고 분석 결과를 부유한 리테일 고객 혹은 대형 기관 투자자들에게 전달한다. CNBC나 블룸버그에 나와 미래 연준의 행동에 대한 예측을 피력하기도 한다. 이따금씩 좋은 통찰력을 보여주기도 하지만 그들이 하는 대부분의 일은 옳은 정보와 훈련된 사람이라면 누구나 할 수 있다. 이번 장에서 Fed Watching의 기본을 알려주겠다.

2008년 금융위기 이전에 연준의 행동은 예측하기 매우 어려웠다. 실제로 시장은 연준의 깜짝 이자율 결정에 당황하기도 했다. 이런 일은 더 이상 일어나기 힘들다. 이제 시장은 연준의 행동을 정확하게 예측한다. 이것은 연준이 연준의 생각을 시장과 투명하게 공유하려고 노력하기 때문이다. Fed Watcher의 기본은 연준이 최근에 무슨 생각을 하고 있는지 지속적으로 추적하고 연준이 미래에 어떻게 행동할지 예측하는 것이다. 앞으로 연준이 시장과 소통하는 채널들을 리뷰해보겠다.

<table>
    <caption>
        <h4>
            Fed Communication and Importance
    	</h4>
    </caption>
    <colgroup>
        <col style="width:70%">
        <col style="width:30%">
    </colgroup>
    <tr>
        <td >FOMC Statement</td> 
        <td style="text-align:center">★★★</td> 
    </tr>
    <tr>
        <td >FOMC Press Conference</td> 
        <td style="text-align:center">★★★</td> 
    </tr>
    <tr>
        <td >FOMC Minutes</td> 
        <td style="text-align:center">★★★</td> 
    </tr>
    <tr>
        <td >FOMC "Dot Plot"</td> 
        <td style="text-align:center">★★★</td> 
    </tr>
    <tr>
        <td >Fed Official Speeches</td> 
        <td style="text-align:center">★★☆</td> 
    </tr>
    <tr>
        <td>Fed Intervies</td>
        <td style="text-align:center">★★☆</td>
    </tr>
    <tr>
        <td>Desk Operating Statements</td>
        <td style="text-align:center">★★☆</td>
    </tr>
    <tr>
        <td>Fed Balance Sheet</td>
        <td style="text-align:center">★★☆</td>
    </tr>
    <tr>
        <td>Fed Research</td>
        <td style="text-align:center">★☆☆</td>
    </tr>
    <tr>
        <td>Fed Surveys</td>
        <td style="text-align:center">★☆☆</td>
    </tr>
</table>

<br>

#### FOMC Statement

#### FOMC Press Conference

#### FOMC Minutes

#### FOMC "Dot Plot"

#### Federal Reserve Speeches

#### Fed Interviews and Congressional Testimonies

#### Desk Operating Statements

<br>

#### Fed Balance Sheet

Fed Watcher들의 연준 대차대조표가 연준의 중요 정책 도구가 되어가며 연준 대차대조표에 대한 관심이 점점 커지고 있다. Fed Watcher들은 연준 대차대조표가 증가하는지, 만약 그렇다면 어떤 자산이 증가를 이끄는지 알고싶어 한다. 이러한 정보를 이용해 금융 시장에 어떤 일이 발생할지 예측한다. 일반적으로 연준이 대차대조표를 확장하면 금리는 낮아지고 주식 시장은 상승한다고 가정한다. 일부 신용 기구의 높은 참여율은 시장 일부 부분에 스트레스 정도를 알려주는 지표가 될 수 있다.

연준은 대차대조표를 매주 목요일 오후에 [The Fed - Factors Affecting Reserve Balances - H.4.1](https://www.federalreserve.gov/releases/h41/)를 통해 발표한다. <span style="color:blue">우리나라 시간으로는 금요일 새벽에 확인할 수 있다.</span> 이를 통해 상업은행이 갖고 있는 은행 지급준비금 규모, 연준이 보유하고 있는 국채과 기관 MBS 증권의 규모, 그리고 특별 연준 신용 기구의 규모와 해외 공식 계좌를 대신에 보유하고 있는 증권의 규모 등을 알 수 있다. 

<b>(1) Reserves and Securities Holdings</b> 

지급준비금<span style="color:blue">(부채 항목)</span>과 증권 보유 내역<span style="color:blue">(자산 항목)</span>은 서로 동전의 양면가아서 지급준비금은 연준이 국채나 MBS를 매수하면서 생성된다.  <span style="color:blue">따라서 부채 항목 중 Reserve가 시장의 유동성 수준을 가늠할 수 있는 지표가 된다. </span> 

<b>(2) Fed Credit Facilities</b>

시장 스트레스가 심각할 때 연준은 시장의 특정 부문을 지원하기 위해 특별 신용 창구를 운영한다. 2020년 COVID-19 패닉 당시 연준은 2008년 금융위기 시기의 창구에 더해 몇 가지 신용 창구를 추가적으로 운영했다. 이러한 기구를 통해 관리되는 대출 규모는 매주 공개된다. 이 창구들의 사용 정도에 따라 시장 참여자들은 시장 압박의 정도를 가늠할 수 있다. 예를 들어, 해외 중앙은행과의 FX스왑 잔액 규모는 4월에 거의 ＄5,000억 증가했다. 같은 기간 동안 민간 시장의 FX스왑 베이시스는 폭등하여 달러는 상당한 강세를 보였다. 그러나 FX 스왑 잔액 규모는 역외 달러 조달 스트레스가 완화됨에 따라 4월 이후 감소하기 시작했다. 이는 COVID-19 패닉 기간에 역외 달러 조달 시장에 심각한 스트레스가 있었음을 의미하고, 이러한 스트레스는 연준의 약 ＄5,000억 규모의 유동성 공급으로 해소되었다.

<b>(3) FIMA Accounts</b>

연준은 해외 중앙은행이나 해외 정부 혹은 국제 기구 등 해외 공식 부문 고객에게 크게 두 가지 은행 서비스를 제공한다. 첫째는 담보된 "예금계좌"이고 둘째는 유가증권에 대한 수탁 서비스이다. 담보돤 예금계좌는 레포(repo) 거래로 구조화되있고, 해외 공식 부문 고객에게 연준에 레포(대여) 형식으로 연준에 돈을 맡길 수 있다. 국채를 담보로 갖고 있는 예금 계좌이다. 많은 해외 공식 부문 고객이 그들의 달러 준비금을 국채의 형태로 갖고 있어 이자를 수취한다. 연준은 이러한 증권의 수탁사로 작동할 수 있다.

많은 해외 공식 부문 고객은 그들의 달러 준비금을 연준에 예치하는 것을 선호하는데 연준은 위험이 없는 거래상대방이기 때문이다. 그러나 일부는 달러 준비금을 상업은행을 통해 보유하기도 한다. 상업은행이 더 종합적인 상품을 제공하고 높은 금리를 제공하거나 지정학적 위험이 증가할 때 분산하기 위함이다. 시장 참여자들은 해외 중앙은행의 미국채 보유량이 감소하고, 즉 국채를 매도하고 외환시장에 개입할 때 주목한다. 

<span style="color:blue">2022년 9월 기준으로 중국의 미국채 보유량 감소가 지속되고 있는데, 중국이 보유하고 있는 미국채를 매도해 위안화 가치 하락을 방어하고 있다는 해석이 있다. [관련 기사: 미국 국채 덜어내는 중국...보유액 12년래 최저 - 이투데이 (etoday.co.kr)](https://www.etoday.co.kr/news/view/2164075)</span>



#### Desk Surveys

#### Federal Reserve Research

#### Federal Reserve Surveys

<br>

#### The New Framework

2020년 8월 27일, 잭슨홀 미팅에서 파월 연준 의장은 연준의 새로운 통화정책 프레임워크를 발표했다. 이 프레임워크는 연준 통화정책의 두 가지 큰 변화가 있었는데, '평균물가목표제'와 '비대칭적 완전고용'이 그것이다.

<b>(1) Asymetry in Maximum Employment</b>

완전고용은 연준의 이중 책무 중 하나이다. 연준의 전략 성명문에서 정책은 완전 고용 수준으로부터 벗어난 정도에 영향을 받는다고 하였다. 이는 고용이 완전 고용 수준을 초과할 경우 정책 금리를 인상할 수 있고, 고용이 완전 고용 수준을 밑돌경우 금리를 인하할 수 있음을 의미한다. 새로운 전략 성명에서 연준은 완전 고용 수준으로부터 부족한 부분에 대한 평가에 의해 정책금리를 결정할 것이라고 밝힌다. 이는 연준이 추정한 완전 고용 수준 이상일 경우에 연준이 기준금리 인상을 하지 않을 수 있음을 의미한다.

파월 의장은 연설에서 이러한 변화는 완전 고용 수준을 추정하기 어렵고 필립스 곡선(Phillips curve)이 평탄화 되었기 때문이라고 밝혔다. 필립스 곡선은 실업률과 물가상승률 사이의 관계에 대한 개념이며 낮은 실업률이 물가상승을 야기한다는 것이다.

인플레이션은 경제가 완전 고용 수준을 넘어설 때 상승하곤 한다. 그러나 최근에 실업률과 인플레이션 사이의 관계가 매우 약해졌다. 2019년 실업률은 수십년간 최저 수준인 3.5%까지 하락했음에도 물가상승률은 지속적으로 2%를 하회했다.

이는 완전 고용 수준이 연준이 생각하는 것보다 높거나 고용과 인플레이션 사이의 관계가 바뀌었을 가능성을 의미한다. 고용 데이터를 보았을 때 연준은 더 이상 이전 프레임워크를 적용할 수 없다. 그러므로 연준은 낮은 실업률이 더 이상 긴축적인 통화정책의 요인이 아니라고 말한다.

<b>(2) Average Inflation Targeting</b>

연준의 두 번째 책무는 물가 안정이며, 2% 수준의 개인소비지출(PCE) 물가 지수가 2% 수준에 유지되도록 하는 것으로 알려져있다. 지난 수십년간 PCE는 안정적으로 연준의 목표치를 하회했고, 이는 연준이 물가 안정 의무를 수행하는데 있어 프레임을 변화하는데 기여했다.

연준은 공식적으로 평균 물가 목표제(Average Inflation Targeting, AIT)를 도입하였다. 이는 이전에 인플레이션 목표치를 하회한 만큼 미래에 물가가 인플레이션 목표치를 상회하는 것을 용인해 평균적으로 2%의 물가를 달성하는 것을 목표로 함을 의미한다. 이는 연준이 2%를 상회하는 인플레이션을 허용할 수 의마하고, 이전 프레임워크에서는 허용되지 않던 것이다.

비평가들은 연준이 과거 수년간 2% 인플레이션 목표를 충족시키지 못하였고, 이전의 부족분을 보상할 만큼 인플레이션이 높은 레벨이 될 것 같지 않다고 지적했다.  연준이 기준금리를 수차례 인상해도 PCE 물가는 종종 2%를 상회하기도 했다. 만약 연준이 금리를 전혀 인상하지 않았다면 인플레이션은 2%를 상회하는 수준을 지속했을 수 있다. 연준의 새로운 프레임워크에 대한 평가에는 향후 수년이 필요하겠지만 채권 시장은 연준에게 일정 부분 신뢰를 보내는 것 같다. 새로운 프레임워크가 발표되고 미국채 수익률 곡선은 가팔라졌는데, 이는 일부 시장 참여자들이 미래에 높은 인플레이션을 예상한다는 것을 의미한다.

인플레이션은 대체로 정치적인 선택이다. 어느 정부라도 대규모 재정 지출로 인플레이션을 만들 수 있고, 어느 정부라도 대규모 세금 인상으로 디플레이션을 만들 수 있다. 연준은 장기간 름리를 낮게 유지할 것을 선택했고, 연방 정부는 대규모 재정적자 지출을 지속할 것이며 따라서 미래에 인플레이션이 높을 가능성은 매우 높다.

<span style="color:blue">(현재를 기준으로 과거를 평가하는 태도는 매우 좋지 못하나...) 2021년 잭슨홀 미팅에서 파월은 "인플레이션은 일시적(transitory)이다"라고 했다. 그런데 연임이 확정 되자마자 인플레이션을 잡으려는 의지를 드러내기 시작했다. 이러한 태도 변화에 대해 매우 정치적인 행동이라는 비판이 많다. 2022년 잭슨홀 미팅에서는 8분 남짓의 짧은 연설에서는 폴 볼커를 들먹이며 "인플레이션 파이터"로서의 강력한 의지를 드러냈다.</span>



