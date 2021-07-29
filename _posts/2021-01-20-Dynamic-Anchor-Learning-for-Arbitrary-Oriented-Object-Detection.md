---
title: Paper Review. Dynamic Anchor Learning for Arbitrary-Oriented Object Detection@AAAI' 2021
author: JooChan Park
date: 2021-01-20 13:00:00 +0800
categories: [Paper Reviews, Object Detection]
tags: [Object Detection, CV]
math: true
pin: False
---

- [Paper link](https://ojs.aaai.org/index.php/AAAI/article/view/16336)

## **Abstract**
- 기존 모델들은 IoU를 적용하여 positive 와 negative 앵커를 샘플링을 함

- Positive 앵커는 항상 정확한 탐지를 보장할 수 없지만, 일부 negative 앵커는 정확한 위치를 파악할 수 있음

- 이는 IoU를 통한 앵커의 품질 평가가 적절하지 않음을 나타내며, 이로 인해 classification confidence와 localization accuracy 사이에 불일치가 발생함

- 이 논문에서는 새롭게 정의된 matching degree를 활용하여 앵커의 localization의 가능성을 종합적으로 평가하는 dynamic anchor learning(DAL) 방법을 제안함


## **Introduction**
<img src='\assets\papers\Dynamic Anchor Learning for Arbitrary-Oriented Object Detection\1.PNG' width='800'>
<img src='\assets\papers\Dynamic Anchor Learning for Arbitrary-Oriented Object Detection\2.PNG' width='800'>
<img src='\assets\papers\Dynamic Anchor Learning for Arbitrary-Oriented Object Detection\3.PNG' width='800'>

- 이러한 문제를 해결하기 위해 DAL(Dynamic Anchor Learning) 방법을 제안함
    1. 앵커의 localization 가능성을 평가하기 위해 간단하면서도 효과적인 MD(Matching Degree)를 설계
    2. Sample selection을 학습하기 위해 matching degree를 사용하여 false-positive 샘플을 제거하고 잠재적인 고품질 후보를 동적으로 선택함
    3. matching-sensitive loss function을 통해 classification과 regression간의 불일치를 완화함


## **Proposed Method**
### Dynamic Anchor Selection
<img src='\assets\papers\Dynamic Anchor Learning for Arbitrary-Oriented Object Detection\4.PNG' width='800'>
<img src='\assets\papers\Dynamic Anchor Learning for Arbitrary-Oriented Object Detection\5.PNG' width='800'>
<img src='\assets\papers\Dynamic Anchor Learning for Arbitrary-Oriented Object Detection\6.PNG' width='800'>
<img src='\assets\papers\Dynamic Anchor Learning for Arbitrary-Oriented Object Detection\7.PNG' width='800'>

### Matching-Sensitive Loss
<img src='\assets\papers\Dynamic Anchor Learning for Arbitrary-Oriented Object Detection\8.PNG' width='800'>
<img src='\assets\papers\Dynamic Anchor Learning for Arbitrary-Oriented Object Detection\9.PNG' width='800'>
<img src='\assets\papers\Dynamic Anchor Learning for Arbitrary-Oriented Object Detection\10.PNG' width='800'>
<img src='\assets\papers\Dynamic Anchor Learning for Arbitrary-Oriented Object Detection\11.PNG' width='800'>

## **Experiments**
- Dataset
    - Aerial datasets
        - HRSC2016
        - DOTA
        - UCAS-AOD

    - Scene text datasets
        - ICDAR 2015

<img src='\assets\papers\Dynamic Anchor Learning for Arbitrary-Oriented Object Detection\12.PNG' width='800'>
<img src='\assets\papers\Dynamic Anchor Learning for Arbitrary-Oriented Object Detection\13.PNG' width='800'>
<img src='\assets\papers\Dynamic Anchor Learning for Arbitrary-Oriented Object Detection\14.PNG' width='800'>
<img src='\assets\papers\Dynamic Anchor Learning for Arbitrary-Oriented Object Detection\15.PNG' width='800'>
<img src='\assets\papers\Dynamic Anchor Learning for Arbitrary-Oriented Object Detection\16.PNG' width='800'>
<img src='\assets\papers\Dynamic Anchor Learning for Arbitrary-Oriented Object Detection\17.PNG' width='800'>
<img src='\assets\papers\Dynamic Anchor Learning for Arbitrary-Oriented Object Detection\18.PNG' width='800'>
<img src='\assets\papers\Dynamic Anchor Learning for Arbitrary-Oriented Object Detection\19.PNG' width='800'>

## **Conclusions & Reviews**
- 고성능의 회전된 객체 탐지를 위해 Dynamic anchor learning 방법을 제안함.

- Classification confidence와 localization accuracy 사이의 불일치를 어느정도 해결함 (양의 상관관계)

- 여러 개의 앵커를 만드는 것이 중요한 것이 아니라 positive, negative 앵커를 어떻게 구분(평가)하느냐가 중요함


## **Reference**
