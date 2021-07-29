---
title: Paper Review. Learning to Reweight Examples for Robust Deep Learning@ICML' 2018
author: JooChan Park
date: 2020-04-15 18:00:00 +0800
categories: [Paper Reviews, Machine Learning]
tags: [Meta Learning, Machine Learning]
math: true
pin: true
---

- [Paper link](http://proceedings.mlr.press/v80/ren18a.html)

## **Abstract**
- 일반적인 지도학습 데이터는 bias와 noisy label가 존재함

- Gradient direction에 따라 훈련 데이터에 가중치를 할당 하는 방법을 제안하며 이것이 bias와 noisy label을 잡을 수 있다고 주장함

- Bias와 noisy label이 없는 소량의 검증 데이터(validation set)가 있다면 class imbalance와 noisy label 문제를 완화 할 수 있음


## **Introduction**
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\1.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\2.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\3.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\4.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\5.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\6.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\7.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\8.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\9.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\10.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\11.PNG' width='800'>

## **Proposed Method**
### Meta-Learning Objective
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\12.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\13.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\14.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\15.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\16.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\17.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\18.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\19.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\20.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\21.PNG' width='800'>

### Online Approximation
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\22.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\23.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\24.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\25.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\26.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\27.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\28.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\29.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\30.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\31.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\32.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\33.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\34.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\35.PNG' width='800'>

### Learning to Reweight Examples in a MLP
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\36.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\37.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\38.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\39.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\40.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\41.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\42.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\43.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\44.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\45.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\46.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\47.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\48.PNG' width='800'>


## **Experiments**
- MNIST 및 CIFAR 벤치 마크에서 임의로 class imbalance와 noisy label을 설정하고 reweighting 알고리즘의 효과를 테스트 함

- MNIST data setting
    - Class 4와 9에 대해서 총 5,000장의 이미지를 다양한 비율로 class imbalance가 발생하도록 샘플링 하여 training set으로 둠
    - Training set에서 10장의 이미지로 구성된 class balance한 validation set을 생성

<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\49.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\50.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\51.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\52.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\53.PNG' width='800'>
<img src='\assets\papers\Learning to Reweight Examples for Robust Deep Learning\54.PNG' width='800'>


## **Conclusions & Reviews**
- Training examples에 reweighting하는 online meta-learning 알고리즘을 제안함

- Class imbalance, noisy label, class imbalance + noisy label인 training examples에 성능이 좋음

- Deep learning architecture에 바로 적용 가능함

- 모든 training step에 validation을 사용하는 것은 참신함

- 소량이지만 clean한 validation set만 가지고 class imbalance와 noise가 들어간 label을 어느정도 해결 할 수 있다는 점이 흥미로웠음

- 학습 할 때 validation set을 사용해 loss를 주는 방식을 생각해볼 수 있지만 어떻게 줄지를 생각해 내는 것이 어려운 것 같고 어떻게 줄지를 생각해도 이렇게 수학적으로 의미 있게 푸는 방식이 대단했음

- 수식이 많지만 notation이 자세히 되어있지 않아 추론해야 하는 부분이 많았음

- Convergence of the reweighted training에 대한 내용을 수학적으로 증명하는 부분이 있는데 이해하지 못해서 다음에 이해하면 좋을 것 같음


## **Reference**
