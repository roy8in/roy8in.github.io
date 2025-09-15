---
title: 포트폴리오 내 자산 비중 변화의 변동성
date: 2025-09-15
categories: [arithmetic]
tags: [SAA, Rebalancing]
comments: True
---

기본적인 확률과정(random process)을 이용하여 포트폴리오 내 자산(군) 비중 변화의 변동성에 대해 생각해봅니다.

## 기본 가정

$t$ 시점에서 자산군 $j$의 평가금액을 $NAV_t^j$라고 하고, $t$시점에서 자산군 $j$의 비중을 $\omega_{t, j}$라 한다면, 

$$
\omega_t^j := \frac{NAV_{t}^j}{\sum_{i} NAV_{t}^i}
$$

라고 할 수 있다. 앞으로 편의상 Portfolio의 P를 따와 

$$
NAV_{t}^{P} \equiv \sum_{i} NAV_{t}^{i}
$$

라고 쓴다.

여기서 앞으로의 논의를 위해 큰 가정을 하나 하기로 한다. $i$가 자산군 혹은 포트폴리오를 의미하는 문자일 때, $t$시점에서 자산군 $i$의 평가금액은 다음과 같은 Geometric Brownian Motion을 따른다고 가정한다.

$$
NAV_{t}^{i} = NAV_{0}^{i} e^{(\mu_i - \sigma_{i}^2/2)t+\sigma_{i} W_{t}^i},
$$

여기서 $W_{t}^{i}$는 Winer process이고, $\mu$는 drift term(평균), $\sigma$는 변동성(표준편차)를 의미한다. 

## 계산 

이를 활용하여 $t-1$부터 $t$까지의 평가금액 변화율을 계산하면

$$
\frac{NAV_{t}^{i}}{NAV_{t-1}^{i}} = e^{(\mu_i - \sigma_i^2 /2) + \sigma_i (W_{t}^{i} - W_{t-1}^{i})} = e^{(\mu_i - \sigma_i^2 /2) + \sigma_i \xi_{t}^{i}}
$$

임을 알 수 있다. 여기서 $\xi_t^{i}:= W_{t}^{i} - W_{t-1}^{i} \sim \mathcal{N}(0,~1)$이다.

자산군 $j$에 대해 $t$시점의 비중 $\omega_t^{j}$과 $t-1$시점의 비중 $\omega_{t-1}^{j}$의 차이를

$$
\triangle \omega_{t}^{j} := \omega_t^{j} - \omega_{t-1}^{j}
$$

로 쓰기로 한다. 

$$
\begin{aligned}
\log(\omega_{t}^{j})-\log(\omega_{t-1}^{j})
&= \log \left( \frac{NAV_{t}^{j}}{NAV_{t-1}^{j}} \times \frac{NAV_{t-1}^{P}}{NAV_{t}^{P}} \right) \\
&= \log \left( e^{(\mu_{j} - \sigma_{j}^{2} /2) + \sigma_{j} \xi_{t}^{j}} \times e^{(\mu_{p} - \sigma_{p}^2 /2) + \sigma_{p} \xi_{t}^{p}}\right) \\
&= (\mu_{j} - \mu_{p}) - (\sigma_{j}^2 - \sigma_{p}^2)/2 + (\sigma_{j} \xi_t^{j} - \sigma_p \xi_t^p)
\end{aligned}
$$

이고,

$$
\begin{aligned}
\log(\omega_{t}^{j})-\log(\omega_{t-1}^{j})
&= \log(\omega_{t}^j / \omega_{t-1}^{j}) \\
&= \log\left(1+ \frac{\triangle \omega_{t}^{j}}{\omega_{t-1}^{j}} \right) \\
& \approx \frac{\triangle \omega_{t}^{j}}{\omega_{t-1}^{j}}
\end{aligned}
$$

이므로

