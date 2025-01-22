---
title: 선물(Futures) Roll Yield
date: 2025-01-20
categories: 
- derivatives
tags: [futures, roll yield]
comments: True
use_math: True
---

선물 Roll과 관련된 주요 날짜(Date)들을 정리하면 아래 표와 같다.

|Date|설명|
|----|----|
|First Trade Date|계약에 대한 거래가 시작되는 날짜|
|Last Trade Date|계약에 대한 거래가 종료되는 날짜|
|Settlement Date|계약에 대한 최종 정산가격이 결정되는 날짜|
|First Notice Date|실물 인도가 할당되었다는 통지를 받는 첫 번째 날짜|
|Last Notice Date|실물 인도가 할당되었다는 통지를 받는 마지막 날짜|
|First Delivery Date|배송을 완료하는 첫 번째 날짜|
|Last Delivery Date|배송을 완료하는 마지막 날짜|

참고로 블룸버그에서 관련 날짜를 조회하는 기능은 "EXS"이다.

다양한 날 중 선물거래 Roll과 관련되어 특히 중요한 날은 최초통보일과 최종거래일이다.

**최초통보일(First Notice Date, FND)**
선물 계약을 구매한 투자자가 해당 계약의 기초자산이 실물인수 될 수 있다고 통보받는 최초 날짜
최초통보일은 일반적으로 실물인도월의 첫 번째 영업일 기준 1-3일 전
대부분의 선물 투자자는 실제 상품 인도를 원하지 않기 때문에 **최초통보일 전에 포지션을 청산**

**최종거래일(Last Trade Date, LTD)**

실물을 인도하는 미국 국채 선물(TY)의 경우 최초통보일(FND)이 최종거래일(LTD)보다 빠르고
실물을 인도하는 WTI 선물(CL)의 경우 최초통보일(FND)이 최종거래일(LTD)보다 느리다.
실물을 인도하지 않는 S&P500 e-mini 선물(ES)같은 경우 최초통보일(FND), 최종거래일(LTD), First Delivery Date, Last Delivery Date가 모두 같다.

선물 Roll-over는 최초통보일과 최종거래일 중 빠른 날을 기준으로 2거래일 전에 거래를 종료하는 것이 일반적이다.
그렇게 함으로써 아웃 거래나 오류가 있는 경우 거래자는 FND 이전에 문제를 해결할 수 있다.


Futures Return = Spot Return + Excess Benefit or Cost of Owning the Underlying Asset
으로 표현할 수 있다. [^1]
[^1]: Deconstructing Futures Returns: The Role of Roll Yield, Campbell White Paper Series (February 2014) 참고

Roll Yield는 선물 수익률과 현물 수익률의 차이로 정의한다.
Roll Yield = Futures Returns - Spot Returns
즉, Roll Yield는 기초자산을 보유함으로써 생기는 초과 이익 혹은 비용이다. S&P500의 경우 Roll Yield는 배당수익률(이익)과 조달 비용(Financing Costs, 비용)이라고 생각할 수 있다.

주요 자산군의 효용과 비용을 정리하면 아래와 같다.

|자산군|효용|비용|
|------|----|----|
|채권|쿠폰|조달 비용|
|외환|해외 예금 금리|국내 예금 금리|
|주식|배당|조달 비용|

S&P500의 경우 배당수익률이 조달 비용보다 낮으면 Roll Yield < 0 이 된다. 배당수익률은 변동성이 크지 않으므로 조달 비용, 즉 시장 금리가 Roll Yield에 중요한 역할을 하게 된다.

Roll 시점 선물의 기간 구조(term structure)는 Roll Yield와 관련이 있다.
Contango[^2]의 경우 Roll로 인한 비용이 발생하게 되고(Roll Adjustment < 0)
Backwardation[^3]의 경우 Roll로 인한 수익이 발생하게 된다(Roll Adjustment > 0).

[^2]: Continuation에서 유래. 거래를 연장하거나 다음으로 이어가는 것
[^3]: Backward에서 유래. 가격이 현재보다 뒤로(낮게) 이동하는 현상
