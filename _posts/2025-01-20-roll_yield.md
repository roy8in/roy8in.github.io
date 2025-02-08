---
title: 선물(Futures) Roll Yield
date: 2025-01-20
categories: 
- derivatives
tags: [futures, roll yield]
comments: True
use_math: True
---





### 블룸버그 선물 티커

#### 기초자산에 따른 티커

|     기초자산     | 티커 |                             설명                             |
| :--------------: | :--: | :----------------------------------------------------------: |
|     미국 2년     |  TU  | <span style="color:blue; font-weight:bold;" >T</span>reasury <span style="color:blue; font-weight:bold;">U</span>ltra short |
|     미국 5년     |  FV  | treasury <span style="color:blue; font-weight:bold;" >F</span>i<span style="color:blue; font-weight:bold;">V</span>e-year |
|    미국 10년     |  TY  | <span style="color:blue; font-weight:bold;" >T</span>reasury <span style="color:blue; font-weight:bold;">Y</span>ear |
| 미국 Ultra 10년  | UXY  | <span style="color:blue; font-weight:bold;" >U</span>ltra <span style="color:blue; font-weight:bold;">X</span><span style="color:blue; font-weight:bold;">Y</span>ield |
|    미국 20년     |  US  | treasury <span style="color:blue; font-weight:bold;" >U</span>ltra long-term <span style="color:blue; font-weight:bold;">S</span>ecurities |
|    미국 30년     |  WN  |                              ?                               |
|     독일 2년     |  OE  | <span style="color:blue; font-weight:bold;" >O</span>bligation <span style="color:blue; font-weight:bold;">E</span>uro |
|    독일 10년     |  RX  | <span style="color:blue; font-weight:bold;" >R</span>enten <span style="color:blue; font-weight:bold;">X</span> |
|    독일 30년     |  UB  | <span style="color:blue; font-weight:bold;" >U</span>ltra <span style="color:blue; font-weight:bold;">B</span>und |
|    영국 10년     | "G " |   <span style="color:blue; font-weight:bold;">G</span>ilt    |
|   프랑스 10년    | OAT  | <span style="color:blue; font-weight:bold;" >O</span>bligaions <span style="color:blue; font-weight:bold;">A</span>ssimilables du <span style="color:blue; font-weight:bold;">T</span>resor |
|    일본 10년     |  JB  | <span style="color:blue; font-weight:bold;" >J</span>apanese <span style="color:blue; font-weight:bold;">B</span>ond |
|   캐나다 10년    |  CN  | <span style="color:blue; font-weight:bold;" >C</span>a<span style="color:blue; font-weight:bold;">N</span>ada |
|  이탈리아 10년   |  IK  | <span style="color:blue; font-weight:bold;" >I</span>taly <span style="color:blue; font-weight:bold;">K</span> |
|  S&P 500 E-mini  |  ES  | <span style="color:blue; font-weight:bold;" >E</span>-mini <span style="color:blue; font-weight:bold;">S</span>&p 500 |
|    Nasdaq 100    |  NQ  | <span style="color:blue; font-weight:bold;" >N</span>asda<span style="color:blue; font-weight:bold;">Q</span> 100 |
|    Dow E-mini    |  DM  | <span style="color:blue; font-weight:bold;" >D</span>ow <span style="color:blue; font-weight:bold;">E</span>-mini |
|    Nikkei 225    |  NK  | <span style="color:blue; font-weight:bold;" >N</span>i<span style="color:blue; font-weight:bold;">K</span>kei 225 |
|      TOPIX       |  TP  | <span style="color:blue; font-weight:bold;" >T</span>o<span style="color:blue; font-weight:bold;">P</span>ix |
|     FTSE 100     | "Z " |                              ?                               |
|   EuroStoxx 50   |  VG  |                              ?                               |
|   MSCI Emg Mkt   | MES  | <span style="color:blue; font-weight:bold;" >M</span>sci <span style="color:blue; font-weight:bold;">E</span>merging market<span style="color:blue; font-weight:bold;">S</span> |
|  FTSE China A50  |  XU  |                              ?                               |
|    S&P/TSX 60    |  PT  | s&<span style="color:blue; font-weight:bold;" >P</span>/<span style="color:blue; font-weight:bold;">T</span>sx 60 |
| Stoxx Europe 600 | SXO  | <span style="color:blue; font-weight:bold;" >S</span>to<span style="color:blue; font-weight:bold;">X</span>x eur<span style="color:blue; font-weight:bold;">O</span>pe 600 |
|       WTI        |  CL  | <span style="color:blue; font-weight:bold;" >C</span>rude<span style="color:blue; font-weight:bold;"> L</span>ight |
|        금        |  GC  | <span style="color:blue; font-weight:bold;" >G</span>old<span style="color:blue; font-weight:bold;"> C</span>ontract |
|        은        |  SI  |  <span style="color:blue; font-weight:bold;" >SI</span>lver  |
|       구리       |  HG  | <span style="color:blue; font-weight:bold;" >H</span>igh<span style="color:blue; font-weight:bold;"> G</span>rade copper |
|   유로존 유로    |  EC  | <span style="color:blue; font-weight:bold;" >E</span>uro <span style="color:blue; font-weight:bold;">C</span>urrency |
|     일본 엔      |  JY  | <span style="color:blue; font-weight:bold;" >J</span>apanese <span style="color:blue; font-weight:bold;">Y</span>en |
|    호주 달러     |  AD  | <span style="color:blue; font-weight:bold;" >A</span>ustrian <span style="color:blue; font-weight:bold;">D</span>ollar |
|   영국 파운드    |  BP  | <span style="color:blue; font-weight:bold;" >B</span>ritish <span style="color:blue; font-weight:bold;">P</span>ound |