$$
\begin{aligned}
\triangle \omega_{t}^{j}
&\approx \omega_{t-1}^{j} \left[ (\mu_{j} - \mu_{p}) - \tfrac{1}{2}(\sigma_{j}^2 - \sigma_{p}^2) + (\sigma_{j} \xi_t^{j} - \sigma_p \xi_t^p) \right] \\
&= \omega_{t-1}^{j}\left[ (\mu_{j} - \mu_{p}) - \tfrac{1}{2}(\sigma_{j}^2 - \sigma_{p}^2)\right] + \omega_{t-1}^{j}\left[ (\sigma_{j} \xi_t^{j} - \sigma_p \xi_t^p) \right]
\end{aligned}
$$

임을 알 수 있다. 여기서 첫 번째 항은 $t-1$ 시점에 알 수 있는(deterministic) 값이고, 두 번째 항은 $t$시점에서 확인할 수 있는 확률변수이다. 이를 통해 알 수 있는 점은

- $t-1$시점에서 $t$시점까지의 비중 변화 $\omega_{t}^{j}$는 $t-1$시점에서의 비중 $\omega_{t-1}^{j}$에 비례한다.
- 전체 포트폴리오 $p$의 변동성과 자산군 $j$의 변동성이 유사하다면($\sigma_j \approx \sigma_p$), 자산군 $j$의 기대수익률이 포트폴리오 $p$의 기대수익률보다 클 경우($\mu_{j} > \mu_{p}$) $t$시점에서의 비중 $\omega_{t}^{j}$은  $t-1$시점에서의 비중  $\omega_{t-1}^{j}$보다 클 확률이 높다. 다만, 이는 확률변수 $\xi_{t}^{j}$와 $\xi_{t}^{p}$에 의해 임의성(randomness)이 부여된다.
- 자산군 $j$의 기대수익률이 포트폴리오 $p$의 기대수익률이 유사하다면($\mu_{j} \approx \mu_{p}$) 자산군 $j$의 변동성이 전체 포트폴리오 $p$의 변동성보다 작을 경우($\sigma_j < \sigma_p$), $t$시점에서의 비중 $\omega_{t}^{j}$은  $t-1$시점에서의 비중 $\omega_{t-1}^{j}$보다 클 확률이 높다. 다만, 이는 확률변수 $\xi_{t}^{j}$와 $\xi_{t}^{p}$에 의해 임의성(randomness)이 부여된다.

Wiener Process의 특성 중 하나인

$$
\xi_{t}^{j} = W_{t}^{j} - W_{t-1}^{j} \sim \mathcal{N} (0,~1^2)
$$

을 활용하면, 두번째 항은
$\mathcal{N}(0,\sigma_{j}^{2})$
을 따르는 확률변수와 
$\mathcal{N}(0,\sigma_{p}^{2})$
을 따르는 확률변수의 차이와 관련이 있다. 이때 두 확률변수는  $\rho_{j, p}$를 상관관계로 갖는다고 가정한다.

$\mu_j, \mu_p, \sigma_j, \sigma_p$는 주어진 파라미터(상수)이고, 
$\xi_t^i \sim \mathcal{N}(0,~1^2)$
라는 점을 이용하여 양변에 기댓값을 취하면

$$
\mathbb{E}\left[ \triangle \omega_{t}^{j} \right]
\approx 
\omega_{t-1}^{j}\left\{ (\mu_{j} - \mu_{p}) - \tfrac{1}{2}(\sigma_{j}^2 - \sigma_{p}^2)\right\}
$$

이고,

$$
Var\left[ \triangle \omega_{t}^{j}\right] \approx \left(\omega_{t-1}^{j} \right)^2 \left( \sigma_{j}^{2} - 2\rho_{j,p} \sigma_{j}\sigma_{p} + \sigma_{p}^2\right)
$$

이다. 

즉, 자산군 $j$의 비중 변화의 변동성은

