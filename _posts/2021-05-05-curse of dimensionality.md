---
layout: post
title: "차원의 저주(Curse of Dimensionality)"
author: Roy
date: '2021-05-05'
category:
  - Quantitative
tags:
  - python
---

 

단위 직선(1) 안에 있는 임의의 두 점을 선택하면 두 점 사이의 거리는 평균적으로 0.33 이다.

![1dim](https://user-images.githubusercontent.com/72531163/117042203-a0ade900-ad46-11eb-8da2-8afddad26a5d.png)

단위 면적(1×1) 안에 있는 임의의 두 점을 선택하면 두 점 사이의 거리는 평균적으로 0.52 이다.

![2dim](https://user-images.githubusercontent.com/72531163/117042206-a1467f80-ad46-11eb-830f-a2375489a288.png)

단위 큐브(1×1×1) 안에 있는 임의의 두 점을 선택하면 두 점 사이의 거리는 평균적으로 0.66 이다.

![3dim](https://user-images.githubusercontent.com/72531163/117042209-a1467f80-ad46-11eb-95cb-50c832120d93.png)



만약 10차원 속 단위 공간(1×1×1×1×1×1×1×1×1×1) 안에 있는 임의의 두 점을 선택하면 두 점 사이의 거리는 평균적으로 1.27 이다.

![10dim](https://user-images.githubusercontent.com/72531163/117042200-a0155280-ad46-11eb-836d-5fe9ab51bdff.png)


이렇게 차원이 커질수록 임의의 두 점 사이의 거리가 증가하게 되는데, 이는 차원이 클수록 더 많은 공간을 갖고 있기 때문이다. 따라서 고차원에서 예측은 저차원일 때보다 불안정하다. 따라서 차원 축소가 필요하다.

```python
import numpy as np
import matplotlib.pyplot as plt

def curse_of_dim(N, d):
    # make two random points a and b in N-dimensional space
    a = np.random.rand(N, d)
    b = np.random.rand(N, d)

    # calculate distance between two points for each sample
    dist_ = []
    for i in range(N):
        dist_.append(np.linalg.norm(a[i]-b[i]))
    # and take cummulative average
    dist = np.cumsum(dist_)/np.arange(1, N+1)

    # Plot the result
    plt.figure()
    plt.plot(dist)
    plt.xlabel("N")
    plt.ylabel("Distance")
    plt.title("Average distance between two random points\ 
               in %i dimension: %.2f" %(d, dist[-1]))
    return
```