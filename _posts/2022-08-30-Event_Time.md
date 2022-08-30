---
layout: post
title: Event Time
date: 2022-08-30
categories: Quant
tag: Mahalanobis, Distance, Probability, Quant, Quantitative, Information Theory, python, 마할라노비스, 거리, 확률, 퀀트, 계량분석, 정보이론, 파이썬
comments: true
use_math: true
---

금융자산 수익률의 측정 단위를 시간(calendar)이 아닌 사건(event) 기준으로 하는 방법에 대한 M. Czasonis, M. Kritzman, D. Turkington의 최근 [페이퍼](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4101500)를 정리/이해하고 실습해본다.

***



1년이라는 시간은 지구가 태양을 한 바퀴 도는 데 걸리는 기간을 의미한다. 시간을 기준으로 100m 달리기 기록을 측정하는 것은 합리적이다. 그러나 NBA 농구선수가 한 주라는 시간 동안 얼마나 많은 득점을 기록하였는지는 합리적이지 않다. 비시즌 기간에는 0점을 기록할 수도 있다. 반면 시즌 중에는 경기를 많이 치르는 주간도 있고, 경기를 적게 치르는 주간도 있다. 따라서 경기 당 평균 득점 등을 사용한다.

금융자산 수익률을 측정할 때에도 비슷한 고민을 할 수 있다. 지구가 태양을 도는 것과 투자 전략 사이에는 어떠한 관계가 있을까? 자산 수익률을 시간(calendar)이 아닌 사건 집약도(event intensity)를 활용한 단위로 측정하는 방안을 고민해본다.

클러드 섀넌(Claude Shannon)이 고안한 정보 이론(Information Theory)에 따르면 정보란 불확실성(entropy)를 줄여주는 정도를 뜻한다. 그리고 발생할 확률이 낮은 사건일수록 더 많은 정보를 전달한다. 정보의 개념을 활용해 누적된 자산 수익률의 비정상적 움직임을 이용해 사건 집약도를 측정하고, 이를 기준으로 자산 수익률을 기록한다. 즉, 동일한 시간 간격 대신 동일한 사건 집약도를 갖는 간격으로 수익률을 측정한다.

비정상적(unusual)인 수익률일수록 그것은 잡음(Noise)의 결과라기 보다는 금융시장의 혼란을 일으키는 재앙적 사건과 관련이 있을 가능성이 높다. 여기서 '비정상적임'은 [Mahalanobis distance](https://en.wikipedia.org/wiki/Mahalanobis_distance)를 활용해 측정한다.



> **참고**: Mahalanobis 거리
>
> <center>
> $d=(x-\mu)\Sigma^{-1}(x-\mu)^{'}$
> </center>
>
> 여기서 $d$는 Mahalanobis 거리를, $x$는 변수들의 행벡터, $\mu$는 변수들의 과거 평균, $\Sigma^{-1}$는 변수들의 공분산행렬의 역행렬, $^{'}$는 행렬의 transpose를 의미한다. 최근에 관찰된 데이터($x$)가 그것의 과거 흔적($\mu$, $\Sigma$)과 얼마나 다른지를 측정하는 것이다. 
>
> Mahalanobis 거리가 일반적으로 사용되는 [유클리드 거리(Euclidean distance)](https://en.wikipedia.org/wiki/Euclidean_distance)와 가장 다른 점은 이전까지 측정된 변수들 간의 공분산, 즉 표준편차와 상관관계를 함께 고려한다는 점이다. 단순히 과거 평균으로부터 멀리 벗어나 유클리드 거리 $(x-\mu)(x-\mu)^{'}$가 큰 것이 비정상적인 모습이 아니라, 과거 패턴과의 유사성($\Sigma$)을 고려한 유클리드 거리가 큰 것이 비정상적인 것이다.
>
> 아래 그림에서 <span style="color:red">점 A</span>는 <span style="color:green">점 B</span>보다 유클리드 거리는 길다. 하지만 <span style="color:red">점 A</span>는 두 변수의 부호가 같은 반면, <span style="color:green">점 B</span>는 이전과 다르게 두 변수의 부호가 다르다. 따라서 미리 설정한 타원의 영역을 벗어나고, 그 결과 Mahalanobis 거리가 더 길게 계산된다. 즉 Mahalanobis 거리는 한 점에서 정규분포 $\mathcal{N}(\mu, \Sigma)$ 까지의 거리를 측정한다.
>
> <img src="/assets/images/Mahalanobis_distance1.png" width="90%" height="90%" title="점 A는 점 B보다 Mahalanobis 거리가 가깝다."/>



수익률 기록의 기준을 Calendar time에서 Event time으로 변환하기 위해 짧은 기간에서 계산한 Mahalanobis 거리의 누적된 합이 미리 정한 threshold를 넘기면, 그 시점을 기록하여 새로운 시점의 기준을 만든다. 새로운 시점이 기록되면 누적된 Mahalanobis를 0으로 초기화하고 다시 누적하기 시작한다. 이를 python 코드로 작성하면 다음과 같다.

```python
import numpy as np

def mahalanobis(x=None, data=None, cov=None):
    x_mu = x - data.mean()
    if not cov:
        cov = np.cov(data.values.T)
    inv_cov = np.linalg.inv(cov)
    left = np.dot(x_mu, inv_cov)
    mahal = np.dot(left, x_mu.T)
    return mahal

def indexer(df_returns, window = 260, threshold = 100):
    idx = []
    d_mahal = 0
    for i in range(window, len(df_returns)-window):    
        x = df_returns.iloc[i+window]
        data = df_returns.iloc[i: i+window]
        d_mahal += mahalanobis(x, data)
        if d_mahal >= threshold:
            d_mahal = 0
            idx.append(x.name)
    return idx
```

1989년 9월 11일부터 2022년 8월 29일까지 미국 S&P500 지수의 GICS 기준 하위 10개 섹터 지수들의 일간 수익률을 기준으로 threshold 100을 기준으로 사건 집약도를 계산했다. 이를 기준으로 새로운 indexing을 해보면 사건 집약도 기준 한 구간은 평균 10영업일이었다. S&P500 에너지 업종 지수의 10영업일 간격 수익률을 계산(10일 수익률, 이하 Calendar)한 결과와 Mahalanobis를 이용해 사건 집약도 기준 구간 수익률(이하 Event)의 분포를 함께 그려보면 다음과 같다.

<img src="/assets/images/Comparing return distribution_energy.png" width="65%" height="65%" title="에너지 업종 기간 수익률 분포 비교: Calendar(좌) vs. Event(우)"/>

Event 기준 분포가 Calendar 기준 분포보다 첨도가 낮고, 극단치가 적게 발생하는 것을 확인할 수 있다. 주요 통계치를 비교해보면 아래와 같다.

|   구분   | Calendar |  Event  |
| :------: | :------: | :-----: |
|   평균   |  0.0035  | 0.0033  |
| 표준편차 |  0.0461  | 0.0470  |
|   왜도   | -0.9116  | -0.2016 |
|   첨도   |  9.2603  | 2.1048  |
|  최솟값  | -0.4107  | -0.2457 |
|  최댓값  |  0.2150  | 0.1848  |

같은 평균과 같은 표준편차를 갖는 정규분포의 pdf와 비교해보면 Event 기준 분포가 더욱 정규분포와 닮았음을 알 수 있다.

<img src="/assets/images/compare with normal dist_energy.png" width="100%" height="100%" title="에너지 업종 정규분포와 비교: Calendar(좌) vs. Event(우)"/>



