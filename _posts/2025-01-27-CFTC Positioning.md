---
title: CFTC 포지셔닝(Positioning)
date: 2025-01-27
categories: 
- quant-idea
tags: [position]
comments: True
use_math: True
---



CFTC 포지션을 활용하는 아이디어



선물 투자자를 크게 두 부류로 나눌 수 있다. 한 집단은 Hedger, 또 다른 한 집단은 Speculator. 원유 시장을 예로 들면 Hedger는 정유회사 혹은 유틸리티 회사(서로 입장이 반대), Speculator는 IB, 헤지펀드 등 투기적 목적을 가진 세력이라고 볼 수 있다. 

일반적으로 Hedger들은 가격 불확실성 제거를 위한 비용을 지불해가며 Hedge 포지션을 만들어야 하고, 이러한 Hedging 수요를 Speculator들이 대응함으로써 비용만큼을 벌어가는 역학관계로 시장을 바라본다. Hedger들은 Short 포지션이 일반적인데, 여기서는 Hedger들의 Hedging Pressure에 주목해본다. 

Hedging Pressure가 증가할수록 Hedger들의 리스크가 Speculator로 전이되며, 더 많은 리스크가 전이될수록 Speculator들에게 더 높은 수익 기회가 생긴다고 생각할 수 있다. 그런데, Hedger들이 더 많이 Hedging할수록 해당 기초자산의 향후 성과는 나빠지는 경향이 관찰되기도 한다. 이는 Hedger들이 해당 시장에 대한 이해가 Speculator들 보다 더 높은 경향이 있어 Hedging 수요의 증가는 Hedger들이 향후 기초자산의 가격하락에 대비한 결과로 해석하는 경우가 있다. 



CFTC는 1995년부터 포지션 데이터를 무료로 제공하였고, 좀 더 세분화된 투자자 포지션 데이터는 2006년부터 제공되기 시작했다. 1995년 3월 21일 데이터부터 무료로 제공되는 COM 레포트에서 CFTC는

1. 선물 거래를 헤지 목적으로 사용하는 투자자(Hedger)의 경우 Commercial로 분류하고
2. 반면 Speculators는 Non-Commercial로 분류한다.

TFF 보고서는 2006년 6월 13일 데이터부터 발표되는데, 투자자 분류는 다음과 같다.

1. Dealer / Intermediary (DI): Hedger
2. Asset Manager / Institutional(AI): Speculator
3. Leverage Funds(LF): Speculator



Hedger들의 Hedging Pressure 변화는 반대 포지션인 Speculator의 받아주는 물량 변화로 추적할 수 있다. 원자재 포지션의 경우 COM 레포트의 Non-Commercial의 순매수 포지션을 미결제약정으로 나눈 비율을 사용할 수 있다. 주식이나 FX는 TFF 레포트의 AI와 LF 의 순매수 포지션의 합을 미결제약정으로 나눈 비율을 사용할 수 있다. 채권은 AI의 순매수 포지션의 합을 미결제약정으로 나눈 비율을 사용할 수 있다. 채권의 경우 Leverage Funds들은 베이시스 트레이드에 선물을 활용할 가능성이 높기에 제외한다.

| 자산군 | 보고서 | Hedging Pressure Proxy                      |
| ------ | ------ | ------------------------------------------- |
| 원자재 | COM    | Non-Commercial Net Position / Open Interest |
| 주식   | TFF    | (DI + AI) Net Position / Open Interest      |
| 외환   | TFF    | (DI + AI) Net Position / Open Interest      |
| 채권   | TFF    | AI Net Position / Open Interest             |



기초자산마다 거래되는 선물의 양이 다르고, Hedger와 Speculator의 구성도 다르다. 각 기초자산별 Hedging Pressure의 최근 값이 장기 평균보다 증가하는지, 감소하는지를 모니터링할 수 있다. 단, CFTC 보고서의 날짜는 매주 화요일의 포지션 정보를 의미하고, 보고서는 보통 해당 주 금요일에 발표되므로 약 4일 정도의 Lag가 있음에 유의해야 한다.