#### 선물 계약 만기에 따른 티커

| 만기(월) | 티커 |
| :------: | :--: |
|    1     |  F   |
|    2     |  G   |
|    3     |  H   |
|    4     |  J   |
|    5     |  K   |
|    6     |  M   |
|    7     |  N   |
|    8     |  Q   |
|    9     |  U   |
|    10    |  V   |
|    11    |  X   |
|    12    |  Z   |

이는 선물 거래의 역사적인 기원과 관련이 있다. 1-12월까지의 각 월을 알파벳 순서로 대체하면서 몇몇 문자는 제외한다.

- A, B, C, D, E는 제외
- I, L은 숫자 1과 유사하여 제외
- O, P는 숫자 0과 유사하여 제외
- R, S, T, W, Y는 제외





### 선물 관련 날짜

선물 Roll과 관련된 주요 날짜(Date)들을 정리하면 아래 표와 같다.

|Date|설명|
|:--:|:--:|
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

> 선물 계약을 구매한 투자자가 해당 계약의 기초자산이 실물인수 될 수 있다고 통보받는 최초 날짜
> 최초통보일은 일반적으로 실물인도월의 첫 번째 영업일 기준 1-3일 전
> 대부분의 선물 투자자는 실제 상품 인도를 원하지 않기 때문에 **최초통보일 전에 포지션을 청산**한다.

**최종거래일(Last Trade Date, LTD)**

>  실물을 인도하는 미국 국채 선물(TY)의 경우 최초통보일(FND)이 최종거래일(LTD)보다 빠르고
> 실물을 인도하는 WTI 선물(CL)의 경우 최초통보일(FND)이 최종거래일(LTD)보다 느리다.
>
> 실물을 인도하지 않는 S&P500 e-mini 선물(ES)같은 경우 최초통보일(FND), 최종거래일(LTD), First Delivery Date, Last Delivery Date가 모두 같다.



### 선물 미결제약정(Open Interst, O/I)과 Rollover

선물 만기는 LTD를 기준으로 소통한다. 예를 들어 Mar 25 만기 S&P500 e-mini 선물(ESH5)의 LTD는 2025년 3월 21일이다.

선물 Roll-over는 **최초통보일(FND)과 최종거래일(LTD) 중 빠른 날을 기준**으로 2거래일 전에 거래를 종료하는 것이 일반적이다.
그렇게 함으로써 아웃 거래나 오류가 있는 경우 거래자는 FND 이전에 문제를 해결할 수 있다.

