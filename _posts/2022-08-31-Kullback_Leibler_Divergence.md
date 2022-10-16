---
title: Kullback-Leibler Divergence
date: 2022-08-31
categories: 
    - Information_Theory
tag: 
    - [Probability]
comments: True
use_math: True
---

쿨백-레이블러 발산(Kullback-Leibler Divergence)에 대해 알아본다.

***

### 엔트로피(Entropy)

엔트로피란 사건을 예측하는 데에 필요한 질문 개수를 의미한다. 다른 표현으로는 최적의 전략 하에서 필요한 질문개수에 대한 기댓값이다. 

1부터 4까지 자연 수 중 하나를 맞추기 위해서는

1. {1, 2} vs. {3, 4}

2. (1 vs. 2) or (3 vs. 4)

2개의 질문이 필요하다. 

알파벳은 26개인데, 26개의 알파벳 중 하나를 맞추는 경우에 최적의 전략은 선택지를 절반씩 나누는 것이다. 이 경우에 $2^{질문개수} = 26$ 이다. 일반적으로

<center>질문개수 = $\log_2$(가능한 결과의 수)</center>

임을 알 수 있다.



엔트로피가 감소한다는 것은 우리가 사건을 맞히기 위해서 필요한 질문의 개수가 줄어드는 것을 의미한다. 즉, 불확실성이 감소한다는 것을 의미한다.



$X$가 $x \in S_X$를 값으로 가질 수 있는 이산 확률 변수(discrete random variable)일 때, X의 엔트로피(entropy)는 다음과 같다.

<center>$H[X]= - \sum\limits_{x \in S_x} p(x) \log(p(x))$</center>



### 교차 엔트로피(Cross Entropy)

확률변수 $X$의 엔트로피를 측정할 때 $X$의 실제 분포 $p$가 아닌 잘못된 분포 $q$를 사용할 경우, 즉

<center>$H_c(p|q) = - \sum\limits_{x \in S_x} p(x) \log(q(x))$</center>

는 $H(X)$ 보다 불확실성이 더해진다. 즉, 



<center>$H_c(p|q) = - \sum\limits_{x \in S_x} p(x) \log(q(x))=H(X)- \sum\limits_{x \in S_x} p(x) \log( {q(x) \over p(x)})$</center>



이므로, $H(X)$에 $- \sum\limits_{x \in S_x} p(x) \log( {q(x) \over p(x)} )$ 만큼의 불확실성이 더해진다. 이 추가되는 불확실성을 쿨백-라이블러 발산(Kullback-Leibler Divergence)라고 부른다.



쿨백-라이블러 발산(Kullback-Leibler Divergence)는 두 확률분포의 차이를 계산하는 데에 사용하는 함수로, 어떤 이상적인 분포($q$)에 대해, 그 분포를 근사하는 다른 분포($p$)를 사용해 샘플링을 한다면 발생할 수 있는 엔트로피 차이를 계산한다. 상대 엔트로피(relative entropy)라고도 한다.

<center>$D_{KL} (p ||q) = - \sum\limits_{x \in S_x} p(x) \log \left[ q(x)\over p(x) \right]$</center>

여기서 $p(x)$와 $q(x)$가 닮을수록 $\log\left[ q(x)\over p(x) \right]$ 값이 0에 가까워지고 $D_{KL}$의 값은 0에 가까워 진다. 즉 Divergence가 적다.
