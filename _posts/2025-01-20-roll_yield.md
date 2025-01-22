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
