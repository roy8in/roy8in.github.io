---
title: Term Funding Premium (TFP)
date: 2025-01-28
categories: 
- derivatives
tags: [Interest Rate Derivatives]
comments: True
use_math: True
---





**SOFR Swap**





10년물을 예로 들자. Swap Spread는 "10년 Swap Yield"와 "10년 국채 금리"의 차이를 의미한다.[^1]

1. 10년 Swap Yield는 레포시장에서 하루짜리 Overnight 무위험 대출을 10년 동안 연장하는 금리고
2. 10년 국채 금리는 미국 국채의 형태로 10년 동안의 무위험 수익률을

의미한다. 미국 국채 10년물의 **Swap Spread**는 음수인 경우가 일반적인데 이는 10년 Sawp Yield가 10년 국채 금리보다 낮음을 의미하며 일종의 **기간 프리미엄(Term Premium)**으로 생각할 수 있다. 은행이나 금융기관은 단기로 자금을 조달할 때 보다 장기로 자금을 조달할 때 추가적인 비용이 발생한다. 

미국채 10년 금리는 시장에서 바라보는 10년 동안의 무위험 수익률을 의미하며, 이는 세 가지 요소로 구성된다.

1. (un-observable) 향후 10년 동안 1일짜리 무위험 금리의 (평균적인)복리 수익률
2. (un-observable) 돈을 빌리는 사람의 금리를 10년 동안 확정함에 따라 발생하는 **이자율 변동 위험에 대한 보상**
3. (observable) 돈을 빌리는 사람의 입장에서 매일 Overnight 대출을 롤오버를 하는 것 대신 **10년 동안 안정적인 자금을 조달하는 것을 보장**하는 것에 대한 보상

ACM 모델 등에서는 (2)와 (3)의 합을 Term Premium으로 본다. 여기서는 (3)을 따로 떼어 **Term Funding Premium(TFP)**으로 부르기로 한다. 이는 Swap Spread와 관련이 있다.



(1)과 (2)는 각각 분리하여 관찰할 수 없으나, (3)은 시장에서 관찰할 수 있는데, 10년 SOFR swap yield를 (1)과 (2)의 합으로 볼 수 있기 때문이다. 즉, 10년 국채 금리와 10년 SOFR swap yield의 차이, 즉 - Swap Spread가 (3)이다. 물론 Swap Spread에는 TFP외의 수급이나 특정 만기 채권에 대한 선호도 등이 포함될 수 있다. 그러나 다양한 만기의Swap Spreads를 살펴봄으로써, 즉 Swap Spread의 전체 기간 구조(term structure)를 관찰함으로써 TFP를 추정할 수 있다. 

특정일을 기준으로 세로축(y-axis)엔 On-the-run(OTR) 국채 금리와 Swap Rate의 차이를, 가로축(x-axis)에는 OTR 국채의 modified 듀레이션을 두고 그리면 음의 상관관계를 갖는다. 이 때 기울기가 특정일의 TFP이다. 만약 기울기가 -2.3이라면, 2년까지보다 10년까지는 15bp정도의 추가적인 Term Funding Premium이 요구된다는 의미이다. 이 기울기는 매일 계산 가능하며, 기울기의 시계열도 추적할 수 있다. 기울기 계산을 위해 벤치마크로 2년, 3년, 5년, 7년, 10년, 20년, 30년의 OTR 채권을 사용할 수 있다. 



**Term Funding Premium 모델링**

TFP은 채권시장의 수요와 공급에 따라 그 수준이 변할 것이다. 여기에는 크게 네 가지 요소가 영향을 미친다고 가정할 수 있다.

1. 월간 미국채의 듀레이션 기반 공급량. 공급되는 미국채가 증가할수록(듀레이션이 증가할수록) TFP은 커질 수 있다. 
2. Fed 대차대조표(B/S) 크기. QE/QT는 TFP에 영향을 미칠 수 있다. QE로 연준이 국채를 많이 매입할수록, 즉 B/S사이즈가 커질수록 유동성이 많아짐에 따라 TFP는 작아질 수 있다.
3. 채권 펀드 AUM. 주요 채권 펀드의 AUM이 증가하는 것은 채권에 대한 수요가 증가함을 의미하며, 이에 따라 TFP이 작아질 수 있다.
4. RRP 잔액. RRP 잔액이 증가할수록 채권으로갈 돈이 RRP로 이동했음을 의미하며, 따라서 TFP이 증가할 수 있다.

| Driver                     | TFP 영향 |
| -------------------------- | -------- |
| 월간 미국채 공급(듀레이션) | (+)      |
| Fed 대차대조표             | (-)      |
| 채권 펀드 AUM              | (-)      |
| RRP 잔액                   | (+)      |



기울기 뿐만 아니라 y절편도 계산할 수 있다. y절편의 경우 $x=0$이므로 이는 zero-duration채권의 Swap Spread라고 볼 수 있다.

**Zero Duration Swap Spreads 모델링**

1. TFP 레벨. TFP이 증가할수록 장기 자금 조달에 부담을 느껴 듀레이션을 줄일 것이고, 그에 따라 점점 zero-duration의 swap spread에 근접한다. 즉, TFP 레벨이 커질수록 y절편은 증가한다.
2. RRP 잔액. RRP 잔액이 증가할수록 채권으로갈 돈이 RRP로 이동했음을 의미하며, 따라서 y절편도 증가할 수 있다.
3. 단기 금리 수준. 3m3m OIS rate와 같은 단기 금리가 높을수록 zero duration swap spread(=swap rate - treasury yield)는 감소한다.

| Driver         | y절편 영향 |
| -------------- | ---------- |
| TFP 레벨       | (+)        |
| RRP 잔액       | (+)        |
| 단기 금리 수준 | (-)        |





[^1]: Srini Ramaswamy 등, Interest Rate Derivatives: Term Funding Premium and the Term Structure of SOFR Swap Spread, J.P.Morgan North America Fixed Income Strategy, 2024.04.29.











