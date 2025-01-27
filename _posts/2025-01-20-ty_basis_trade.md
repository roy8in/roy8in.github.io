---
title: 베이시스(basis) 트레이드
date: 2025-01-20
categories: 
- derivatives
tags: [futures, roll yield]
comments: True
use_math: True
---



**Basis Trade**

베이시스 트레이드는 현물(spot)과 선물(futures) 중 상대적으로 저평가된 자산을 사고 다른 것을 매도하는 방법으로 차익을 취하는 전략이다.  국채선물(Futures)을 매도하고 상대적으로 저렴한 국채현물(Spot)을 매수한 후 만기에 전체 포지션을 정리하는 전략이다. 베이시스 트레이드는 헤지펀드가 많이 사용하는 전략으로 알려져있다.

헤지펀드들은 국채 현물을 매수하고, 국채 선물을 매도하는 포지션을 잡고 있다. 이는 CFTC 데이터를 통해 알 수 있다. CFTC 데이터에서는 Hedge Fund라는 명목으로 [트레이더를 분류](https://www.cftc.gov/sites/default/files/idc/groups/public/@commitmentsoftraders/documents/file/tfmexplanatorynotes.pdf)하고 있지 않으나, Leveraged Funds라는 카테고리로 헤지펀드와 CTAs 등의 포지션을 표기한다. 

Leveraged Funds를 헤지펀드라고 보면, 2025년 1월 기준 **헤지펀드들은 국채 선물에 대해 순매도 포지션**을 취하고 있다. TU에 대한 헤지펀드들의 순매수 포지션(TFF2GLFN Index), FV에 대한 헤지펀드들의 순매수 포지션(TFF2INFN Index), TY에 대한 헤지펀드들의 순매수 포지션(TFF2HLFN Index)를 통해 이를 확인할 수 있다. 헤지펀드들은 선물에 대해 매도 포지션을 취한 만큼 현물에 대해서는 매수(basis trade)하므로 헤지펀드들은 **신규로 발행되는 국채(현물)를 소화**하는 주체로의 역할을 하기도 한다. 주로 2년, 5년, 10년 국채가 베이시스 트레이드의 대상으로 알려져있다.

참고로 기관투자자 등을 일컫는 Asset Managers들은 Leveraged Funds의 포지션의 상대방으로써 국채에 대해 순매수 포지션을 취하고 있다.

헤지펀드들은 수익률 극대화를 위해 레포시장을 통해 레버리지를 일으킨다. 국채현물을 매입한 후 레포시장에서  국채를 담보로 제공하고 현금을 차입한다. 미국국채를 담보로 한 레포시장에서 Haircut은 2%로 약 50배까지의 레버리지가 가능하다.

헤지펀드는 1일 만기 레포를 통해 자금을 차입하는데, O/N 레포시장에서 문제가 발생해 레포금리가 급등하게 된다면 헤지펀드는 어쩔 수 없이 갖고 있는 베이시스 트레이드 규모를 줄여야 한다. 즉, 기존에 갖고 있던 국채 선물에 대한 매도 포지션을 매수 포지션을 통해 줄이고, 매수하고 있던 국채 현물은 매도해야 한다. 헤지펀드들이 구축한 포지션의 가파른 되돌림은 국채 금리 변동성을 크게 키울 수 있다.

단, 헤지펀드들이 다른 목적으로 국채 선물에 대해 매도포지션을 취할 수 있음에 유의해야 한다. [2024년 3월 연준 연구](https://www.federalreserve.gov/econres/notes/feds-notes/quantifying-treasury-cash-futures-basis-trades-20240308.html)에 따르면 CFTC의 Leveraged Funds의 국채 순매도 포지션은 베이시스 트레이드 규모를 과대평가할 가능성을 지적했다. 그럼에도 불구하고 방향성은 유사하다.