- 이전 시점($t-1$)에서의 비중 $\omega_{t-1}^{j}$
- 자산군 $j$의 변동성 $\sigma_{j}$
- 포트폴리오 $p$의 변동성 $\sigma_p$
- 자산군 $j$와 포트폴리오 $p$의 상관관계 $\rho_{j, p}$

와 관련이 있다. $\omega_{t-1}^j$가 클수록 $\rho_{j, p}$는 1에 가까워지며, $\sigma_j$와 $\sigma_p$의 값은 유사해진다.

이처럼 자산군의 비중 $\omega_{t-1}^j$는 다른 변수에 미치는 영향이 존재하나, 실무적으로 SAA 밴드를 설정할 시점에 $\omega_{t-1}^j$는 주어진 값(given condition)으로 취급하는 것이 편하다. 따라서 논의의 편의를 위해 $\omega_{t-1}^{j}$와 $\left(\sigma_j, \sigma_p, \rho_{j, p}\right)$를 구분하여 생각하기로 한다.

다른 모든 것이 동일하다면, 자산군 $j$의 비중 변화의 변동성은

- 이전 시점($t-1$)의 비중 $\omega_{t-1}^j$에 비례하고
- 자산군 $j$의 변동성 $\sigma_j$의 영향과 포트폴리오 $p$의 변동성 $\sigma_p$의 영향은 상관관계 $\rho_{j, p}$와 변동성의 상대적인 크기에 따라 영향이 달라진다.

$$
V(\sigma_j, \sigma_p, \rho_{j, p}) := \sigma_j^2 - 2 \rho_{j, p} \sigma_j \sigma_p + \sigma_p^2
$$

라고 했을 때

- $\partial V/ \partial \sigma_j = 2(\sigma_j - \rho_{j, p} \sigma_p)  $이므로, $\sigma_j > \rho_{j, p} \sigma_p$인 경우 $V$는 $\sigma_j$에 비례하고,  $\sigma_j < \rho_{j, p} \sigma_p$인 경우 $V$는 $\sigma_j$에 반비례
- $\partial V/ \partial \sigma_p = 2(\sigma_p - \rho_{j, p} \sigma_j)  $이므로, $\sigma_p > \rho_{j, p} \sigma_j$인 경우 $V$는 $\sigma_p$에 비례하고,  $\sigma_p < \rho_{j, p} \sigma_j$인 경우 $V$는 $\sigma_p$에 반비례
- $\partial V/ \partial \rho_{j, p} = -2 \sigma_j \sigma_p <0$이므로, $V$는 $\rho_{j, p}$에 반비례

함을 알 수 있다. 

## 결론

이 결과를 위험자산과 안전자산에 주는 영향에 대해 생각해보면

- 위험자산  
  $\rho_{j, p} \in [-1, 1]$ 이므로 포트폴리오 $p$의 변동성보다 큰 변동성을 갖는 자산 $j$의 경우 $\sigma_j > \rho_{j, p} \sigma_p$이므로 비중 변화의 변동성은 $\sigma_j$가 클수록 커진다.
- 안전자산  
  포트폴리오 $p$의 변동성보다 작은 변동성을 갖는 자산 $j$의 경우 $\rho_{j, p}$이 충분히 작으면(분산효과가 높은 자산, 예: 국내채권) $\sigma_j > \rho_{j, p} \sigma_p$인 상황이 충분히 발생할 수 있으며, 이 경우에도 비중 변화의 변동성은 $\sigma_j$에 비례한다.

포트폴리오 내 비중 변화의 변동성은 크게 4가지 요소의 영향을 받으며, 그 정도에 대해서는 다양한 조합이 가능하다. SAA 리밸런싱의 범위(밴드)를 자산군 비중 변화의 변동성과 관련하여 설정한다면

$$
Var\left[ \triangle \omega_{t}^{j}\right] \approx \left(\omega_{t-1}^{j} \right)^2 \left( \sigma_{j}^{2} - 2\rho_{j,p} \sigma_{j}\sigma_{p} + \sigma_{p}^2\right)
$$

이 식을 참고할 수 있다.
