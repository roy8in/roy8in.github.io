---
layout: post
title: "(정규분포) 평균과 표준편차를 활용한 VaR와 CVaR 계산"
author: Roy
date: 2021-05-06
last_modified_at: 2021-05-06
category:
  - Quantitative
tags:
  - Risk Management
comments: true
use_math: true
---
확률변수 $X$가 평균 $\mu$, 표준편차 $\sigma$인 정규분포를 따른다고 가정하자.
$$
X \sim N(\mu, \sigma^2)
$$
$95\%$ 등 신뢰도를 $\beta$,  $\beta-VaR$를 $\alpha_\beta (x)$,  $\beta-CVaR$를 $\phi_\beta (x)$라고 할 때 다음이 성립한다.
***
$$
\begin{align}
&\alpha_\beta (x)=\mu(x)+c_1(\beta) \sigma(x) \\
&\phi_\beta (x) =\mu(x)+c_2(\beta) \sigma(x) \\
\end{align}
$$
여기서
$$
\begin{align}
 c_1(\beta)&= \sqrt{2} \mathrm{erf}^{-1}(2\beta-1) \\
 c_2(\beta)&= {1\over 1-\beta }{1 \over {\sqrt{2\pi}}} \mathrm{exp}(-[{\mathrm{erf}^{-1} (2\beta -1)]^2})\\
\mathrm{erf}(z)&= {2 \over \sqrt{\pi}} \int_0^{z} \mathrm{e}^{-t^2} dt
\end{align}
$$
이다.

***