TYZ4와 TYH5의 미결제약정(Open Interst)과 거래량(Volume)추이를 보면 아래와 같다.

<img src="https://github.com/roy8in/roy8in.github.io/blob/main/assets/images/TYZ4,%20TYH5%20OI,%20VOLUME.png?raw=true" style="zoom:100%;" />

(위) TYZ4의 LTD는 2024년 12월 19일이었는데, 해당 선물의 미결제약정이 감소하기 시작하는 시점은 약 1개월 전인 2024년 11월 19일이다. LTD보다 중요한 FND는 2024년 11월 29일인데, 이보다 약 1주일 이상 빠른 시점부터 Rollover가 시작된다. FND 1주일 전인 2024년 11월 22일경에는 TYZ4와 TYH5의 미결제약정의 역전이 발생한다. 

(아래) Volume 추이를 보면 TYZ4의 FND시점 이후에는 TYZ4의 거래량이 의미 없는 수준까지 하락함도 알 수 있다.



### 연결 선물 지수와 P&L

블룸버그에서 제공하는 ES1, TY1 등의 1st 연결 선물 지수들의 경우 LTD를 기준으로 선물 계약을 연결한다. 선물 가격은 LTD 시점에 현물 가격에 수렴하기 때문에 1st 선물 지수는 기초자산의 spot 가격에 주기적으로 수렴하는 모습이 관찰된다. 그러나 이는 현실적으로 구현이 불가능하다.

실제로 선물 rollover를 고려한다면 연결선물 지수는 미결제약정(O/I)이 가장 많은 선물의 가격을 연결해야 한다. 이것이 현실적인 선물을 활용한 포지션의 P&L과 가장 유사하다. 



### Roll Yield

Futures Return = Spot Return + Excess Benefit or Cost of Owning the Underlying Asset
으로 표현[^1]할 수 있다. 

Roll Yield는 선물 수익률과 현물 수익률의 차이로 정의한다.
Roll Yield = Futures Returns - Spot Returns
즉, Roll Yield는 기초자산을 보유함으로써 생기는 초과 이익 혹은 비용이다. S&P500의 경우 Roll Yield는 배당수익률(이익)과 조달 비용(Financing Costs, 비용)이라고 생각할 수 있다.

주요 자산군의 효용과 비용을 정리하면 아래와 같다.

|자산군|효용|비용|
|:----:|:--:|:--:|
|채권|쿠폰|조달 비용|
|외환|해외 예금 금리|국내 예금 금리|
|주식|배당|조달 비용|

S&P500의 경우 배당수익률이 조달 비용보다 낮으면 Roll Yield < 0 이 된다. 배당수익률은 변동성이 크지 않으므로 조달 비용, 즉 시장 금리가 Roll Yield에 중요한 역할을 하게 된다.

Roll 시점 선물의 기간 구조(term structure)는 Roll Yield와 관련이 있다. Long 포지션을 기준으로
Contango의 경우 Roll로 인한 비용이 발생하게 되고(Roll Adjustment < 0)
Backwardation의 경우 Roll로 인한 수익이 발생하게 된다(Roll Adjustment > 0).

선물의 기간 구조가 Contango라면 선물을 Rollover하는 과정에서 더 높은 가격의 선물 계약을 매수하고, 해당 선물 계약이 만기에 가까워짐에 따라 Spot 가격으로 수렴하는 과정에서(높은 가격으로 매수하였으므로) 현물 대비 상대적으로 수익이 덜 나게 된다. BLASH의 반대 상황이다.

다만, 선물의 경우 레버리지가 수반되며, 증거금을 제외한 나머지 현금에서 발생하는 이자(+증거금에서 발생하는 이자)와 현물을 보유함에 따라 받게 되는 배당, 쿠폰 등의 차이가 연결 선물의 Spot (총수익)지수 대비 언더퍼폼 영향을 일부 상쇄할 수 있다.






[^1]: Deconstructing Futures Returns: The Role of Roll Yield, Campbell White Paper Series (February 2014)
